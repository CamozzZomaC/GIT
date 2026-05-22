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

# git checkout -> Me permite mover HEAD a cualquier commit anterior al último, de ese modo entramos en estado "detached". Detached significa que no estamos en una rama, sino que estamos en un commit específico. En este estado, cualquier cambio que hagamos no se guardará en ninguna rama, por lo que es importante tener cuidado al hacer cambios en este estado.

>git checkout + hash del commit -> Mueve HEAD a ese commit específico, entrando en estado "detached".

# git reset -> Permite mover HEAD a un commit específico, pero a diferencia de git checkout, git reset también mueve la rama actual para que apunte al commit al que se ha movido HEAD. Esto significa que cualquier cambio que hayas hecho después del commit al que te has movido se perderá, ya que la rama actual ahora apunta a un commit anterior. Es importante tener cuidado al usar git reset, ya que puede resultar en la pérdida de trabajo si no se usa correctamente.

>git reset + hash del commit -> Mueve HEAD y la rama actual a ese commit específico, perdiendo cualquier cambio posterior a ese commit.

