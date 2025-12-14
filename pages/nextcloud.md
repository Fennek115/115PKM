tags:: #proxmox #code #cloud

- ### Mantenimiento
	- Nextcloud Self-Hosted - Mantenimiento y Configuración
		- Fecha de registro:: 2025-10-18
		- Usuario administrador:: dust115
		- Sistema:: Debian en VM Proxmox
		- Nextcloud:
			- Directorio raíz:: /var/www/nextcloud
			- Datos:: /var/www/nextcloud-data
			- Configuración:: /var/www/nextcloud/config/config.php
				- dbname:: nextcloud
				- dbuser:: nextcloud
				- logfile:: /var/www/nextcloud-data/nextcloud.log
			- Backups:: /var/www/backups/nextcloud
		- PHP:
			- Versión CLI:: 8.2.29
			- Comando PHP:: /usr/bin/php
		- Webserver:
			- Apache2 ejecutándose bajo www-data
		- Scripts:
			- Mantenimiento Nextcloud:: /usr/local/bin/nextcloud-maintenance.sh
			- Funciones principales:
				- Ejecuta cron.php
				- Limpieza de archivos huérfanos
				- Limpieza de versiones antiguas
				- Limpieza de papelera (trashbin)
				- Añade índices y columnas faltantes
				- Convierte filecache a bigint si es necesario
				- Ejecuta maintenance:repair
				- Limpieza de logs antiguos
				- Limpieza de temporales adicionales (/tmp/nextcloud_tmp, /var/tmp/nextcloud)
		- Cron Jobs:
			- Ejecutar cron.php cada 5 minutos (recomendación oficial):
			  ```
			  */5 * * * * sudo -u www-data php /var/www/nextcloud/cron.php
			  ```
			- Ejecutar mantenimiento completo cada 3 días a las 15:00:
			  ```
			  0 15 */3 * * /usr/local/bin/nextcloud-maintenance.sh | tee /var/log/nextcloud-maintenance.log
			  ```
		- Logs importantes:
			- Log de mantenimiento:: /var/log/nextcloud-maintenance.log
			- Log de Nextcloud:: /var/www/nextcloud-data/nextcloud.log
		- Errores observados:
			- `libpng warning: iCCP: known incorrect sRGB profile` → relacionado con imágenes de usuarios
			- `maintenance:cleanup` → no definido, reemplazado por otros comandos
		- Observaciones:
			- Cron.php debe ejecutarse frecuentemente para mantener tareas en segundo plano
			- Directorios temporales y logs se pueden limpiar periódicamente
			- Backups automáticos de DB y config se guardan en /var/www/backups/nextcloud
			- Script de mantenimiento ajustado para Bash y permisos correctos (ejecutado con sudo)
		- #### Codigo del script: #code
			- ```bash
			  ##!/usr/bin/env bash
			  #
			  # nextcloud-maintenance.sh
			  # Script de mantenimiento para Nextcloud
			  # Adaptado (Nextcloud en /var/www/nextcloud)
			  # Guardar en: /usr/local/bin/nextcloud-maintenance.sh
			  # Hacer ejecutable: sudo chmod +x /usr/local/bin/nextcloud-maintenance.sh
			  
			  set -euo pipefail
			  IFS=$'\n\t'
			  
			  # --- Configurables ---
			  NC_USER="www-data"
			  NC_PATH="/var/www/nextcloud"
			  PHP_BIN="/usr/bin/php"
			  LOG_DIR="/var/www"                         # ubicación genérica
			  NEXTCLOUD_LOG_FILE="/var/www/nextcloud-data/nextcloud.log"
			  BACKUP_DIR="/var/www/backups/nextcloud"
			  BACKUP_RETENTION_DAYS=7
			  LOG_RETENTION_DAYS=30
			  
			  # TMP dirs a limpiar
			  TMP_DIRS=(
			    "/tmp/nextcloud_tmp"
			    "/var/tmp/nextcloud"
			  )
			  
			  # ------------------------------------------------
			  log_msg() {
			    echo "[$(date '+%F %T')] $*"
			  }
			  
			  # Intenta extraer credenciales DB desde config.php (si existe)
			  extract_db_config() {
			    local cfg="$NC_PATH/config/config.php"
			    DBNAME=""
			    DBUSER=""
			    DBPASS=""
			    DBHOST=""
			    if [ -f "$cfg" ]; then
			      DBNAME=$(grep -Po "'dbname'\s*=>\s*'\K[^']+" "$cfg" || true)
			      DBUSER=$(grep -Po "'dbuser'\s*=>\s*'\K[^']+" "$cfg" || true)
			      DBPASS=$(grep -Po "'dbpassword'\s*=>\s*'\K[^']+" "$cfg" || true)
			      DBHOST=$(grep -Po "'dbhost'\s*=>\s*'\K[^']+" "$cfg" || true)
			    fi
			  
			    # Fallbacks
			    DBNAME=${DBNAME:-nextcloud}
			    DBUSER=${DBUSER:-nextcloud}
			    DBPASS=${DBPASS:-}
			    DBHOST=${DBHOST:-localhost}
			  }
			  
			  run_occ() {
			    # Usa occ con el usuario del servidor web
			    sudo -u "$NC_USER" "$PHP_BIN" "$NC_PATH/occ" "$@"
			  }
			  
			  # ------------------------------------------------
			  log_msg "==== Inicio mantenimiento Nextcloud ===="
			  
			  # 0) Comprobar que exista la ruta de Nextcloud
			  if [ ! -d "$NC_PATH" ]; then
			    log_msg "ERROR: NC_PATH $NC_PATH no existe. Edita el script con la ruta correcta."
			    exit 1
			  fi
			  
			  # 1) Ejecutar cron.php (jobs en background)
			  log_msg "Ejecutando cron.php (background jobs)"
			  sudo -u "$NC_USER" "$PHP_BIN" "$NC_PATH/cron.php" || log_msg "Warning: cron.php devolvió error (continúa)"
			  
			  # 2) Extraer credenciales DB
			  extract_db_config
			  log_msg "DB info detectada: dbname='$DBNAME' dbuser='$DBUSER' dbhost='$DBHOST' (dbpassword: $( [ -n "$DBPASS" ] && echo "****" || echo "VACÍA" ))"
			  
			  # 3) Limpiezas Nextcloud via OCC
			  log_msg "Limpiando archivos huérfanos (files:cleanup)"
			  run_occ files:cleanup || log_msg "files:cleanup falló o no relevante"
			  
			  log_msg "Limpiando versiones antiguas (versions:cleanup)"
			  run_occ versions:cleanup || log_msg "versions:cleanup falló o no relevante"
			  
			  log_msg "Limpiando papelera de usuarios (trashbin:cleanup) - todo"
			  run_occ trashbin:cleanup --all-users || log_msg "trashbin:cleanup falló o no relevante"
			  
			  # legacy, en los nextcloud actuales se usa maintenance:repair
			  # log_msg "Limpieza de mantenimiento interno (maintenance:cleanup)"
			  # run_occ maintenance:cleanup || log_msg "maintenance:cleanup falló o no relevante"
			  
			  # 4) Indices / columnas / reparaciones administrativas
			  log_msg "Añadiendo índices faltantes (db:add-missing-indices)"
			  # Este puede tardar; ejecuta sin parar el script si falla, sólo lo reportamos
			  run_occ db:add-missing-indices || log_msg "db:add-missing-indices falló o no aplicable"
			  
			  log_msg "Añadiendo columnas faltantes (db:add-missing-columns)"
			  run_occ db:add-missing-columns || log_msg "db:add-missing-columns falló o no aplicable"
			  
			  log_msg "Convertir filecache a bigint si es necesario (db:convert-filecache-bigint)"
			  run_occ db:convert-filecache-bigint || log_msg "db:convert-filecache-bigint (no aplicable o fallo)"
			  
			  log_msg "Ejecutando maintenance:repair"
			  run_occ maintenance:repair || log_msg "maintenance:repair falló o no aplicable"
			  
			  # 5) Opcionales: comprobación de integridad
			  log_msg "Chequeo de integridad del core (integrity:check-core) - puede tardar"
			  run_occ integrity:check-core || log_msg "integrity check devolvió fallo (revisar en logs)"
			  
			  # 6) Limpieza de ficheros temporales definidos
			  for d in "${TMP_DIRS[@]}"; do
			    if [ -d "$d" ]; then
			      log_msg "Limpiando temporales en $d (archivos >7 días)"
			      find "$d" -type f -mtime +7 -print -delete || log_msg "No se pudo limpiar $d"
			    fi
			  done
			  
			  # 7) Backup básico de base de datos y config (si existe DB password se usa)
			  mkdir -p "$BACKUP_DIR"
			  chown "$NC_USER":"$NC_USER" "$BACKUP_DIR" || true
			  log_msg "Realizando backup DB y config (guardando en $BACKUP_DIR)"
			  if [ -n "$DBPASS" ]; then
			    mysqldump -u"$DBUSER" -p"$DBPASS" -h"$DBHOST" "$DBNAME" > "$BACKUP_DIR/db_$(date +%F).sql" 2>/dev/null || log_msg "mysqldump devolvió error"
			  else
			    # si no hay password, intenta sin -p
			    mysqldump -u"$DBUSER" -h"$DBHOST" "$DBNAME" > "$BACKUP_DIR/db_$(date +%F).sql" 2>/dev/null || log_msg "mysqldump devolvió error (comprueba credenciales)"
			  fi
			  tar -czf "$BACKUP_DIR/config_$(date +%F).tar.gz" -C "$NC_PATH" config || log_msg "error al comprimir config"
			  
			  # eliminar backups viejos
			  find "$BACKUP_DIR" -type f -mtime +"$BACKUP_RETENTION_DAYS" -print -delete || true
			  
			  # 8) Rotación / limpieza de logs Nextcloud (si existe fichero)
			  if [ -n "$NEXTCLOUD_LOG_FILE" ] && [ -f "$NEXTCLOUD_LOG_FILE" ]; then
			    log_msg "Rotando / limpiando logs Nextcloud: $NEXTCLOUD_LOG_FILE"
			    # mantener LOG_RETENTION_DAYS para logs antiguos; aquí simplemente truncamos si > 100MB
			    max_mb=100
			    size_mb=$(du -m "$NEXTCLOUD_LOG_FILE" | cut -f1)
			    if [ "$size_mb" -ge "$max_mb" ]; then
			      log_msg "Truncando $NEXTCLOUD_LOG_FILE (size ${size_mb}MB >= ${max_mb}MB)"
			      : > "$NEXTCLOUD_LOG_FILE"
			    fi
			  fi
			  
			  # 9) Limpieza logs custom
			  if [ -d "$LOG_DIR" ]; then
			    log_msg "Limpiando logs en $LOG_DIR con más de $LOG_RETENTION_DAYS días"
			    find "$LOG_DIR" -type f -name "*nextcloud-*.log" -mtime +"$LOG_RETENTION_DAYS" -print -delete || true
			  fi
			  
			  log_msg "==== Mantenimiento completado ===="
			  exit 0
			  
			  ```