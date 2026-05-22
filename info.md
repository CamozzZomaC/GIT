1. git status -> No commits yet

2. git add

3. git status -> Changes to be commited

¿QUÉ ES HEAD?
HEAD es un puntero que apunta al último commit realizado en la rama actual. Es decir, HEAD siempre apunta al commit más reciente en la rama en la que estás trabajando. Cuando haces un nuevo commit, HEAD se mueve para apuntar a ese nuevo commit. Si haces checkout a una rama diferente, HEAD se moverá para apuntar al último commit de esa rama. En resumen, HEAD es una referencia que indica el estado actual de tu repositorio y te permite navegar por el historial de commits.


# git cat-file -t + hash del commit -> Muestra el tipo de commit:

    bloob = fichero
    tree = folder

# git cat-file -p + hash del commit -> Muestra commit & hash, autor

# git log -> Ver el historial de commits + hashes de los commits

# git checkout -> Me permite mover HEAD a cualquier commit anterior al último, de ese modo entramos en estado "detached". Detached significa que no estamos en una rama, sino que estamos en un commit específico. En este estado, cualquier cambio que hagamos no se guardará en ninguna rama, por lo que es importante tener cuidado al hacer cambios en este estado.

    - git checkout + hash del commit -> Mueve HEAD a ese commit específico, entrando en estado "detached".

# git reset -> Permite mover HEAD a un commit específico, pero a diferencia de git checkout, git reset también mueve la rama actual para que apunte al commit al que se ha movido HEAD. Esto significa que cualquier cambio que hayas hecho después del commit al que te has movido se perderá, ya que la rama actual ahora apunta a un commit anterior. Es importante tener cuidado al usar git reset, ya que puede resultar en la pérdida de trabajo si no se usa correctamente.

    - git reset + hash del commit -> Mueve HEAD y la rama actual a ese commit específico, perdiendo cualquier cambio posterior a ese commit.

