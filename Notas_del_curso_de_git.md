# note Mis pasos a seguir
/n :~$ git config -l
/n :~$ git config --global user.name "dczinil@'star wars planet'"
/n :~$ git config --global user.mail "correo"
    <!-- Linux -->
:~$ ssh-keygen -t ed25519 -C “dczinil@gmail.com”
:~$ ssh-key -t rsa -b 4096 -C "dczinil@gmail.com"
:~$ eval "$(ssh-agent -s)"
:~$ install xclip
:~$ xclip -selection clipboard < ~/.ssh/id_rsa.pub
    <!-- Windows -->
~> ssh-keygen -t ed25519 -C “dczinil@gmail.com”
~> ssh-keygen -t rsa -b 4096 -C "dczinil@gmail.com"
~> clip < "url/ed25519.pub"
    <!-- Como iniciar bajar un repositorio de github -->
:~$ git init
:~$ git add "url"
:~$ git commit -m "Commentarios"
:~$ git remote add "url"
:~$  git pull origin master

# Nuevo repositorio en la línea de comando

:~$ echo "# aprendiendo_git" >> README.md
:~$ git init
:~$ git add README.md
:~$ git commit -m "first commit"
:~$ git branch -M "main o master"
:~$ git remote add origin https://github.com/dczinil/"repositorio.git"
:~$ git push -u origin "main o master"

# Inserte un repositorio existente desde la línea de comando

:~$ git remote add origin https://github.com/dczinil/"repositorio.git"
:~$ git branch -M "main o master"
:~$ git push -u origin "main o master"

.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-.-

# Se realiza sta comando para iniciar "git" en la carpeta que se encuenta la terminal.

:~$ git init

# Para tener una referencia de quién realiza los cambios agregamos. El diferenciador "--global", es para todos los repositorios en los que se trabaje, en cambio "--local", es para este entorno específico.
.
    <!-- Para revisar lo que tenemos configurado en git -->
:~$ git config -l
    <!-- Para agregar el nombre a la configuracióon, teneren cuanta "--global y --local" -->
:~$ git config --global users.name <<"Nombre del usuario"@>>
    <!-- Para agregar el correo a la configuración, teneren cuanta "--global y --local" -->
:~$ git config --global user.mail <<"elcorreo@mail.com">>

# Es para agregar los archivos en el seguimiento. Agregando el ".", se le da seguimiento a todos los archivos en esa carpeta.

:~$ git add "Archivos"

# Para eliminar del seguimiento.

:~$ git rm "Archivo"
    <!-- Borrar de la cache -->
:~$ git rm "Archivo" --cached

# Con este comando se genera el historial de versiones, siempre hay que agregar algún comentario para saber qué fue lo que se modificó. Si se le agrega el nombre del archivo al fina solo se modificara este. Si se agrega el parametro "-a" se manda todos los archivos en la carpeta posicionado.

:~$ git commit -m "Comentarios"
    <!-- Agrega al commit todos los comentarios sin pasar por el "gir add ...", solo aplica para los archivos que no son recien creados -->
:~$ gir commit -am "Comentarios"

# Para ver el historico de los eventos de git se realiza. 

:~$ git log
.
    <!-- Revisas que cambios se han hecho a cada archivo. -->
:~$ git log --stat
.
    <!-- Para ver un los commit un poco más graficos. -->
:~$ git log --all --graph 
.
    <!-- Para ver los commit enun entorno aun más grafico y compacto -->
:~$ git log --all --graph --decorate --oneline
.
    <!-- NOTE Linux  -->
:~$ alias arbolitogit="git log --all --graph --decorate --oneline"


# Para ver el historico de un archivo es con el comando

:~$ git show "Nombre del archivo"
    <!-- El diff muestra las cambios que se han hecho en forma de historial a, b, c...  -->
    <!-- "@@...@@" nos indica cuantos bytes han cambiado entre versiones -->
    <!-- Nos muestra las líneas que han cambiado -->

# Para ver las diferencias entre las versiones del archivo se usa; diff, utilizando los codigo de commit "c8b00e3ed48..." "1c2bb004d70...", regresara la diferencia entre el primer commit y el utimo agregado

:~$ git diff 1c2bb004d70103cae33e7d05f4f98357684e2cc4

# Para realizar un reset y regresar a los archivos se usa el comando "git reset" utilizado el codigo commit al que se quiere regresar. Hay dos tipos de reset "Hard" y "Soft"; Hard regresa a la version mencionada y todo aquel que este en transito es eliminado. Con soft se regresa a la versión requerida pero permanece los archivos en transito.

:~$ git reset 1c2bb004d70103cae33e7d05f4f98357684e2cc4 --soft

# Para regresar aun archivo a un tiempo anterior lo realizamos con "'checkout' 'el codigo del commit' 'nombre del archivo'", si se quiere volver permanente hay que realizar un commit antes de regresar a la nueva versión.

:~$ git checkout
    <!-- Para regresar a la versión actual nuevamente es con "'checkout' master 'nombre del archivo'" -->
:~$ git checkout 1c2bb004d70103cae33e7d05f4f98357684e2cc4 Notas_del_curso_de_git.txt
    <!-- Para cambiar entre ramas -->
:~$ git checkuot "nombre de la rama"

# Para mandar los datos al repositorio remoto se utiliza el complemento 'push'

:~$ git push -u origin "main o master"

# Para traer los datos del repositorio en la nube alrepositorio local si carlos a mis archivos "Tenerlos en memoria cache".

:~$ git fetch

# Une los archivos con los de una rama o nube (posterior a un "fetch"). El merge al unir las ramas se ejecuta desde la rama a la que se le quiere traer las cosas de las demás, lo comun es traer las cosas de las demás ramas a la "Master, Main

:~$ git merge
    <!-- Para unir las ramas -->
    <!-- Cuando existe un conflicto. aparecen estos comentarios en el codigo:
    # <<<<<<<HEAD
    # "Codigo con el que tiene confligto."
    # =======
    # >>>>>>>"nombre de la rama"
    # VSCODE indica conque versión del conflicto te quieres quedar.
    # En otros editores podría ser manual el borrar la parte que no quieres.
    # Guardar archivo
    # 
    # Hay que volver hacer commit
    -->
:~$ git merge "nombre de la rama"
    <!-- Para abortar un merge o revertir hay que invocar. -->
:~$ git merge --abort

# Para generar una nueva rama

:~$ git branch "nombre de la rama"
    <!-- Para borrar una rama. -->


# Para poder clonar un repositorio de un servidor remoto se utiliza el diferenciador 'clone' lo más comun es utilizar de servicios como 'github' y 'gitlab'.

:~$ git clone url

# Guardar el repositorio en la nube (GitHub, GitLab, etc.).

:~$ git remote add origin "url"
    <!-- Para verificar que la url se haya guardado correctamente. -->
:~$ git remote
:~$ git remote -v

# Para bajar la información de un repositorio remoto se utiliza el comando "pull", para evitar mandar los dos comandos "fetch y merge"

:~$ git pull origin master --allow-unrelated-histories

# Generar un tag, este se utiliza para revisar las versiones de un proyecto. Se necesita un hash al que se le va aplicar este. #NOTE Los tag no son cambios. 

:~$ git tag -a <Nombre del tag, lo comun 'v0.1'> -m "Comentarios sobre el tag" <Hash>
    <!-- Para mostrar los tag que se tienen -->
:~$ git tag
    <!-- Para saber a que commit o a que tag esta conectado cada tag -->
:~$ git show-ref --tags
    <!-- Eviar los tag a la nube de repositorios se utliza -->
:~$ git push origin --tags
    <!-- Eliminar tag #NOTE no se eliminan en la nube de git y esto es porque se pueden utilizar como release -->
:~$ git -d <Nombre del tag>
    <!-- Eliminar tag de forma definitiva en la nube de git -->
:~$ git push origin :refs/tags/<Nombre del tag>

