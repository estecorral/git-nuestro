- ¿Qué comando utilizaste en el paso 11? ¿Por qué?
git reset --hard HEAD~1
Se utilizo este comando para deshacer el ultimo commit que se habia hecho en
la rama styles, añadiendo el --hard para que se pierdan los cambios realizados
en el working copy, sin el --hard se mantendria nuestro Working copy.

- ¿Qué comando o comandos utilizaste en el paso 12? ¿Por qué?
git reflog - para buscar el commit en el que quiero recuperar, en este caso: 
1e749e9 HEAD@{1}: commit: Modifica git-nuestro.md con style

Por lo que en el siguiente paso aplico el comando:
git reset 1e749e9

Una vez que lo hemos realizado el archivo git-nuestro.md volvera a nuestro
Working area, por lo que tendremos que hacer un nuevo git add git-nuestro.md y un nuevo
commit. 
- El merge del paso 13, ¿Causó algún conflicto? ¿Por qué?
No causa ningún conflicto, simplemente nos indica el mensaje already up to date,
ya que la rama styled ya tiene el commit de la rama master. Si lo hiciesemos al contrario
si tendriamos cambios nuevos y master absorberia los cambios de la rama styled.

- El merge del paso 19, ¿Causó algún conflicto? ¿Por qué?
No hay conflitos, simplemente git nos indica "Merge made by the 'recursive strategy'" y 
la rama styled asimila los cambios realizados en la rama htmlify en un nuevo commit.
En este caso realiza un merge no Fast Fortward, porque la ramas no forman una lista.

- El merge del paso 21, ¿Causó algún conflicto? ¿Por qué?
En este caso no hay ningún conflicto, simplemente se hace un merge Fast Fordward,
sin crear un nuevo commit como en el caso anterior, ya que las ramas forman una lista

- ¿Qué comando o comandos utilizaste en el paso 25?
git log --graph

- El merge del paso 26, ¿Podría ser fast forward? ¿Por qué? 
Se usa el comando git merge --no-ff title estando en la rama master.
Si podria ser fast fordwar porque se en cuentran en lista y el ultimo commit
de la rama title aputaba al commit en el que se encuentra la rama master.

- ¿Qué comando o comandos utilizaste en el paso 27?
Utilize git reset HEAD~1 para volver al anterior commit manteniendo los cambios que 
tenemos en el working copy.

- ¿Qué comando o comandos utilizaste en el paso 28? 
git checkout -- git-nuestro.md lo que hace que se descarten los cambios del archivo
git-nuestro.md

- ¿Qué comando o comandos utilizaste en el paso 29? 
git branch -D title lo que elimina la rama title

- ¿Qué comando o comandos utilizaste en el paso 30? 
Hago un git reflog busco la referencia en la que se hizo el merge de master con title y
con git checkout b81e0b3 me muevo al commit de la rama que hemos eliminado, ahora me
encontraria en deached HEAD state. Por lo que con git branch title creo la rama y con git
checkout title me muevo a la rama para salir del detached HEAD y ya habria recuperado el merge

- ¿Qué comando o comandos usaste en el paso 32?
Uso un git reflog para buscar el commit inicial;
9d71d7a HEAD@{22}: commit (initial): Añade archivo git-nuestro.md
y moverme a el con git reset 9d71d7a

- ¿Qué comando o comandos usaste en el punto 33?
Hacemos un git reflog para buscar el commit:
da2b771 HEAD@{7}: commit: Añade título a git-nuestro.md
Y por ultimo con gir reset da2b771
