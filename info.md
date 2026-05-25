# git init

0. git init -> Inicializa un nuevo repositorio de Git en el directorio actual, creando una estructura de archivos y carpetas necesarias para que Git pueda rastrear los cambios en ese directorio. Esto crea .git en el directorio actual, lo que indica que ese directorio ahora es un repositorio de Git.

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
7. git checkout -b + nombre de la rama -> Mover HEAD a una rama específica para trabajar en esa rama. (sustituye git branch + nombre de la rama).
8. git merge + nombre de la rama -> Combinar los cambios de una rama con otra, pero cuál se mergea con cuál? La rama que se mergea es la rama actual, es decir, la rama en la que estás trabajando. Por ejemplo, si estás en la rama "feature" y quieres fusionar los cambios de la rama "main", debes hacer git merge main mientras estás en la rama "feature".*
*8b. GIT REBASE
git rebase es una alternativa a git merge para combinar cambios de una rama con otra. En lugar de crear un nuevo commit de fusión, git rebase toma los commits de la rama que estás rebasing y los aplica uno por uno sobre la rama base. Esto puede resultar en un historial de commits más limpio y lineal, pero también puede ser más complicado de usar y puede causar problemas si no se usa correctamente. Es importante tener cuidado al usar git rebase, especialmente si estás trabajando en un equipo, ya que puede resultar en conflictos de fusión y pérdida de trabajo si no se usa correctamente.

GITHUB
9. git remote add origin + URL del repositorio -> Agregar un repositorio remoto en GitHub, lo que permite que puedas subir tus cambios locales a ese repositorio remoto y colaborar con otros desarrolladores en el proyecto. El comando git remote add origin establece una conexión entre tu repositorio local y el repositorio remoto en GitHub. Add origin 

>git remote add origin + URL del repositorio

10. git push origin + nombre de la rama -> Subir los cambios locales a un repositorio remoto en GitHub, permitiendo que otros colaboradores puedan acceder a esos cambios y colaborar en el proyecto. Esto solo se hace la primera vez que se sube una rama nueva, después de eso, ya no es necesario usar -u porque la relación entre la rama local y la rama remota ya está establecida. Normalmente en este punto origin siempre sera main, pues es el primer push (Initial commit).

>git push -u origin + nombre de la rama (main)

En realidad, se pone push -u origin + nombre de rama (feature/x) cuando se hace el primer push a una rama nueva, es decir, cuando se hace el primer push después de crear la rama. Esto establece la relación entre la rama local y la rama remota, lo que permite que en los siguientes pushes a esa misma rama ya no sea necesario usar -u, ya que la relación entre la rama local y la rama remota ya está establecida. Esto se llama tracking branch, y permite que git push y git pull funcionen sin necesidad de especificar el nombre del repositorio remoto y la rama cada vez.

11. Crear un pull request en GitHub -> Solicitar que los cambios realizados en una rama específica sean revisados y fusionados con la rama principal del proyecto, facilitando la colaboración y revisión de código entre los miembros del equipo. Es la pull requet la que hace merge, no el comando git merge. El comando git merge se utiliza para fusionar ramas localmente en tu repositorio, mientras que la pull request es una solicitud para que los cambios realizados en una rama sean revisados y fusionados con la rama principal del proyecto en GitHub.

## FLUJO DE TRABAJO "DIARIO"
1. git pull -> Obtener los cambios más recientes del repositorio remoto en GitHub y fusionarlos con tu rama local, asegurando que tu trabajo esté actualizado con los cambios realizados por otros colaboradores antes de comenzar a trabajar en nuevas características o correcciones de errores.
Pull por debajo está haciendo un fetch + merge, es decir, primero obtiene los cambios del repositorio remoto y luego los fusiona con tu rama local. Es importante hacer un pull antes de comenzar a trabajar en nuevas características o correcciones de errores para asegurarte de que estás trabajando con la versión más reciente del código y evitar conflictos de fusión más adelante.

2. git push -> Subir los cambios locales al repositorio remoto en GitHub, permitiendo que otros colaboradores puedan acceder a esos cambios y colaborar en el proyecto (no se pone -u origin +nombre de rama porque ya se ha hecho el push -u anteriormente, cuándo? El primer push que se hace a una rama nueva, es decir, el primer push después de crear la rama, se debe hacer con -u para establecer la relación entre la rama local y la rama remota. Después de ese primer push, ya no es necesario usar -u en los siguientes pushes a esa misma rama, ya que la relación entre la rama local y la rama remota ya está establecida).

3. Y cada x tiempo conviene volver a hacer un git pull para asegurarte de que tu trabajo esté actualizado con los cambios realizados por otros colaboradores. Esto va cambiando el origin/main al commit más reciente.

