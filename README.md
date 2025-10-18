
<center>

# UT1-A3 Practicando Git


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


- ***Clonar repo y commit inicial***

```bash
git clone git@github.com:alumno-XXX/my-proyecto-millonario.git
cd my-proyecto-millonario
touch README.md
git add .
git commit -m "commit inicial"
git push origin master
```

- ***Ignorar Archivos***

```bash
touch privado.txt
mkdir privada
echo "privado.txt" >> .gitignore
echo "/privada" >> .gitignore
git add .
git commit -m "añadido fichero .gitignore"
```

- ***3. Añadir Fichero y Tags***

```bash
touch 1.txt
git add .
git commit -m "añadido 1.txt"
git tag v0.1
git push --tags origin master
```

- ***Trabajo con ramas***

```bash
git branch v0.2
git checkout v0.2
touch 2.txt
git add .
git commit -m "añadido 2.txt"
git push origin v0.2
```
- ***Merge sin Conflicto***

```bash
git checkout master
git merge v0.2 -m "merge v0.2 sin conflictos"
```
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

Esta práctica nos sirvió para aprender a usar Git y GitHub.
También para usar ramas, que es como trabajar en copias de seguridad de tu proyecto. Permite desarrollar cosas nuevas sin estropear el código principal que ya funciona.
Los tags que sirven para poner etiquetas de "Versión 1.0" a tu código, marcando momentos importantes. El archivo .gitignore. Y por último, cuando juntas el trabajo de las ramas (fusión), a veces Git se confunde porque dos personas cambiaron la misma línea. Aprender a resolver esos conflictos es la parte más importante para poder trabajar en equipo.
