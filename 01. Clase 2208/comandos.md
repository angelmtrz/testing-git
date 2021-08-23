# Comandos git

## Crear un repositorio local
    git init

## Revisar el estado de los archivos
    git status

## Monitorear los archivos
    git add nombre_archivo.extension
    git add .

## Confirmar archivos
    git commit
    git commit -m "Mensaje de Commit"                 //usar esto de preferencia

## Listar Commits
    git log
    git log --oneline
    git log --pretty

## Agregar credenciales por proyecto y global
    git config user.name "Angel Marthans"
    git config user.email "angemtrz@gmail.com"
    git config --global user.name "Angel Marthans"
    git config --global user.email "angemtrz@gmail.com"

## Editar configuracion
    git config -e               //local
    git config --global -e      //global

## Moverse entre Commits
    git checkout identificador_de_commit
    git checkout 4e82a8         //primeros 6 caracteres del identificador 
    git checkout master

## MOverse a un commit usando posisciones relativas
    git checkout HEAD^   //tantos ^ como niveles de commits
    git checkout HEAD~   //regresa 1 commit
    git checkout HEAD~3  //regresa 3 commits

## Almacenamiento temporal
    git stash save "mensaje"
    git stash save "cambios en comandos.md"

## Para listar los stash
    git stash list

## Recuperar/devolver un stash
    git stash pop numero_de_stash
    git stash pop 0

## Eliminar un stash
    git stash drop numero_stash

## Crear una rama (Branch)
    git branch nombre_rama
    git branch interactividad

## Combinar ramas (fusion)
    git merge nombre_rama_para_merge
    git merge interactividad

## Crear rama y cambiar a esa rama
    git chekcout -b nombre_rama

## Reorganizar ramas (rebase)
    git rebase rama_con_cambios rama_master
    git rebase seo master

## Eliminar un commit (solo local, mientras q no se haya sicronizado con el repositorio remoto)
    git reset HEAD^       //eliminar el ultimo commit
    git reset --hard HEAD~5      //eliminar varios commits consecutivos hacia atras

## Eliminar un commit (cuando ya esta sicnronizado en el remoto - no elimina realmente)
    git revert HEAD  //confirmar mensaje de eliminacion, crea un commit para eliminar el anterior
    git rever --no-commit HEAD~6..HEAD     //eliminar commits desde el inicio hasta los 5 siguientes, queda el sexto como referencia... este comando crea 1 commit q elimina los 5 anteriores

## Mover commits especificos a la rama master
    git cherry-pick identificador_de_commit
    git cherry-pick b669b6

## Agregar Hitos o Etiquetas (tags)
    git tag "v1.0.0" 95ccff5e

## Agregar cambios al ultimo commit
    git commit --amend

## Clonar un repositorio remoto
    git clone url_del_repositorio

## Enviar commits de repo local a repo remota (Actualizar)
    git push

## OPCION 1
## Obtener/copiar commits remotos (Sincroniza commits) [paso 1]
    git fetch

## Actualizar archivos obtenidos con git fetch [paso 2]
    git merge origin/main

## OPCION 2
## Obtener commits remotos y actualizar archivos [alternativa a pasos 1 y 2]
    git pull

## Obtener/copiar commits de todas las ramas remotas
    git fetch --all

## OPCION 3
## Obtener/Copiar commits remotos
    git fetch
    git rebase repo_local repo_remota
    git rebase main origin/main

## OPCION 4
## Obtener/Copiar commits remotos
    git pull --rebase

## Vincular repo local con repo remoto
    git remote add origin https://github.com/angelmtrz/testing-git.git
    git branch -M main
    git push -u origin main