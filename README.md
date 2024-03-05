Este repositorio lo use para aprender los comnados de Github
El resumen es el siguiente

CURSO GIT Y GITHUB

♦♦♦♦♦♦♦CONFIGURACIÓN♦♦♦♦♦♦♦♦
► git --version | Ver la version instalada
► git -h | Ayuda de git.
► git config --global user.name "(NombreUsuario)" | Es para configurar el nombre del usuario ligado al git
► git config --global user.email "(CorreoUsuario)" | Es para configurar el correo del usuario (Son obligatorios para utilizar git)

♦♦♦♦♦♦♦USO DE GIT♦♦♦♦♦♦♦♦
► git init | Inicializar git en una carpeta
► git status | Verificar los cambios de la fotografia anterior
► git add (Nombre archivo.ext) | Agregar archivos a una version del proyecto
► git commit -m "mensaje" | confirma la version con fotos, si es la primera vez se inicia el arbol.
► git log | Muestra los commits realizados en el proyecto (las fotografias del proyecto)
► git checkout (Nombre archivo) | Para recuperar el archivo original de la ultima foto tomada
► git reset | Enlista los archivos que no se han recuperado de la ultima fotografia - para hacerle el git checkout (Nombre del listado de git reset)
► git log --graph | Muestra los logs en forma de rama
► git log --graph --pretty=oneline | Muestra los logs como una sola linea
► git log --graph --decorate --all --oneline | Aun mas resumido
► git config --global alias.tree "log --graph --decorate --all --oneline" | Generar alias de comandos de git lo que esta "comando para el alias sin git" lias."nombre de alias"
► "Git ignore" | Crear un archivo que se llama .gitignore en la carpeta del proyecto y colocar los archivos que se requieran ignorar la nomenclatura es  **"Ruta del archivo con ext" git add y git commit para agregar el archivo
► git diff | Muestra los cambios realizados entre la ultima fotografia y los cambios sin fotografiar.
► git checkout (has) | Es para cambiar a una fotografia en particular este has aparece con git log, es necesario no tener cambios actualmente y se tiene se debe de tomar una fotografia. o un reset del mismo
► git checkout HEAD | Para que donde regresamos que esta sea el principal, para regresar se debe de poner el codigo del ultimo commit en el checkout 
► git reset --hard (has) | Es para regresar a una fotografia eliminando las posteriores en el log 
► git reflog | Para mostrar el historial completo de interacciones en el git
► git tag nombre_1 | es para colocar etiquetas en los commits para identificar los puntos de avance en el historico general
► git tag | Para mostrar todos los tags que hemos escrito
► git checkout tags/(nombre tag) | para movernos entre las versiones de tags

♦♦♦♦♦♦♦RAMAS O BRANCH ♦♦♦♦♦♦♦♦
Cuando se necesita trabajar en distintas ramas. por ejemplo una funcionalidad no afectando a la rama principal
► git branch (nombrerama) | Para crear nuevas ramas de la rama principal
► git switch (nombrerama) | Para cambiar de rama en caso en una diferente
► git merge MAIN | Se hace un merge desde MAin a RamaNueva, osea se trae los cambios que tiene Main a ramaNueva, aqui pueden haber conflictos
► git stash | es para guardar sin hacer commit
► git stash list | Muestra todos los stash que se han realizado
► git stash pop | Te da el estado en la cual dejaste el stash
► git stash drop | Elimina el stash que tienes para dejarte como lo dejaste.
► git branch -d (Nombrerama) | Para eliminar una rama cuando ya se termino

♦♦♦♦♦♦♦CONEXION SSH GITHUB♦♦♦♦♦♦♦♦
► "Documentacion" | https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent

► ls al ~/.ssh | Enlista los SSH que ya se tengan.
► ssh-keygen -t ed25519 -C "(Tu correo github)" | Se genera el key de ssh para la configuracion, Pide si la ruta es la correcta o hay que cambiarla, pide si hay que agregarle una contraseña si no se deja vacio, pide confirmar la contraseña
► Get-Service -Name ssh-agent | Set-Service -StartupType Manual | Se debe ejecutar con un permisos de administrador para iniciar el agente SSH en segundo plano
► Start-Service ssh-agent | Se debe ejecutar con un permisos de administrador Para iniciar el servicio de SSH 
► ssh-add c:/Users/(USUARIO)/.ssh/id_ed25519 | Se agrega el ssh con el nombre que se ha creado.

♦♦♦♦♦♦♦GIT HUB♦♦♦♦♦♦♦♦
Funciona cuando es tu repositorio y cuando estas invitado a ese repositorio

Crear Repositorio en Github y alli viene la ruta
► git clone https://github.com/mfloress02/pagina-blue.git | Es para clonar un repositorio a tu maquina debes de ser dueño o estar como invitado.
► git remote add origin https://github.com/Poncho150996/Pruebas.git | Ligar el repositorio github con el local
► git push -u origin main | Para subir inicialmente nuestro proyecto a github (main es el nombre de la rama pricipal)
► git push | Es para subir los cambios a github por que ya sabe el origen, puede mandar error cuando no esta completamente actualizado.
► git fetch | Nos trae el historial de cambios sin descargarse los cambios
► git pull | Se descargan los cambios desde git a local en caso de no tener conflito. si marca error hay que especificar el tipo de pull
► git config pull.rebase false | Para que se configure el tipo de pull que se realizara false = merge, true rebase, ff only fast-forward only
► git pull origin master | Se puede especifica de donde debe de descargar los cambios, hay que agregar el mensaje de merge.

♦♦♦♦♦♦♦COLABORAR EN UN REPOSITORIO INDEPENDIENTE♦♦♦♦♦♦♦♦
Es necesario hacer un branch del repositorio a colaborar ya que no tenemos los permisos de escribir en ese repositorio

► Realizar un FORK | Es un clon del repositorio pero a tu repositorio, y despues puede aplicar todo de la seccion de GitHub por que esta en tu repositorio
► Revisar la Sync Fork | Ya que es necesario estar sincronizado primero del Repo original hacia el fork de nuestro repositorio
► Contribuir con un Pull Request "PR" | Esto es para mandar una solicitud de integracion al repositorio original, puede mandarse a una rama interna tambien de ese repositorio
► Esperar autorizacion de PR | Se debe de esperar la autorizacion de estas solicitudes de cambios

► Cuando eres revisor | Hay una seccion en el repositorio llamado Pull Request y puedes aceptar o rechazar dejando el comentario.

► Conflictos.| Son codigos que afectan a otros entre ramas, repositorios, al momento de hacer merge.
