# Structures and typedef

Languages
[English](#English)
[Español](#Español)

## English

### Topics to be covered in the project:

- How to use structures
- How to use Typedef

### Concepts

#### Structures

Structures or `struct` in C are the way to relate various variables in a single place, or also seen, in a larger variable. Each variable within the structure is known as a `member` of the structure. Unlike an `array` that can only contain data of the same type, structures can contain many other different types of data (`int`, `char`, `float`, etc.).

Structures are usually used to group related data, let's take as an example a rectangle, which has a height and length. The way to create a structure in this way would be like this

```c
struct rectangle
{
int height;
int width;
}
```

In this example we only use `int` data types, but we could use any other type, let's do an example with the data of a dog:

```c
struct dog {
int age;
char *name;
}
```

We already saw how to create it but how could we call this type of structure data? To call a structure we would do it like this:

```c
int main (void)
{
struct rectangle newRectangle;

return (0);
}
```

and to access the values ​​within this structure, we use the name that we defined for the structure, followed by a period and the name of the value (or member) to access

```c
struct rectangle
{
int height;
int width;
}

int main (void)
{
struct rectangle newRectangle;

newRectangle.height = 10;
newRectangle.width = 5;

printf("height of rectangle: %d\n", newRectangle.heigth);
printf("width of rectangle: %d\n", newRectangle.width);

return (0);
}
```

You can create as many structures as you consider necessary, change their values, etc. But it is not convenient to have to always use the reserved word `struct` to call a variable of type structure, I wish there was a way to create a data type that refers to said structure.

#### Typedef

`typedef` is a keyword used to create a new name for an existing data type, used to redefine the name of a data type.

syntax:

```c
typedef existing_name alias_name;
```

Example:

```c
typedef long long ll;
```

This is especially useful when working with structures, so we can give our structure a name or an alias, and instead of calling it the whole thing we can use typedef to give it a more easily recognizable name.

```c
#include <stdio.h>

typedef struct dog
{
char *name;
int age;
} Dog_t;

int main (void)
{
Dog_t newDog;
strcpy(newDog.name, "firulais");
newDog.age = 1;

printf("name of my dog: %s\n", newDog.name);
printf("age of my dog: %d\n", newDog.age);

return (0);
}
```

Here we can see that we changed the name of the structure, and we no longer call it `struct dog newDog` but simply `Dog_t newDog`, saving us a lot of complications, making it easier to understand the code and what we create.

We can also create an instance of a structure in the following way:

```c
#include <stdio.h>

typedef struct dog
{
char *name;
int age;
} Dog_t;

int main (void)
{
Dog_t newDog = {"firulais", 1};

printf("name of my dog: %s\n", newDog.name);
printf("age of my dog: %d\n", newDog.age);

return (0);
}
```

Where you can see that we directly create the instance of our `Dog_t` structure with the values ​​"firulais" for the name and 1 for the age.

### Tasks

1. In the `C_basics` repository create a directory called `structures_and_typedef`
2. Create a file `main.h`
   1. Use the functions `#ifndef _MAIN_H_`, `#define _MAIN_H_`, `#endif /* _MAIN_H_ */` in order to ensure code quality
   2. Create a structure called `Person`, which has 3 members:
      1. `name` of type `char *`
      2. `salary` of type `float`
      3. `parentsName` of type `char *[]` (array of char pointers)
   3. Give it an alias called `Person_t`
3. Create a file called `structres_typedef.c`
   1. Create the function `main` and make sure it receives `argc` and `argv`.
   2. The way to use it will be as follows:
      `./structs_typedef john 25 lucia alfred`
      where argument 1 is the name of the person, the second is the salary, and 3 and 4 are the names of the parents.
   3. Cast the necessary data types to fit the necessary values.
   4. Assign the values ​​given in the arguments to an instance of the created structure `Person_t`.
   5. Make sure to print the values ​​of the structure instance
   6. Return 0.
4. To compile use the flags `-Wall -Werror -Wextra -pedantic -std=gnu98` and the name of the executable must be `structrs_typedef`

## Español

### Temas a tratar en el proyecto:

- Como usar estructuras
- Como usar Typedef

### Conceptos

#### Estructuras

Las estructuras o `struct` en C son la forma de relacionar diversas variables en un único lugar, o también visto, en una variable más grande. Cada variable dentro de la estructura es conocido como `member` (miembro en inglés) de la estructura. A diferencia de un `array` que sólo puede contener datos del mismo tipo, las estructuras pueden contener muchos otros tipos de datos diferentes (`int`, `char`, `float`, etc. ).

Por lo general se usan estructuras para agrupar datos relacionados, tomemos como ejemplo un rectángulo, que tiene alto y largo. La forma de crear una estructura de esta forma sería así

```c
struct rectangle
{
	int height;
	int width;
}
```

En este ejemplo sólo usamos tipos de datos `int`, pero podríamos usar cualquier otro tipo, hagamos un ejemplo con los datos de un perro:

```c
struct dog {
	int age;
	char *name;
}
```

Ya vimos como crearlo pero como podríamos llamarlo este tipo de dato estructura? para llamar una estructura lo haríamos así:

```c
int main (void)
{
	struct rectangle newRectangle;

	return (0);
}
```

y para acceder a los valores dentro de esta estructura, usamos el nombre que le definimos a la estructura, seguido de un punto y el nombre del valor (o miembro) a acceder

```c
struct rectangle
{
	int height;
	int width;
}

int main (void)
{
	struct rectangle newRectangle;

	newRectangle.height = 10;
	newRectangle.width = 5;

	printf("heigth of rectangle: %d\n", newRectangle.heigth);
	printf("width of rectangle: %d\n", newRectangle.width);

	return (0);
}
```

Puedes crear tantas estructuras como consideres necesario, cambiar sus valores, etc. Pero no es cómodo tener que para llamar una variable de tipo estructura, tener que usar siempre la palabra reservada `struct`, ojalá hubiera una forma de poder crear un tipo de dato que se refiera a dicha estructura.

#### Typedef

`typedef` es una palabra clave utilizada para crear un nuevo nombre a un tipo de dato ya existente, usado para redefinir el nombre de un tipo de dato.

sintaxis:

```c
typedef nombre_existente nombre_alias;
```

Ejemplo:

```c
typedef long long ll;
```

Esto es especialmente util cuando trabajamos con estructuras, por así le podemos dar un nombre o un alias a nuestra estructura, y en lugar de llamarla todo completo podemos utilizar typedef para darle un nombre más fácilmente reconocible.

```c
#include <stdio.h>

typedef struct dog
{
	char *name;
	int age;
} Dog_t;

int main (void)
{
	Dog_t newDog;
	strcpy(newDog.name, "firulais");
	newDog.age = 1;

	printf("name of my dog: %s\n", newDog.name);
	printf("age of my dog: %d\n", newDog.age);

	return (0);
}
```

acá podemos observar que le cambiamos el nombre a la estructura, y ya no lo llamamos como `struct dog newDog` sino que simplemente `Dog_t newDog`, ahorrándonos muchas complicaciones, haciendo más fácil entender el código y lo que creamos.

También podemos crear una instancia de una estructura de la siguiente forma:

```c
#include <stdio.h>

typedef struct dog
{
	char *name;
	int age;
} Dog_t;

int main (void)
{
	Dog_t newDog = {"firulais", 1};

	printf("name of my dog: %s\n", newDog.name);
	printf("age of my dog: %d\n", newDog.age);

	return (0);
}
```

Donde se puede ver que crear directamente la instancia de nuestra estructura `Dog_t` con los valores "firulais" para el nombre y 1 para la edad.

### Tareas

1. En el repositorio `C_basics` crea un directorio llamado `structures_and_typedef`
2. Cree un archivo `main.h`
   1. Utilice las funcines `#ifndef _MAIN_H_`, `#define _MAIN_H_`, `#endif /* _MAIN_H_ */` con el fin de asegurar la calidad del código
   2. Cree una estructura llamada `Person`, que tenga 3 miembros:
      1. `name` tipo `char *`
      2. `salary` typo `float`
      3. `parentsName` tipo `char *[]` (arreglo de punteros char)
   3. Asígnele un alias llamado `Person_t`
3. Crea un archivo llamado `strucutres_typedef.c`
   1. Cree la función `main` y asegúrese de recibir `argc` y `argv`.
   2. La forma de usarse sera de la siguiente manera:
      `./structs_typedef john 25 lucia alfred`
      donde el argumento 1 es el nombre de la persona, el segundo es el salario, y 3 y 4 son los nombres de los padres.
   3. Castee los tipos de datos necesarios para que encajen en los valores necesarios.
   4. Asigne los valores dados en los argumentos a una instancia de la estructura creada `Person_t`.
   5. Asegúrese de imprimir los valores de la instancia de la estructura
   6. Retorne 0.
4. Para compilar utilice las banderas `-Wall -Werror -Wextra -pedantic -std=gnu98` y el nombre del ejecutable debe ser `structrs_typedef`
