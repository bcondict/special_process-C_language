# Argv - Argc And Malloc - Free

Languages - Idiomas
[English](#English)
[Español](#Español)

## English

### Topics to consider for the project

- Argv, Argc
- Malloc and Free

### Concepts

#### Argv - Argc

Since at the beginning of programming the systems did not have much memory to store commands, `UNIX` based systems stored commands with acronyms. E.g: `ls` -> list, `mv` -> move, `pwd` -> print working directory, etc.

Following this line of character economy, the C language is built. So `Argc` is the acronym for 'Argument Count' which translates 'Argument Count', and `Argv` is the acronym for 'Argument Vector' which translates ' Argument Vectors'.

To use them, they must be included in the main function and its prototype looks like this:
`int main(int argc, char *argv[])` .

As you can see, the arguments that the main function receives are 2:

- `int argc`: variable argc of type int which is the count of the arguments
- `int argv`: variable argv of type char\*, which means that it is a pointer, but it is also "[]", that is, it is also an array, and as we saw in the last session, arrays and pointers are similar, that is, they are the same for the system below. Why this, because you receive an array of strings, the strings are pointers or arrays of characters. So if you understood it correctly, it is an array of arrays, or a pointer of arrays or... **A pointer of pointers**. Therefore you can access the positions of the first pointer and then the pointer inside.

Looking at it practically:

```bash
./executable argument1 argument2
```

```c
#include <stdio.h>

int main(int argc, char *argv[])
{
  int i = 0;

  printf("argument count: %d\n", argc) /* 3 */
  for (i = 0; i < argc; i++)
  {
  printf("arguemnts: %s\n", argv[i]);
  }

  return(0);
}
```

As you can see in the example, we are destructuring the array `argv`, and accessing the vectors within it. Which in this case would be: `./executable`, `argument1`, `argument2`.

#### Malloc - Free

`Malloc` is short for 'Memory Allocation'. It is used to allocate memory to a variable that we do not know when it will contain. Making a simile it would be like: When we know the size of what we are going to store, we take a bigger or smaller box,

What happens when we need to use malloc is that we do not know the size of the object, therefore, we do not know what size our box should be to store that object. This is considered variable memory, whose value is not defined before the execution of the program.

Already touched on `Malloc` then `Free` is to free the memory that we host with each `Malloc` that we made. The reason why it may be something 'tricky' is that we do not do free at the same time that we do malloc, not even at the end of said function, but rather we do free after we are no longer using the memory we host.

### Tasks

1. In the `C_basics` repository create a folder called `Argv_Argc_Free`
2. Create within said folder create a file called `argv_argc.c`
   1. Within said file, create the `main` function that receives `argc` and `argv` as parameters.
   2. Create a variable of type array of integers, where you will store the values ​​of `argv` converted to numbers
   3. Create a malloc of said variable about the number of numbers to save
   4. Convert the values ​​given in `argv` to numbers, if a value inside `argv` cannot be converted to number, or returns error, print: `Error`, free the reserved memory and return (`1`).
   5. Add all the values ​​of `argv` converted to numbers.
   6. Print all values ​​of `argv`
   7. Print the sum of these values
   8. If everything went well, return (`0`) and free the reserved memory.

## Español

### Temas a considerar para el proyecto

- Argv, Argc
- Malloc y Free

### Conceptos

#### Argv - Argc

Como en los inicios de la programación los sistemas no poseían demasiada memoria para almacenar los comandos, los sistemas basados en `UNIX` guardaban los comandos con acrónimos. E.j: `ls` -> list, `mv` -> move, `pwd` -> print working directory, etc.

Siguiendo esa línea de economía de los caracteres, se construye el lenguaje C. Entonces `Argc` es el acrónimo para 'Argument Count' que traduce 'Conteo de Argumentos', y `Argv` es el acrónimo para 'Argument Vector' que traduce 'Vectores de Argumentos'.

Para utilizarlos se deben incluir en la función main y su prototipo luce de la siguiente forma:
`int main(int argc, char *argv[])` .

Como puedes ver los argumentos que recibe la función main son 2:

- `int argc`: variable argc de tipo int que es el conteo de los argumentos
- `int argv`: variable argv de tipo char\*, lo que quiere decir que es un puntero, pero también es "[]", es decir es también un arreglo, y como vimos en la sesión pasada los arreglos y los punteros son similes, es decir son los mismo para el sistema por debajo. Por que esto, porque tú recibes un arreglo de cadenas, las cadenas son punteros o arreglos de caracteres. Entonces si lo comprendiste bien, es un arreglo de arreglos, o un puntero de arreglos o... **Un puntero de punteros**. Por ende puedes acceder a las posiciones del primer puntero y luego al puntero dentro.

Viéndolo de forma práctica:

```bash
./executable argument1 argument2
```

```c
#include <stdio.h>

int main(int argc, char *argv[])
{
	int i = 0;

	printf("argument count: %d\n", argc) /* 3 */
	for (i = 0; i < argc; i++)
	{
		printf("arguemnts: %s\n", argv[i]);
	}

	return(0);
}
```

Como se puede observar el ejemplo, estamos desestructurando el arreglo `argv`, y accediendo a los vectores dentro de este. Que en este caso serían: `./executable`, `argument1`, `argument2`.

#### Malloc - Free

`Malloc` es de forma abreviada 'Memory Allocation', que traduce 'Asignación de Memoria'. se utiliza para asignar memoria a una variable que no sabemos cuando va a contener. Haciendo un símil sería como: Cuando conocemos el tamaño de lo que vamos a guardar cogemos una caja más grande o más pequeña,

Lo que sucede cuando necesitamos usar malloc es que no conocemos el tamaño del objeto, por ende, no sabemos que tamaño debe tener nuestra caja para guardar ese objeto. A esto se le considera memoria variable, que su valor no está definido antes de la ejecución del programa.

Ya tocado `Malloc` entonces `Free` es para liberar la memoria que alojamos con cada `Malloc` que hicimos. El porqué puede ser algo 'triqui' es que no hacemos free en el mismo momento que hacemos malloc, ni siquiera al final de dicha función, sino que hacemos free después de que ya no estamos usando la memoria que alojamos.

### Tareas

1. En el repositorio `C_basics` crea una carpeta llamada `Argv_Argc_Free`
2. Crea dentro de dicha carpeta crea un archivo llamado `argv_argc.c`
   1. Dentro de dicho archivo crea la función `main` que reciba como parámetros `argc` y `argv`.
   2. Cree una variable de tipo arreglo de enteros, donde va a guardar los valores de `argv` convertidos a números
   3. Cree un malloc de dicha variable sobre la cantidad de números a guardar
   4. Convierta los valores dados en `argv` a números, si un valor dentro `argv` no puede ser convertido a número, o devuelve error, imprima: `Error`, libere la memoria reservada y retorne (`1`).
   5. Sume todos los valores de `argv` convertidos a números.
   6. Imprima todos los valores de `argv`
   7. Imprima la suma de dichos valores
   8. Si todo salió bien, retorne (`0`) y libere la memoria reservada.
