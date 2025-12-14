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