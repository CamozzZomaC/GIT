# git status -> Muestra el estado actual del repositorio, incluyendo los archivos que han sido modificados, los archivos que están en el área de staging y los archivos que no están siendo rastreados por Git.

1. git status -> No commits yet

# git add -> Agrega los cambios realizados a un archivo específico al área de staging, lo que significa que esos cambios están listos para ser incluidos en el próximo commit.

2. git add

3. git status -> Changes to be commited

¿QUÉ ES HEAD?
HEAD es un puntero que apunta al último commit realizado en la rama actual. Es decir, HEAD siempre apunta al commit más reciente en la rama en la que estás trabajando. Cuando haces un nuevo commit, HEAD se mueve para apuntar a ese nuevo commit. Si haces checkout a una rama diferente, HEAD se moverá para apuntar al último commit de esa rama. En resumen, HEAD es una referencia que indica el estado actual de tu repositorio y te permite navegar por el historial de commits.

# git commit -> Crea un nuevo commit con los cambios añadidos al área de staging (con git add). El commit incluye un mensaje que describe los cambios realizados.

>git commit -m "mensaje del commit" -> Crea un nuevo commit con el mensaje especificado.

# git cat-file -> Permite mostrar información sobre los objetos almacenados en el repositorio, como commits, árboles y blobs. Es una herramienta útil para explorar el historial de commits y entender cómo se organizan los objetos en Git.

>git cat-file -t + hash del commit -> Muestra el tipo de commit:   

    bloob = fichero
    tree = folder

>git cat-file -p + hash del commit -> Muestra commit & hash, autor

# git log -> Ver el historial de commits + hashes de los commits

# git reflog -> Muestra un registro de los movimientos de HEAD, incluyendo los commits a los que se ha movido HEAD. Es útil para recuperar commits perdidos o para entender el historial de cambios en el repositorio.

# git branch -> Muestra las ramas disponibles en el repositorio y la rama actual en la que estás trabajando. La rama actual se indica con un asterisco (*).

# git branch + nombre de la rama -> Crea una nueva rama con el nombre especificado.

# git checkout -> Me permite mover HEAD a cualquier commit anterior al último, de ese modo entramos en estado "detached". Detached significa que no estamos en una rama, sino que estamos en un commit específico. En este estado, cualquier cambio que hagamos no se guardará en ninguna rama, por lo que es importante tener cuidado al hacer cambios en este estado. Por esa razón checkout NUNCA se usa para moverse entre commits, sino entre ramas, por eso el comando correcto sería :

>git checkout + nombre de la rama -> Mueve HEAD a la rama especificada, permitiéndote trabajar en esa rama y realizar commits que se guardarán en esa rama.

>git checkout + hash del commit -> Mueve HEAD a ese commit específico, entrando en estado "detached". NUNCA

# git checkout -b -> Crea una nueva rama y mueve HEAD a esa nueva rama, permitiéndote trabajar en esa rama y realizar commits que se guardarán en esa rama.

# git reset -> Permite mover HEAD a un commit específico, pero a diferencia de git checkout, git reset también mueve la rama actual para que apunte al commit al que se ha movido HEAD. Esto significa que cualquier cambio que hayas hecho después del commit al que te has movido se perderá, ya que la rama actual ahora apunta a un commit anterior. Es importante tener cuidado al usar git reset, ya que puede resultar en la pérdida de trabajo si no se usa correctamente.

>git reset + hash del commit -> Mueve HEAD y la rama actual a ese commit específico, perdiendo cualquier cambio posterior a ese commit.

# git merge -> Permite combinar los cambios de una rama con otra. Cuando haces un merge, Git toma los cambios de la rama que estás fusionando y los aplica a la rama actual. Si hay conflictos entre los cambios, Git te pedirá que resuelvas esos conflictos antes de completar el merge.

## FLUJO DE TRABAJO
1. git status -> Ver el estado actual del repositorio.
2. git add -> Agregar los cambios realizados a un archivo específico al área de staging.
3. git commit -> Crear un nuevo commit con los cambios añadidos al área de staging.
4. git log -> Ver el historial de commits. (ocpcional).
5. git branch + nombre de la rama -> Crear una nueva rama para trabajar en una nueva característica o corrección de errores.
6. git branch -> Ver las ramas disponibles en el repositorio.
7. git checkout -b + nombre de la rama -> Mover HEAD a una rama específica para trabajar en esa rama. 
8. git merge + nombre de la rama -> Combinar los cambios de una rama con otra.

GITHUB

9. git push origin + nombre de la rama -> Subir los cambios locales a un repositorio remoto en GitHub, permitiendo que otros colaboradores puedan acceder a esos cambios y colaborar en el proyecto.
10. Crear un pull request en GitHub -> Solicitar que los cambios realizados en una rama específica sean revisados y fusionados con la rama principal del proyecto, facilitando la colaboración y revisión de código entre los miembros del equipo. Es la pull requet la que hace merge, no el comando git merge. El comando git merge se utiliza para fusionar ramas localmente en tu repositorio, mientras que la pull request es una solicitud para que los cambios realizados en una rama sean revisados y fusionados con la rama principal del proyecto en GitHub.
