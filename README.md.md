# Comandos básicos de git
Fundamentos
-----

* git init: inicial repositorio
* git config --global user.name "nombre del usuario" configurar el usuario
    * git config --global user.email "nombre del usuario"
* git status: ver el estado del repositorio
* git add .: agrega todos los cambios que se han hecho
* git clean -fdx : borrar todo lo que no este en seguimiento
* git checkout -- . : se devuelve al ultimo commit realizado
* git reset  nombre del archivo: quita un archivo del stage
* git reset HEAD nombre del archivvo : elimina el archivo del stage
* git add "*.txt" agrega todos los txt que se modificaron
* git add *.txt agrega todos los txt
* git add "lista de archivos" lista de archivos
* git add pdfs/*.pdf agrega todos los pdf en la carpeta pdfs
* git add pdfs/ agrega todos los archivos de la carpeta pdfs
* git commit -m "mensaje": crear un scream shot 
* git checkout -- Nombre del archivo: devuelve el ultimo commit realizado
* git log: mirar los cambios que se han hecho desde que se inicio el proyecto
* git config --global alias.lg "log --oneline --decorate --all --graph" : mirar los cambios de forma mas bonita
* git config --global alias.s "status -s -b": mirar el estado de forma mas bonita en un alias 
* git commit -- amend -m "Actualizamos el readme" : actualiza el mensaje del ultimo commit
* git reset --soft 1763fac : se devuelve a un punto para poder editar
* git reset --hard a698930 : se para en el punto y elimina las posteriores modificaciones realizadas
* git reflog : muestra todo el registro del repositorio
* git mv 'nombre viejo' 'nombre nuevo' : modificar el nombre de un archivo desde git
* git rm nombre del archivo : Elimina el archivo 
* git add -u : actualiza todo el stash

.gitignore
-------
* *.extención : elimina del seguimiento todo los archivos de esa extención
* nombre del directorio/ : elimina del seguimiento ese directorio

Ramas
------
* git branch nombre-rama : crear ramas
* git branch : muestra las ramas creadas
* git checkout nombre-rama : selecciona la rama creada
* git merge nombre-rama a unir : une las dor ramas, hay que estar parado en la rama maestra fast forward
* git branch -d nombre-rama : elimina las ramas

Tags
-----
* git tag nombre del tag : crea tags
* git tag -d nombre del tag : Elimina tags
* git tag : muestra todos los tags crados
* git tag -a v1.0.0 -m "Versión 1.0.0" : crea tag mas específicos
* git tag -a v0.1.0 345d7de -m "comentario" : crea tag en un punto diferente
* git show v0.1.0 : muestra la información del tag
* Orden de los tags
    * v1.0.0
    * Mayor.menor.parche

stash
------
Guarda cambios temporalmente para hacer cambio importantes y despues seguir trabajando con estos cambios
* git stash : crea un stash con lo que no este en el commit
* git stash list : lista todos los stash
* git stash pop : extrae el ultimo elemento del stash y lo elimina
* git stash drop : elimina el ultimo stash
* git stash save : guarda lo que tenemos en el stash
* git stash apply : toma la ultima entrada y lo restaura
* git stash apply ID stash : restaura el stash del ID
* git stash save --keep-index : Guarda todo menos los archivos en el stage o en el escenario
* git stash save --include-untracked : Incluye todo los archivos junto a los que git no le da seguimiento
* git stash list --stat : aparece mas información de los stash creados
* git show stash : Muestra la información de los cambios que se hicieron en el stash
* git show stash@{0} : Muestra la información de los cambios que se hicieron en el stash espesifico 
* git stash save "comentario" : crea el stash con un comentario
* git stash clear : borra todos los stash y no hay forma de recuperarlos

rebase
-------
* git rebase master : sirve para actualizar el punto donde se crea la rama y tomar los cambios de los commit posteriores a la creacion de la rama en la que estamos parados
* git rebase -i HEAD~numerode commits : crea un rebase interactivo de los últimos numero de comits commits
    * Ordenar commits
    * Corregir mensajes de los commits
    * Unir commits
    * Separar commits
* git reset HEAD^ revierte los cambios del ultimo commit

git hub
-----
* git remote add origin https://... :  crea un repositorio remoto con el nombre origen en la dirección https
* git remote -v : muestra todos los repositorios remotos creados
* git push -u origin master : 
    * -u : pone la rama como predeterminada
    * origin : nombre del repositorio
    * master : tama que queremos subir o hacer push
* guardar la contraseña
    * git config --global credential.helper wincred -> Windows
    * https://help.github.com/en/github/using-git/caching-your-github-password-in-git#platform-linux -> Linux
* git push --tags : sube todos los tags que tenemos
* git pull : Descarga el repositorio de git 
* git clone URL nombre que queremos : clona todo el repositorio en el computador
* git fetch : descarga la diferencia entre github y el repositorio
* git pull --all : se actuliza con todas las ramas que hay en el repositorio
* git branch -a : muestra todas las ramas incluyendo las remotas
* git branch :rama a borrar : borra la rama directamente del repositorio remoto
    * git push origin : rama a borrar
* git remote prune origin : Borra todas las ramas locales, que ya no existan en el remote

Issues
--------
Los issues no solo sirven para resolver problemas, se pueden hacer requeriemientos y muchas mas cosas, los titulos deben ser muy descriptivos

si tenemos un isue abirto podemos hacer referencia y cerrarlo con un commit -m "comentario [fixes, closes, resolves] clo #del issue"

Label totalmente personalizables 

MileStone
------
Son grupos de issues, caracteristicas o una fecha dentro de un periode de tiempo

Wikis
------

Proyectos
------
-[] se crean listas 

Pages
-------
si se quiere poner la pagina en una rama aparte, crear esa rama con este nombre gh-pages 
