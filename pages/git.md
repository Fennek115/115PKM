- Configuración inicial:
	- ```bash
	  git config
	  # configurar el user
	  git config --global user.name "nombre"
	  # configurar el mail
	  git config --global user.mail "name@mail.com"
	  ```
- Para empezar:
	- ```bash
	  # iniciar un git
	  git init
	  ```
- como crear ramas
	- ```bash
	  # para que las ramas que se creen por defecto sean main y no master
	  git config --global init.defautBranch main
	  # para cambiar el nombre de la rama main
	  git branch -m main
	  ```
- trabajando con git
	- ```bash
	  # para comprobar
	  git status
	  # para añadir los archivos
	  git add <el archivo>
	  # para hacer el comit y agregar un mensaje
	  git commit -m "un commit zzz"
	  # para ver los logs
	  git log
	  ```
- volver a versiones anteriores
	- ```bash
	  # volver a una version anterior
	  git checkout <archivo>
	  # volver a la ultima version completa
	  git reset
	  # para revisar el historial de commits
	  git log --graph
	  # vista rapida de los ultimos 3 commits
	  git log --graph --pretty=oneline
	  ```
	-