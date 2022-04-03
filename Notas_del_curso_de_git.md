# Mis pasos a seguir

    git config -l
    git config --global user.name "dczinil@'star wars planet'"
    git config --global user.mail <dczinil@gmail.com>

#### Linux

    ssh-keygen -t ed25519 -C “dczinil@gmail.com”
    ssh-key -t rsa -b 4096 -C <dczinil@gmail.com>
    eval "$(ssh-agent -s)"
    install xclip
    xclip -selection clipboard < /.ssh/id_rsa.pub

### Windows

    ssh-keygen -t ed25519 -C “dczinil@gmail.com”
    ssh-keygen -t rsa -b 4096 -C <dczinil@gmail.com>
    clip < <url/ed25519.pub>

### Como iniciar bajar un repositorio de github

    git init
    git add <url>
    git commit -m "Comentarios"
    git remote add <url>
    git pull origin master

### Nuevo repositorio en la línea de comando

    echo "# aprendiendo_git" >> README.md
    git init
    git add README.md
    git commit -m "first commit"
    git branch -M <main o master>
    git remote add origin [https://github.com/dczinil/]<repositorio.git>
    git push -u origin <main o master>

### Inserte un repositorio existente desde la línea de comando

    git remote add origin [https://github.com/dczinil/]<repositorio.git>
    git branch -M <main o master>
    git push -u origin <main o master>

### Se realiza sta comando para iniciar "git" en la carpeta que se encuenta la terminal.

    git init

### Para tener una referencia de quién realiza los cambios agregamos.

Con este diferenciador se configuran los cambios de forma globla para todos los repositorios que se utilicen.

    git config --global

Con este diferenciador se configuran los cambios unicamente en ese repositorio.

    git config --local

Para revisar lo que tenemos configurado en git.

    git config -l

Para agregar el nombre a la configuracióon.

    git config --global users.name "<Nombre del usuario>"

Para agregar el correo a la configuración.

    git config --global user.email <elcorreo@mail.com>

### Es para agregar los archivos en el seguimiento. Agregando el ".", se le da seguimiento a todos los archivos en esa carpeta.

    git add <Url Archivos>

### Para eliminar del seguimiento.

    git rm <Url Archivo>

Borrar de la cache -->

    git rm <Url Archivo> --cache

### Con este comando se genera el historial de versiones, siempre hay que agregar algún comentario para saber qué fue lo que se modificó. Si se le agrega el nombre del archivo al fina solo se modificara este.

    git commit -m "Comentarios"

Agrega al commit todos los comentarios sin pasar por el "git add ...", solo aplica para los archivos que no son recien creados.

git commit -am "Comentarios"

### Para ver el historico de los eventos de git se realiza. 

    git log

Revisas que cambios se han hecho a cada archivo.

    git log --stat

Para ver un los commit un poco más graficos.

    git log --all --graph 

Para ver los commit enun entorno aun más grafico y compacto.

    git log --all --graph --decorate --oneline

### Linux

    alias arbolitogit="git log --all --graph --decorate --oneline"

### Para ver el historico de un archivo es con el comando

    git show <Nombre del archivo>

```
El diff muestra las cambios que se han hecho en forma de historial a, b, c...
"@@...@@" nos indica cuantos bytes han cambiado entre versiones.
Nos muestra las líneas que han cambiado.
```

### Para ver las diferencias entre las versiones del archivo se usa; diff, utilizando los codigo de commit "c8b00e3ed48..." "1c2bb004d70...", regresara la diferencia entre el primer commit y el utimo agregado

    git diff <CommitHash>

### Para realizar un reset y regresar a los archivos se usa el comando "git reset" utilizado el codigo commit al que se quiere regresar. Hay dos tipos de reset "Hard" y "Soft"; Hard regresa a la version mencionada y todo aquel que este en transito es eliminado. Con soft se regresa a la versión requerida pero permanece los archivos en transito.

    git reset <CommitHash> --soft

### Para regresar aun archivo a un tiempo anterior lo realizamos con "'checkout' 'el codigo del commit' 'nombre del archivo'", si se quiere volver permanente hay que realizar un commit antes de regresar a la nueva versión.

    git checkout

Para regresar a la versión actual nuevamente es con <checkout master 'nombre del archivo'"

    git checkout <CommitHash>

Para cambiar entre ramas

    git checkuot <nombre de la rama>

### Para mandar los datos al repositorio remoto se utiliza el complemento 'push'

    git push -u origin <main o master>

Eliminar ramas de repositorios remotos.

    git push origin :<Nombre de la rama>

Enviar ramas a el repositorio remoto.

    git push origin <Nombre de la rama>

### Para traer los datos del repositorio en la nube alrepositorio local si carlos a mis archivos "Tenerlos en memoria cache".

    git fetch

### Une los archivos con los de una rama o nube (posterior a un "fetch"). El merge al unir las ramas se ejecuta desde la rama a la que se le quiere traer las cosas de las demás, lo comun es traer las cosas de las demás ramas a la "Master, Main

Para unir ramas

    git merge

Cuando existe un conflicto. aparecen estos comentarios en el codigo:

![image text](https://www.jorgeacortes.com/blog/wp-content/uploads/2019/01/merge-conflict-solve-vs-code.gif)

https://www.jorgeacortes.com


VSCODE indica conque versión del conflicto te quieres quedar. En otros editores podría ser manual el realizar esta selección, por lo que lo podrías hacer manual.

- Guardar archivo
- Hay que volver hacer commit

Para abortar un merge o revertir hay que invocar.

    git merge --abort

### Para generar una nueva rama

    git branch <nombre de la rama>

Para borrar una rama.</p>

    git branch -d <Nombre de la rama>

Forzar el barrar rama. Tal ves se necesite forzar en caso de que la rama tenga trabaos sin fusionar.

    git branch -D <Nombre de la rama>

Nos muestra el historial de todas las ramas a detalle

    git show-branch --all

### Para poder clonar un repositorio de un servidor remoto se utiliza el diferenciador 'clone' lo más comun es utilizar de servicios como 'github' y 'gitlab'.

    git clone url

### Guardar el repositorio en la nube (GitHub, GitLab, etc.).

    git remote add origin "url"

Para verificar que la url se haya guardado correctamente.

    git remote
    git remote -v

### Para bajar la información de un repositorio remoto se utiliza el comando "pull", para evitar mandar los dos comandos "fetch y merge"

    git pull origin master --allow-unrelated-histories

### Generar un tag, este se utiliza para revisar las versiones de un proyecto. Se necesita un hash al que se le va aplicar este. #NOTE Los tag no son cambios. 

    git tag -a <Nombre del tag, lo comun 'v0.1'> -m "Comentarios sobre el tag" <Hash>

Para mostrar los tag que se tienen.

    git tag

Para saber a que commit o a que tag esta conectado cada tag.

    git show-ref --tags

Eviar los tag a la nube de repositorios se utliza.

    git push origin --tags

Eliminar tag #NOTE no se eliminan en la nube de git y esto es porque se pueden utilizar como release.

    git -d <Nombre del tag>

Eliminar tag de forma definitiva en la nube de git.

    git push origin :refs/tags/<Nombre del tag>

<<<<<<< Updated upstream
### Muestra de forma grafica en una nueva ventana el historial completo de git
=======
### .gitignore - Lo descrito en este archivo se ignora para no subir se a los repositorios locales o remotos

Se genera un archivo es impresindible que se llame <.gitignore> dentro del el va una lista de los archivos que se van a ignorar.</br>
    *.jpg
    *.log
    *.bak
    ´url_del_archivo´

Al finalizar hay que agregar lo al repositorio de forma normal a staging y posterior commit

    git add .gitignore
    git commit -m "Comentarios"

### Rebase - 'Es una mala practica', sobre escribe los repositorios por lo que si se llega a utilizar es importante que solo se use en el entorn local, la rama que se va unir no deberia de estar en el repositorio remoto solo en el localhost.

- Se debe de tener cuidado, dado que sobrescribe la historia del proyecto ocaciona varios conflictos cuando hay que hacer release.
- No quedan historial de los cambios originales.
- No se sabe el autor real de los commit.
- Si la rama principal avanzó varios commit puede generar varios conflictos que se tienen que corregir de forma manual.
- Rebase rimero a la rama que cambia (o que se va a eliminar), despues a la rama que va a qpermanecer.

### stash - Funsiona para poder ocultar momentanimente el trabajo y que git no los rastrie, trabajo en staging como el que no esta. Pero no estara guardado en ningun lugar.

Mando todos los archivos sin seguimiento a la memoria cache.</br>
    git stash

Para guardar los archivos que estan en staging.</br>
    git stash -u

Aun que stash te permite guardar los archivos sin mensaje la mejor practica es agregar un mensaje para tener contexto.</br>
    git stash save "mensaje"</br>
Dado que se pueden agregar parios archivos existe una forma de elistarlos.</br>
    git stash list
        stash@{0}: ...

Para visualizar las diferncias.</br>
    git stash show

Para ver las diferencias completas hay que agregar.</br>
    git stash show -p

Con el diferencial puede sacar todos los archivos en stash a la rama actual. Por defectostash lanzara el ultimo agregado.</br>
    git stash pop

Para lanzar un stash especifico hay que saber primero su identificador con 'list'.</br>
    git stash pop 'StashIdentificador'

Si tus cambios de stash ocacionan conflicto con tus ramas actuales, se puede generar un rama y agregar aplicar los cambios en esta.</br>
    git stash branch 'nombre de la rama' 'StashIdentificador'

Para aplicar los cambios en la rama que se encuentra.</br>
    git stash apply 

Si ya no requieres el stash puedes eliminar lo.</br>
    git stash drop 'StashIdentificador'

Para eliminar todos los stash.</br>
    git stash clear

### clean - 

  

### cherry-pick - 
>>>>>>> Stashed changes

    gitk

### Entorno de trabajo

En un entorno de trabajo la rama master esta bloqueada para pasar a ella hay que hace un <code review>, si pasa todas las pruebas se realiza un <pull request> al servidor de pruebas llamado <Staging develop>. Despues de verificar que no hay errores se realizar otro <pull request> (Esto solo es una caracteristica de GitHub), alos servidores d eproducción.

El equivalente a <Pull request> en Bitbuket {Pull Request}, GitLab {Merge Request} -->
```mermaid
graph LR
A[Flujo de trabajo]-->B[(Ramas trabajo)]--Pull Request-->D([Staging  develo])--Pull Request-->F([Rama master])
```

DeVops Es quienrealiza los pull reques quien se encarga que los trabajos de los developers se vulevan más faciles

### .gitignore

Se genera un archivo es impresindible que se llame <.gitignore> dentro del el va una lista de los archivos que se van a ignorar.

Al finalizar hay que agregar lo al repositorio de forma normal a staging y posterior commit

    git add .gitignore
    git commit -m "Comentarios"

### Markdown

La importanciía de tener un readme en la raíz de tu repositorio es para que puedan leer de que se trata y quienes pueden y como pueden contribuir. Hay paginas que te ayudan a editar lo.[https://pandao.github.io/editor.md/en.html]

### Rebase <Es una mala practica>, sobre escribe los repositorios por lo que si se llega a utilizar es importante que solo se use en el entorn local, la rama que se va unir no deberia de estar en el repositorio remoto solo en el localhost.

- Se debe de tener cuidado, dado que sobrescribe la historia del proyecto ocaciona varios conflictos cuando hay que hacer release.
- No quedan historial de los cambios originales.
- No se sabe el autor real de los commit.
- Si la rama principal avanzó varios commit puede generar varios conflictos que se tienen que corregir de forma manual.
- Rebase rimero a la rama que cambia (o que se va a eliminar), despues a la rama que va a qpermanecer.