# Functions and advanced types

Languages - Idiomas
[English](#English)
[Español](#Español)

## English

### Topics to take into account in this project

- Create and call functions `{return type} {name of function} ({input parameters})`
  Ex: `int main (int argc, char *argc) /* you do not need to understand argv and argc */`
- Pointer variable types, arrays:
  - `char *`
  - `int *`
  - Relationship between pointers and arrays
- Use header files, implement them, uses.

### Concepts

#### Structure of a function

In the previous exercise we saw how to create a main function following the following structure:

`int main(void)`

The structure when creating a function looks like this:

```
{type of value to return} {name of function} ({parameters to receive})
{
  /* function logic here */
}
```

We replace the `{}` with the values ​​then we have the structure of our function

#### Pointers

Essentially a pointer points to an address in memory, that is, the location of a variable, making a simile, a pointer would be the address of your house, and you can know the people inside by visiting the address. You can know the address of the house or see the people inside, clearly the people inside can vary, but the address does not.

Passing it to the C language, I can define a pointer type variable that points to a specific variable, said variable can change its value, and I can still know what it is because the address in memory is the same. Likewise, I can know the value of the address in memory or what the value contained within that address is, this is called 'dereferencing', an example of this could be the following:

```c
#include <stdio.h>

int main(void)
{
  /* I define an int variable */
  int intVariable = 0;
  /* I define a pointer type variable */
  int *intVariablePointer = &intVariable;

  /* I print the value of the int variable in the console */
  printf("value of my int variable: %d\n", intVariable);
  /* I print the value of the pointer type variable in the console */
  printf("value of my pointer variable: %ls\n", intVariablePointer);
  /* I print the dereferenced value of the int type variable in the console */
  printf("value of my int variable from my pointer variable: %d", *intVarriablePointer);

  /* I exclusively change the value of my int type variable */
  intVariable = 5;

  /* I print the value of the int variable in the console */
  printf("value of my int variable: %d\n", intVariable);
  /* I print the value of the pointer type variable in the console */
  printf("value of my pointer variable: %ls\n", intVariablePointer);
  /* I print the dereferenced value of the int type variable in the console */
  printf("value of my int variable from my pointer variable: %d\n", *intVariablePointer);
}
```

Aspects to highlight:

- To access the memory address of a variable I use the `&` symbol (ampersand) followed by the name of the variable whose memory address I want to know
- We see that to declare a pointer type variable it has the following structure: `{data type inside} *{variable name}`, where the first type must be the same type of the variable we want to access, in our example both They are of type `int`. Then follows a `*` to represent that it is a pointer type and the name we assign to our variable.
- We also see that we only change the value of one of the variables, but when printing the value of my pointer variable dereferenced from the pointer, its value is also updated.

#### Arrays

Arrays are values ​​in memory of the same type located consecutively, that is, one after another. Let's take variables of type `int` as an example, and I need 5 consecutive values, that is, I would have an array of type `int` the size of 5 spaces. In code it would represent something like this:

```c
int array[5];
```

Now to assign a value to each of the boxes in that allocated memory we could do it as follows:

```c
array[0] = 10;
array[1] = 11;
fixit[2] = 15;
array[3] = 7;
array[4] = 1;
```

We can observe a peculiar behavior and that is that in the first position we do not use the number `1` to start counting, but rather the `0`, the arrangement in position 0 would be our first space; When we talk about positions in memory or in an array we start counting from zero, but it does not mean that there are 0 elements, if you look there are 5 spaces in memory assigned, and since it starts at `0` the last position would be `4 ` in our example.

We can also do the same thing we did previously in summary:

```c
int array[] = {10, 11, 15, 7, 1};
```

Which works the same as the lines above. In this case, it is not necessary that we assign a specific size to the array, since the language is capable of inferring it based on the number of values ​​that we provide. Given that it will be an arrangement of 5 positions exclusively.

To change the values ​​of each of the positions is the same as the last one as we did above by accessing each of the positions in the array to change the value of the specific position.

#### Arrays and String

In the last project we touched on the topic of characters, which is an individual memory space that we can represent like this `char character = 'h';`. What if we want to represent longer values ​​or texts? Well, for that we have what we call `strings` or chains, but in C we do not have `string` as such, but we do have an array of characters that we can treat as strings.

To assign a variable as if it were a string we would do it as follows:

```c
char string[];
```

But there are also many other ways we can deal with it, such as arrays or specifically strings.

```c
char string[] = "Hello world!";
char string2[] = {'H', 'o', 'l', 'a', ' ', 'm', 'u', 'u', 'n', 'd', 'o', ' !', '\0'};
```

Things to keep in mind:

- All strings end in something we call a null character represented like this: `\0`
- We can create and treat a string equal to an array of numbers that we saw previously but we can also create it with double quotes, which

#### Relationship of arrays and pointers

We have already seen the arrangements we have, how to deal with them, as well as access particular values ​​or positions. So what is the relationship between arrays and pointers?

To make it short, underneath they are the same. To make a more detailed explanation, pointers point to an address in memory, and arrays are a block in memory of the space we need. When we deal with arrays and they are pointers, the pointer points to the first position by default, and if we want to access the next position we have to move the pointer.

We already saw how to declare arrays of numbers and characters. Now we can also declare these same in their pointer form as follows:

```c
char *string = "Hello world!";
int *arrayInt = {1, 2, 3, 4, 5};
```

### Tasks

0. Create directory called `pointers_advances-types`

This folder must have a `README.md` file ` with the description of the topics to be discussed, and a description of the project.

1. Create a file called `0-print_int_array.c` and add the following code:
   1. Create a function called `print_int_array` that receives as parameters a variable called `arrayToPrint` of type `int *` and returns a type `int`.
   2. Create a loop of any type (`while`, `for`) that is responsible for traversing the array.
   3. We are going to access the positions within the arrangement. Use an iterator variable that is responsible for viewing the content within the positions of the array.
   4. Use the `printf` function to print unstructured integers from the array in the console at the position of the iterator variable we created followed by a line break.
   5. Return the iteration variable
2. Create a main function that is responsible for calling the function that we previously created.
   1. Create an array of type `int` of length 5, whose values ​​can be whatever they consider, but
   2. Call the `print_int_array` function passing it the array we created previously
   3. Return the number 0 in the main function.
3. Create a file called `main.h` and add the [prototype](https://www.geeksforgeeks.org/function-prototype-in-c/) of the `print_int_array` function inside
4. Call said file `main.h` in the main function.

## Español

### Temas a tener en cuenta en este proyecto

- Crear y llamar funciones `{return type} {name of function}  ({input parameters})`
  Ej: `int main (int argc, char *argc) /* no neceita entender argv y argc */`
- Tipos de variables punteros, arreglos:
  - `char *`
  - `int *`
  - Relación entre punteros y arreglos
- Utilizar header files, implementarlos, usos.

### Conceptos

#### Estructura de una función

En el ejercicio anterior vimos como crear una función main siguiendo la siguiente estructura:

`int main (void)`

La estructura a la hora de crear una función se parece a esto:

```
{tipo de valor a retornar} {nombe de la función} ({parámetros a recibir})
{
	/* lógica de la función acá */
}
```

reemplazamos los `{}` con los valores entonces tenemos la estructura de nuestra función

#### Punteros

Esencialmente un puntero apunta a una dirección en memoria, es decir la ubicación de una variable, haciendo un símil, un puntero sería la dirección de tu casa, y puedes saber las personas que hay dentro visitando la dirección. Puedes saber la dirección de la casa o ver las personas que hay dentro, cláramente las personas que hay dentro pueden variar, pero la dirección no.

Pasándolo al lenguaje C, puedo definir una variable tipo puntero que apunte a una variable específica, dicha variable puede cambiar su valor, y yo igual puedo saber cuál es porque la dirección en memoria es la misma. Así mismo puedo saber el valor de la dirección en memoria o cual es el valor contenido dentro de esa dirección, a esto se le llama `desreferenciar`, un ejemplo de esto puede ser el siguiente:

```c
#include <stdio.h>

int main(void)
{
	/* defino una variable tipo int */
	int intVariable = 0;
	/* defino una variable tipo pointer */
	int *intVariablePointer = &intVariable;

	/* imprimo en consola el valor de la variable tipo int */
	printf("valor de mi variable int: %d\n", intVariable);
	/* imprimo en consola el valor de la variable tipo pointer */
	printf("valor de mi variable puntero: %p\n", intVariablePointer);
	/* imprimo en consola el valor desreferenciado de la variable tipo int */
	printf("valor de mi variable tipo int desde mi variable tipo puntero: %d", *intVarriablePointer);

	/* cambio exclusivamente el valor de mi variable tipo int */
	intVariable = 5;

	/* imprimo en consola el valor de la variable tipo int */
	printf("valor de mi variable int: %d\n", intVariable);
	/* imprimo en consola el valor de la variable tipo pointer */
	printf("valor de mi variable puntero: %p\n", intVariablePointer);
	/* imprimo en consola el valor desreferenciado de la variable tipo int */
	printf("valor de mi variable tipo int desde mi variable tipo puntero: %d", *intVarriablePointer);
}
```

Aspectos a remarcar:

- Para acceder a la dirección en memoria de una variable utilizo el símbolo `&` (ampersand) seguido de el nombre de la variable cuya dirección en memoria quiero saber
- Vemos que para declarar una variable tipo puntero tiene la siguiente estructura: `{tipo de dato dentro} *{nombre de la variable}`, donde el primer tipo debe ser el mismo tipo de la variable que queremos acceder, en nuestro ejemplo ambos son de tipo `int`. Luego sigue un `*` para representar que es tipo puntero y el nombre que le asignamos a nuestra variable.
- También vemos que sólo cambiamos el valor de una de las variables, pero al momento de imprimir el valor de mi variable pointer desreferenciada desde el pointer su valor también se actualiza.

#### Arreglos

Los arreglos son valores en memoria del mismo tipo ubicadas de forma consecutiva, es decir uno tras de otro. Tomemos como ejemplo variables de tipo `int`, y necesito 5 valores consecutivos, es decir tendría un arreglo de tipo `int` del tamaño de 5 espacios. En código lo representaría algo así:

```c
int arreglo[5];
```

Ahora para asignarle un valor a cada una de las casillas de esa memoria asignada podríamos hacerlo de la siguiente manera:

```c
arreglo[0] = 10;
arreglo[1] = 11;
arregelo[2] = 15;
arreglo[3] = 7;
arreglo[4] = 1;
```

Podemos observar un comportamiento peculiar y es que en la primera posición no utilizamos el número `1` para empezar a contar, sino el `0`, el arreglo en la posición 0 sería nuestro primer espacio; cuando hablamos de posiciones en memoria o en un arreglo comenzamos a contar desde el cero, pero no quiere decir que hayan 0 elementos, si te fijas hay 5 espacios en memoria asignados, y como comienza en `0` la última posición sería la `4` en nuestro ejemplo.

También podemos hacer lo mismo que hicimos previamente de forma resumida:

```c
int arreglo[] = {10, 11, 15, 7, 1};
```

Que funciona igual que las líneas de arriba. En este caso no es necesario que le asignemos un tamaño específico al arreglo, dado que el lenguaje es capaz de inferirlo con base a la cantidad de valores que le proporcionamos. Dado está que va a ser un arreglo de 5 posiciones exclusivamente.

Para cambiar los valores de cada una de las posiciones es igual que la última como hicimos arriba accediendo a cada una de las posiciones del arreglo para cambiar el valor de la posición específica.

#### Arreglos y cadenas

En el proyecto pasado tocamos el tema de los caracteres, que es un espacio en memoria individual que podemos representar así `char caracter = 'h';`. ¿Qué pasa si queremos representar valores más largos o textos? bueno para eso tenemos lo que llamamos `strings` o cadenas, pero en C no tenemos `string` como tal, pero sí tenemos un arreglo de caracteres que podemos tratar como cadenas.

Para asignar una variable como si fuera una cadena lo haríamos de la siguiente manera:

```c
char cadena[];
```

Pero también hay muchas otras formas en las que lo podemos tratar, como arreglos o específicamente cadenas.

```c
char cadena[] = "Hola mundo!";
char cadena2[] = {'H', 'o', 'l', 'a', ' ', 'm', 'u', 'u', 'n', 'd', 'o', '!', '\0'};
```

Cosas a tener en cuneta:

- Todas las cadenas terminan en algo que llamamos carácter nulo representado así: `\0`
- Podemos crear y tratar una cadena igual a un arreglo de números que vimos previamente pero también podemos crearlo con las comillas dobles, lo que

#### Relación de arreglos y punteros

Ya hemos visto los arreglos que tenemos, como tratar con ellos, así mismo acceder a valores o posiciones particulares. Entonces ¿cuál es la relación entre arreglos y punteros?

Para hacerlo corto, por debajo son lo mismo. Haciendo una explicación más detallada, los punteros apuntan a una dirección en memoria, y los arreglos son un bloque en memoria del espacio que necesitamos. Cuando tratamos con arreglos y que son punteros, el puntero apunta a la primera posición por defecto, y si queremos acceder a la siguiente posición tenemos que mover el puntero.

Ya vimos como declarar arreglos de números y de caracteres. Ahora también podemos declarar estos mismo en su forma de punteros de la siguiente forma:

```c
char *cadena = "Hola mundo!";
int *arregloInt = {1, 2, 3, 4, 5};
```

### Tareas

0. Crear una función llamada `print_int_array` que reciba como parámetros una variable llamada `arrayToPrint` tipo `int *` y que retorne un tipo `int`.
   1. Crea un ciclo de cualquier tipo (`while`, `for`) que se encargue de recorrer el arreglo.
   2. Vamos a acceder a las posiciones dentro del arreglo. Utiliza una variable iterador que se encargue de ver el contenido dentro de las posiciones del arreglo.
   3. Utiliza la función de `printf` para imprimir en consola enteros destructurados del arreglo en la posición de la variable iterador que creamos seguidos de un salto de línea.
   4. Retorna la variable iteración
1. Crea una función main que se encargue de llamar la función que nosotros creamos previamente.
   1. Crear una arreglo de tipo `int` de largo 5, cuyos valores pueden ser lo que consideren, pero
   2. Llama la función `print_int_array` pasándole el arreglo que creamos previamente
   3. Retorna el número 0 en la función main.
2. Crea un archivo llamado `main.h` y agrege el [prototipo](https://www.geeksforgeeks.org/function-prototype-in-c/) de la función `print_int_array` dentro
3. Llama dicho archivo `main.h` en la función main.
