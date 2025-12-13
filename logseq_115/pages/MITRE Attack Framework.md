- **Informe Explicativo de las Tácticas del MITRE ATT&CK para Entornos Empresariales**  
  El marco **MITRE ATT&CK** (Adversarial Tactics, Techniques, and Common Knowledge) es una base de conocimiento estructurada que describe las tácticas y técnicas utilizadas por adversarios en ciberataques. A continuación, se presenta un análisis detallado de las **14 tácticas** definidas para entornos empresariales, ordenadas según el ciclo de vida de un ataque:
  
  ---
- ### 1. **Reconocimiento (Reconnaissance)**  
  **Definición:** Fase inicial donde el adversario recopila información sobre el objetivo para identificar vulnerabilidades y planificar el ataque.  
  **Objetivo:** Obtener datos críticos (ej.: correos electrónicos, infraestructura, empleados).  
  **Técnicas Comunes:**
- Escaneo de redes públicas (WHOIS, DNS).
- Búsqueda de información en redes sociales (OSINT).
- Phishing de sondeo (envío de correos falsos para probar respuestas).  
  **Ejemplo:** Un atacante investiga perfiles de LinkedIn para identificar empleados clave.  
  
  ---
- ### 2. **Desarrollo de Recursos (Resource Development)**  
  **Definición:** Preparación de infraestructura y herramientas necesarias para ejecutar el ataque.  
  **Objetivo:** Establecer recursos bajo control del adversario (ej.: servidores, cuentas falsas).  
  **Técnicas Comunes:**
- Registro de dominios maliciosos similares al objetivo.
- Compra de certificados SSL fraudulentos.
- Creación de cuentas en plataformas legítimas (GitHub, Dropbox) para alojar malware.  
  **Ejemplo:** Configurar un servidor C2 (Command and Control) en un proveedor de cloud público.  
  
  ---
- ### 3. **Acceso Inicial (Initial Access)**  
  **Definición:** Métodos para infiltrarse en la red del objetivo.  
  **Objetivo:** Establecer un punto de entrada.  
  **Técnicas Comunes:**
- Phishing con adjuntos maliciosos.
- Explotación de vulnerabilidades en servicios expuestos (ej.: RDP, VPN).
- Uso de dispositivos USB infectados.  
  **Ejemplo:** Envío de un correo con un documento Word que ejecuta macros maliciosas.  
  
  ---
- ### 4. **Ejecución (Execution)**  
  **Definición:** Ejecución de código malicioso en sistemas comprometidos.  
  **Objetivo:** Activar cargas útiles (malware, scripts).  
  **Técnicas Comunes:**
- Explotación de APIs de Windows (PowerShell, WMI).
- Uso de tareas programadas (cron jobs).  
  **Ejemplo:** Ejecutar un script en PowerShell para descargar ransomware.  
  
  ---
- ### 5. **Persistencia (Persistence)**  
  **Definición:** Mantener acceso a largo plazo tras el acceso inicial.  
  **Objetivo:** Evitar la pérdida de control sobre el sistema.  
  **Técnicas Comunes:**
- Modificación de claves de registro para ejecución al inicio.
- Creación de servicios maliciosos.
- Uso de backdoors.  
  **Ejemplo:** Crear una tarea en Task Scheduler que reactiva el malware cada reinicio.  
  
  ---
- ### 6. **Escalación de Privilegios (Privilege Escalation)**  
  **Definición:** Obtención de mayores permisos en el sistema (ej.: de usuario a administrador).  
  **Objetivo:** Ampliar capacidades de ataque.  
  **Técnicas Comunes:**
- Explotación de vulnerabilidades del kernel.
- Robo de tokens de seguridad (ej.: Pass-the-Ticket).  
  **Ejemplo:** Uso de Mimikatz para extraer contraseñas de memoria.  
  
  ---
- ### 7. **Evasión de Defensas (Defense Evasion)**  
  **Definición:** Técnicas para evitar ser detectado por herramientas de seguridad.  
  **Objetivo:** Ocultar actividades maliciosas.  
  **Técnicas Comunes:**
- Ofuscación de código (cifrado, codificación).
- Eliminación de registros de eventos (logs).
- Inyección de procesos en aplicaciones legítimas.  
  **Ejemplo:** Desactivar un antivirus mediante comandos de administrador.  
  
  ---
- ### 8. **Acceso a Credenciales (Credential Access)**  
  **Definición:** Robo de credenciales para suplantar identidades.  
  **Objetivo:** Obtener acceso a cuentas privilegiadas.  
  **Técnicas Comunes:**
- Keylogging (registro de pulsaciones).
- Ataques de fuerza bruta.
- Extracción de hashes de contraseñas (LSASS).  
  **Ejemplo:** Uso de herramientas como LaZagne para recuperar contraseñas almacenadas.  
  
  ---
- ### 9. **Descubrimiento (Discovery)**  
  **Definición:** Exploración del entorno comprometido para entender su estructura.  
  **Objetivo:** Identificar activos críticos y oportunidades de movimiento lateral.  
  **Técnicas Comunes:**
- Comandos como `ipconfig`, `net view`, o `ls` en sistemas Unix.
- Enumeración de permisos de usuarios.  
  **Ejemplo:** Mapeo de unidades de red compartidas mediante `net use`.  
  
  ---
- ### 10. **Movimiento Lateral (Lateral Movement)**  
  **Definición:** Expansión del acceso a otros sistemas dentro de la red.  
  **Objetivo:** Controlar múltiples puntos para alcanzar objetivos críticos.  
  **Técnicas Comunes:**
- Pass-the-Hash o Pass-the-Ticket.
- Explotación de servicios remotos (ej.: SMB, RDP).  
  **Ejemplo:** Conexión a un servidor interno mediante credenciales robadas.  
  
  ---
- ### 11. **Recopilación (Collection)**  
  **Definición:** Agrupación de datos sensibles para su exfiltración.  
  **Objetivo:** Seleccionar información valiosa (ej.: datos financieros, IP).  
  **Técnicas Comunes:**
- Captura de pantallas.
- Robo de bases de datos o archivos confidenciales.  
  **Ejemplo:** Uso de herramientas como `7-Zip` para comprimir documentos antes de exfiltrarlos.  
  
  ---
- ### 12. **Comando y Control (Command and Control - C2)**  
  **Definición:** Comunicación entre sistemas comprometidos y servidores del atacante.  
  **Objetivo:** Mantener control remoto y enviar instrucciones.  
  **Técnicas Comunes:**
- Protocolos encubiertos (DNS tunneling, HTTP/S).
- Uso de dominios dinámicos (DDNS).  
  **Ejemplo:** Tráfico C2 disfrazado como solicitudes HTTPS a Google Cloud.  
  
  ---
- ### 13. **Exfiltración (Exfiltration)**  
  **Definición:** Transferencia de datos robados fuera de la red.  
  **Objetivo:** Extraer información sin ser detectado.  
  **Técnicas Comunes:**
- Canales cifrados (SSH, VPN).
- Subida a servicios de almacenamiento (Mega, Dropbox).  
  **Ejemplo:** Envío de datos a través de conexiones FTP falsificadas.  
  
  ---
- ### 14. **Impacto (Impact)**  
  **Definición:** Acciones para dañar la disponibilidad o integridad de sistemas y datos.  
  **Objetivo:** Causar interrupción operativa o reputacional.  
  **Técnicas Comunes:**
- Ransomware (cifrado de archivos).
- Borrado de backups.
- Ataques DDoS.  
  **Ejemplo:** Sobrescritura del MBR (Master Boot Record) para inutilizar un sistema.  
  
  ---
- ### **Conclusión**  
  Las tácticas del MITRE ATT&CK representan los **objetivos estratégicos** de un adversario durante un ciberataque, mientras que las técnicas detallan los **métodos específicos** para lograrlos. Este marco permite a las organizaciones mapear defensas, simular ataques (Red Teaming) y priorizar mitigaciones (ej.: segmentación de red para limitar movimiento lateral). Entender estas tácticas es esencial para desarrollar una postura de seguridad proactiva y alineada con amenazas reales.