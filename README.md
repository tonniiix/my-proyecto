
<center>

# TÍTULO DE LA PRÁCTICA


</center>

***Antonio:***
***1ºDAW:*** 

### ÍNDICE

+ [Introducción](#id1)
+ [Objetivos](#id2)
+ [Material empleado](#id3)
+ [Desarrollo](#id4)
+ [Conclusiones](#id5)


#### ***Introducción***. <a name="id1"></a>

"Esta práctica consiste en el flujo de trabajo fundamental de Git y GitHub. Empezaremos desde clonar un repositorio y hacer los commits iniciales, hasta la gestión de archivos ignorados (.gitignore), trabajar con ramas (branch), sobre todo fusionar el código (merge).

#### ***Objetivos***. <a name="id2"></a>

Los objetivos principales de esta práctica son:

- Crear y clonar un repositorio de GitHub.

- Dominar el flujo de trabajo básico de Git: add, commit y push.

- Aprender a gestionar y excluir archivos mediante .gitignore.

- Utilizar tags para marcar versiones específicas.

- Comprender y aplicar el concepto de ramas (branchs) para el desarrollo de nuevas características o funcionalidades.

- Realizar fusiones (merges) y aprender a resolver conflictos cuando se producen.

#### ***Material empleado***. <a name="id3"></a>

1. Máquina virtual
2. Terminal (para usar comandos)
3. Captura de pantalla
4. Linux
5. Github 

#### ***Desarrollo***. <a name="id4"></a>

- ***Creamos el repositorio*** 

![Mi Foto](img/crear-repo.png)


- ***Clona el repositorio remoto vacío en el equipo local***

```git clone git@github.com:alumno-XXX/my-proyecto-millonario.git```
- ***Acceder a la carpeta del proyecto***

```cd my-proyecto-millonario```
- ***Crear el archivo de documentación***

```touch README.md```
- ***Añade los cambios (README.md) al staging area***

```git add .```
- ***Confirma los cambios con el mensaje***

```git commit -m "commit inicial"```
- ***Sube los cambios al repositorio remoto***

```git push origin masater```

- ***Crea un fichero sensible***

```touch privado.txt```
- ***Crea un directorio que no debe subir***

```mkdir privada```
- ***Añade la regla para ignorar el fichero***

```echo "privado.txt" >> .gitignore```
- ***Añade la regla para ignorar el directorio***

```echo "/privada" >> .gitignore```
- ***Añade el archivo .gitignore modificado al staging area***

```git add .```
- ***Confirma la adición del .gitignore***

```git commit -m "añadido fichero .gitignore"```
- ***Crea el fichero 1.txt***

```touch 1.txt```
- ***Añade el fichero 1.txt al staging area***

```git add .```
- ***Confirma la creación de 1.txt***

```git commit -m "añadido 1.txt"```
- ***Crea el tag local con el nombre v0.1 en el commit actual***

```git tag v0.1```
- ***Sube la rama y, específicamente, sube el tag recién creado al repositorio remoto***

```git push --tags origin master```
- ***Crea una rama nueva de desarrollo (local)***

```git branch v0.2```
- ***Cambia el directorio de trabajo (HEAD) a la nueva rama***

```git checkout v0.2```
- ***Crea un nuevo fichero 2.txt en esta rama***

```touch 2.txt```
- ***Añade 2.txt al staging area***

```git add .```
- ***Confirma la creación de 2.txt en la rama v0.2***

```git commit -m "añadido 2.txt"```
- ***Sube la rama v0.2 y sus cambios al repositorio remoto***

```git push origin v0.2```
- ***Vuelve a la rama principal***

```git checkout master```
- ***Fusiona los cambios de v0.2 (la adición de 2.txt) en master***

```git merge v0.2 -m "merge v0.2 sin conflictos"```
- ***Fusión merge con conflicto y resolución***

```bash
git checkout master
echo "Hola" >> 1.txt
git add .
git commit -m "hola en 1.txt"
git checkout v0.2
echo "Adios" >> 1.txt
git add .
git commit -m "adios en 1.txt"
git checkout master
git merge v0.2
nano 1.txt
git add .
```

- ***Eliminación de ramas***

```bash
git branch --merged
git branch --no-merged
git tag v0.2
git branch -d v0.2
```

- ***Cambios***

```bash
git config --global alias.list 'log --oneline --decorate --graph --all'
git list
```
#### ***Conclusiones***. <a name="id5"></a>

En esta parte debemos exponer las conclusiones que sacamos del desarrollo de la prácica.
