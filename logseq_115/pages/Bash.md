## Introducción a Bash

**Bash (Bourne Again Shell)** es un intérprete de comandos y lenguaje de scripting ampliamente utilizado en sistemas Unix y Linux. Permite ejecutar comandos, automatizar tareas y manipular archivos y procesos.
- ### 1.  **Conceptos básicos**
	- Para abrir Bash, puedes usar un terminal en Linux o macOS, o instalar Git Bash en Windows.
	- Un **comando** es una instrucción que ejecuta Bash, por ejemplo:
	  
	  ```
	  ls      # Lista archivos
	  pwd     # Muestra el directorio actual
	  cd      # Cambia de directorio
	  ```
- ### 2.  **Ejecución de scripts**
  
  Un script en Bash es un archivo de texto con instrucciones. Para crear y ejecutar un script:
	- Crea un archivo con extensión `.sh`, por ejemplo:
	  
	  ```
	  nano mi_script.sh
	  ```
	- Agrega el siguiente código:
	  
	  ```
	  #!/bin/bash
	  echo "Hola, Bash!"
	  ```
	- Dale permisos de ejecución:
	  
	  ```
	  chmod +x mi_script.sh
	  ```
	- Ejecútalo:
	  
	  ```
	  ./mi_script.sh
	  ```
- ### 3.  **Variables**
  
  Puedes almacenar valores en variables:
  
  ```
  nombre="Franco"
  echo "Hola, $nombre"
  ```
- ### 4.  **Estructuras de control**
	- #### Condicionales:
	  
	  ```
	  if [ $1 -gt 10 ]; then
	  echo "El número es mayor que 10"
	  else
	  echo "El número es 10 o menor"
	  fi
	  ```
	- #### Bucles:
	  
	  **For loop:**
	  
	  ```
	  for i in {1..5}; do
	  echo "Número $i"
	  done
	  ```
	  
	  **While loop:**
	  
	  ```
	  contador=1
	  while [ $contador -le 5 ]; do
	  echo "Iteración $contador"
	  ((contador++))
	  done
	  ```
- ### 5.  **Redirección y pipes**
	- `>` Redirige la salida a un archivo (sobreescribe):
	  
	  ```
	  echo "Hola" > archivo.txt
	  ```
	- `>>` Agrega contenido a un archivo:
	  
	  ```
	  echo "Mundo" >> archivo.txt
	  ```
	- `|` Conecta comandos:
	  
	  ```
	  ls | grep "txt"  # Filtra archivos con "txt"
	  ```
- ### 6.  **Funciones en Bash**
  
  Puedes definir funciones para reutilizar código:
  
  ```
  mi_funcion() {
  echo "Hola, esta es una función"
  }
  mi_funcion
  ```
  
  ---
- Aquí tienes un **Bash Cheat Sheet** con los comandos y conceptos más usados en Bash:
  
  ---
- ## **BASH CHEAT SHEET**  🚀
- ### 🔹  **1. Navegación y gestión de archivos**
  
  ```
  pwd                   # Muestra el directorio actual
  ls                    # Lista archivos y directorios
  ls -l                 # Lista con detalles
  ls -a                 # Lista archivos ocultos
  cd directorio         # Cambia de directorio
  cd ..                 # Retrocede un nivel
  cd ~                  # Va al home
  mkdir carpeta         # Crea una carpeta
  rmdir carpeta         # Elimina una carpeta vacía
  rm archivo            # Elimina un archivo
  rm -r carpeta         # Elimina una carpeta con su contenido
  cp archivo destino    # Copia un archivo
  mv archivo destino    # Mueve o renombra un archivo
  ```
  
  ---
- ### 🔹  **2. Permisos y procesos**
  
  ```
  chmod +x script.sh    # Da permisos de ejecución
  chmod 777 archivo     # Permisos completos (rwxrwxrwx)
  chown usuario archivo # Cambia el dueño del archivo
  ps aux                # Lista procesos activos
  kill PID              # Mata un proceso por su ID
  killall nombre_proceso # Mata procesos por nombre
  top                   # Monitor de procesos en tiempo real
  btop                  # Versión mejorada de top (requiere instalación)
  ```
  
  ---
- ### 🔹  **3. Redirección y Pipes**
  
  ```
  > archivo.txt         # Redirige salida (sobreescribe)
  >> archivo.txt        # Redirige salida (agrega)
  < archivo.txt         # Usa archivo como entrada
  |                    # Pasa la salida de un comando a otro
  ls | grep "txt"       # Filtra archivos que contienen "txt"
  cat archivo | less    # Permite desplazarse por un archivo
  ```
  
  ---
- ### 🔹  **4. Variables y expansión**
  
  ```
  mi_variable="Hola Mundo"  # Definir variable
  echo $mi_variable         # Mostrar variable
  mi_variable=$(ls)         # Asigna la salida de un comando a una variable
  export mi_variable        # Hace la variable global
  unset mi_variable         # Borra la variable
  ```
  
  ---
- ### 🔹  **5. Condicionales**
  
  ```
  if [ $numero -gt 10 ]; then
  echo "Es mayor que 10"
  else
  echo "Es 10 o menor"
  fi
  ```
  
  Operadores:
- `-eq` (igual)
- `-ne` (no igual)
- `-gt` (mayor que)
- `-lt` (menor que)
- `-ge` (mayor o igual)
- `-le` (menor o igual)
- `[ -f archivo ]` (existe el archivo)
- `[ -d directorio ]` (existe el directorio)
  
  ---
- ### 🔹  **6. Bucles**
  
  **For loop**
  
  ```
  for i in {1..5}; do
  echo "Número $i"
  done
  ```
  
  **While loop**
  
  ```
  contador=1
  while [ $contador -le 5 ]; do
  echo "Iteración $contador"
  ((contador++))
  done
  ```
  
  ---
- ### 🔹  **7. Funciones en Bash**
  
  ```
  mi_funcion() {
  echo "Hola desde la función"
  }
  mi_funcion  # Llamar la función
  ```
  
  ---
- ### 🔹  **8. Alias (atajos personalizados)**
  
  ```
  alias ll="ls -lah"   # Crea un alias para listar archivos detalladamente
  unalias ll           # Elimina un alias
  ```
  
  ---
- ### 🔹  **9. Trabajo con archivos de texto**
  
  ```
  cat archivo.txt        # Muestra el contenido
  less archivo.txt       # Permite desplazarse
  head -n 5 archivo.txt  # Muestra las primeras 5 líneas
  tail -n 5 archivo.txt  # Muestra las últimas 5 líneas
  grep "texto" archivo   # Busca líneas que contengan "texto"
  sed 's/viejo/nuevo/g' archivo.txt  # Reemplaza "viejo" por "nuevo"
  awk '{print $1}' archivo.txt  # Muestra solo la primera columna
  ```
  
  ---
- ### 🔹  **10. Comandos Útiles**
  
  ```
  whoami              # Muestra el usuario actual
  hostname            # Muestra el nombre del host
  date               # Muestra la fecha y hora
  uptime             # Tiempo de actividad del sistema
  df -h              # Espacio en disco
  du -sh carpeta     # Tamaño de una carpeta
  find . -name "*.sh" # Busca archivos con extensión .sh
  history            # Muestra historial de comandos
  ```
  
  ---