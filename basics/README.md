# C Basics and Git basics

Languages - Idiomas
[English](#English)
[Español](#Español)

## English:

### Topics to consider for this project:

- Create, clone and fork a git repository
- Compile a program, using `gcc`
  - What are flags for when compiling a .c file?
- Variable types `int`, `char`, `unsigned int`
  - How much memory space does each type of data take up?
  - Type of maximum values ​​to represent in numerical types
- Conditionals `if`, `else`.
- `while`, `for` loops
  - Uses of cycles

### Extra

- These exercises will be evaluated individually to guarantee correct learning of the topics to be covered.
- The use of automatic code generation tools such as: `ChatGPT`, `Blackbox`, `Github Copilot`, etc. They are prohibited, since these tools greatly limit the learning of the proposed topics
- You can use google to search on related topics

### Tasks

0. Create a repository on GitHub called `C_projects` and clone this repository to your local machine.

   This must have a `README.md` file with a description of the topics to be discussed, and a description of each folder within the repository.

1. Create a folder called `basics`.

   This folder must have a `README.md` file describing each of the points to be discussed from this point on.

2. Create a file `0-main.c`
   1. import the standard library to use the `printf` function
   2. create a comment block to document the `main` function
   3. main function prototype: `int main(void)`
   4. Create variables of the following types and assign them a value of your choice:
      - `int`
      - `char`
      - `double`
   5. Use the `printf` function to print the values ​​stored within the variables created previously in the console
   6. Use the `sizeof` function to find out the memory size of the previously used data types (`int`, `char`, `double`)
   7. At the beginning of the file import the following libraries:
      - `time.h`
      - `stdlib.h`
   8. Add the following line of code to the function: `int randomNumber = rand() % 101`
   9. Use the `if` - `else` conditionals to know if the generated number is greater than `50`
      - If the number is greater than 50 you must print the following line of code:
        `The number 51 is greater than 50 YAY!`
      - If the number is less than 50, print the following:
        `The number 49 is not greater than 50 :(`
3. Create a file `1-main.c`
   1. Create the `main` function with the same prototype as above
   2. Create a variable of type `int` that works as an iterator for our loops
   3. Using a `while` loop type generates the following screen printout
      ```
        iteration [0] hello world
        iteration [1] hello world
        iteration [2] hello world
        iteration [3] hello world
        iteration [4] hello world
        iteration [5] hello world
      ```
   4. Do the same using a `for` loop
4. Individually compile the files previously created with the `gcc` command, in the `README.md` file write the function and utility of the following flags of the `gcc` command
   - `-Wall`
   - `-Werror`
   - `-Wextra`
   - `-pedantic`
   - `-std=gnu98`
5. Update the `README.md` file in the `basics` folder describing the two files worked on, the topics learned. The description must be created by you without help from Google or any artificial intelligence tool.
6. Upload the changes made to your remote repository, remember to use useful and descriptive commit messages related to the changes made within the repository.

## Español:

### temas a tener en cuenta para este proyecto:

- Crear, clonar y forkear (bifurcar) un repositorio de git
- Compilar un programa, utilizando `gcc`
  - Para que sirven las banderas a la hora de compilar un archivo .c
- Tipos de variables `int`, `char`, `unsigned int`
  - Cuanto espacio en memoria ocupa cada tipo de dato
  - Tipo de valores máximos a representar en los tipos numéricos
- Condicionales `if`, `else`.
- Ciclos `while`, `for`
  - Usos de los ciclos

### Extra

- Estos ejercicios van a ser evaluados de forma individual para garantizar el correcto aprendizaje de los temas a tratar.
- El uso de herramientas de generación de código automático como: `ChatGPT`, `Blackbox`, `Github Copilot`, etc. Están prohibidos, dado que estas herramientas limitan enormemente el aprendizaje de los temas propuestos
- Puede usar google para hacer búsquedas sobre los temas relacionados

### Tareas

0. Crea un repositorio en GitHub llamado `C_projects` y clona este repositorio en tu máquina local.

   Este debe contar con archivo `README.md` con la descripción de los temas a tratar, y una descripción de cada carpeta dentro del repositorio.

1. Crear una carpeta llamada `basics`.

   Esta carpeta debe contar con un archivo `README.md` describiendo cada uno de los puntos a tratar a partir de este punto.

2. Crear un archivo `0-main.c`
   1. importar la librería estándar para utilizar la función `printf`
   2. crear un bloque de comentarios para documentar la función `main`
   3. prototipo de la función main: `int main(void)`
   4. Crea variables de los siguientes tipos y asígnales un valor a tu elección:
      - `int`
      - `char`
      - `double`
   5. Utiliza la función de `printf` para imprimir en consola los valores almacenados dentro de las variables creadas anteriormente
   6. Utiliza la función `sizeof` para saber el tamaño en memoria de los tipos de datos anteriormente utilizados (`int`, `char`, `double`)
   7. Al inicio del archivo importa las siguientes librerías:
      - `time.h`
      - `stdlib.h`
   8. Agrega la siguiente línea de código a la función: `int randomNumber = rand() % 101`
   9. Utiliza las condicionales `if` - `else` para saber si el número generado es mayor que `50`
      - Si el numero es mayor que 50 debes imprimir la siguiente línea de código:
        `El numero 51 es mayor que 50 YAY!`
      - Si el numero es menor que 50 imprime la siguiente:
        `El numero  49 no es mayor que 50 :(`
3. Crear un archivo `1-main.c`
   1. Crear la función `main` con el mismo prototipo usando anteriormente
   2. Crea una variable de tipo `int` que funcione como iterador para nuestros ciclos
   3. Usando un tipo ciclo `while` genera la siguiente impresión en pantalla
      ```
      iteración [0] hola mundo
      iteración [1] hola mundo
      iteración [2] hola mundo
      iteración [3] hola mundo
      iteración [4] hola mundo
      iteración [5] hola mundo
      ```
   4. Has lo mismo usando un ciclo de tipo `for`
4. Compile individualmente los archivos creados previamente con el comando `gcc`, en el archivo `README.md` escriba la función y utilidad de las siguientes banderas del comando `gcc`
   - `-Wall`
   - `-Werror`
   - `-Wextra`
   - `-pedantic`
   - `-std=gnu98`
5. Actualiza el archivo `README.md` de la carpeta `basics` describiendo los dos archivos trabajados, los temas aprendidos. La descripción debe ser creada por usted sin ayuda de google, ni ninguna herramienta de inteligencia artificial.
6. Sube los cambios hecho a tu repositorio remoto, recuerda utilizar mensajes de commit útiles y descriptivos relacionados a los cambios hechos dentro del repositorio.

## Author

- Jesus Junco
