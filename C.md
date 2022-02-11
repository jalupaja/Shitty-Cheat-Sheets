<<<<<<< HEAD
# C Cheat Sheet
> C is a low-level programming language designed for cross-platform programming

| **Table of Contents** |
| -- |
[console output](#console-output)
[console input](#console-input)
[datatypes and specifiers](#datatypes-and-specifiers)
[types of datatypes](#types-of-datatypes)
[functions](#functions)
[types of functions](#types-of-functions)
[conditionals](#conditionals)
[loops](#loops)
[jump statements](#jump-statements)
[includes](#includes)
[bit-operators](#bit-operators)
[other operators](#other-operators)
[definitions](#definitions)
[pointers](#pointers)
[arrays](#arrays)
[function pointers](#function-pointers)
[enums](#enums)
[structs](#structs)
[typedef](#typedef)
[other resources](#other-resources)

## console output
| Function | Explanation |
| -- | -- |
```printf("<text>")``` | output text
```printf("%x %c\n", <decimal var>, <character var>)``` | output a decimal in hex, a character and a new line

## console input
| Function | Explanation | 
| -- | -- |
```scanf("%c %d", <pointer to var>, &<var>)``` | wait for one character, a space and a decimal
```fgets(<string var>, <length of string>, stdin)``` | input a string of a specific length (better for strings due to possible buffer overflow when using scanf)

## datatypes and specifiers
| Datatype | in C | Specifiers |
| -- | -- | -- |
short integer | ```short``` \| ```short int``` | ```%d``` \| ```%i```
integer | ```signed int``` \| ```int``` | ```%d``` \| ```%i```
unsigned integer (>= 0) | ```unsigned``` \| ```unsigned int``` | ```%u```
long integer | ```long``` \| ```long int``` | ```%ld``` \| ```%li```
long long integer | ```long long``` \| ```long long int``` | ```%lld``` \| ```%lli```
float | ```float``` | ```%f```
double | ```double``` | ```%lf```
long double | ```long double``` | ```%Lf```
character | ```char``` | ```%c```
| | |
string | ```char[]``` | ```%s```
pointer | ```void *``` | ```%p```

## types of datatypes
| Type | Usage |
| -- | -- |
```static``` | won't be deleted at the end of the scope
```auto``` | will be automatically deletet at the end of the scope(default)
```extern``` | used if variable is in another file
```register``` | tells the compiler to save variable in cpu-register which is faster then RAM (compiler will still decide)
```volatile``` | always read variable from memory (mostly used for driver software)
```const``` | defines a constant variable that connot be changed

## functions
| Example | Usage |
| -- | -- |
```void Hey() {printf("Hey\n");}``` | function to print "Hey"
```static int Add(int n1, int n2) {return n1 + n2;}``` | static function to add two numbers
```int main(){Hey(); return 0;}``` | default function that will start on program start and call Hey-function

When calling a function, the compiler has to already "know" that the function exists. This can be done by writing the function above the function-call or by declaring it before: ```returnType functionName(datatype1, datatype2, ...);```

## types of functions
| Type | Usage |
| -- | -- |
```static``` | function scope is limited to its object file
```extern``` | function can be used by other files(default)
```inline``` | compiler will put code of function on function calls

## conditionals
```C
if (condition) /* code */;
```
```C
if (condition) { /* multi line code */ }
```
```C
if (condition1) { } else if (condition2) { } else { }
```
```C
(condition) ? /* code */ : /* else code */; a = (true) ? 1 : 0;
```
```C
switch(int/char-Variable) {
    case 1:
        /* if variable is 1 */
        break;
    case 2:
        /* if variable is 2 */
    case 3:
        /* if variable is 2 or 3 */
        break;
    default:
        /* any other case */
        break;
}
```

## loops
| Loop | Usage |
| -- | -- |
```while(condition) { /* code */ }``` | run code as long as condition is true
```do { /* code */ } while (condition)``` | run code as long as condition is true but at least once
```for(int i=0; i<10; i++) { /* code */}``` | run code 10 times

## jump statements
| Statement | Usage |
| -- | -- |
```continue;``` | stop current running loop and jump to next one
```break;``` | break out of current loop
```jump label;``` | jump to ```label:``` (should not be used)
```return;``` | break out of current function
```exit;``` | exit program

## includes
- include header from compiler folder: ```#include <filename.h>```
- include header from current directory: ```#include "filename.h"```

| ```#include <...>``` | Useful example | Usage |
| -- | -- | -- |
```stdio.h```
| | ```printf()``` | output to console
| | ```scanf()``` | user input from console
| | ```fgets()``` | user input from console
| | ```fopen(file, mode)``` | open file in specified mode
| | ```fclose(file)``` | close previously opened file
```stdlib.h```
| | ```wchar_t``` | 16bit unicode character
| | ```EXIT_SUCCESS``` | "successful" return value
| | ```EXIT_FAILURE``` | "not successful" return value
| | ```rand()``` | returns pseudo-random number
| | ```srand(n)``` | create new seed for rand()
| | ```*malloc(x)``` | allocate x bytes of memory
| | ```*calloc(n, x)``` | allocate x bytes of memory for n items
| | ```*realloc(*ptr, x)``` | reallocate x bytes and copy previously allocated memory(ptr)
| | ```free(*ptr)``` | deallocate previously allocated memory(ptr)
```stdint.h```
| | ```intN_t``` | int with N bits
| | ```uintN_t``` | unsigned int with N bits
| | ```int_fastN_t``` | fastest int with at least N bits
| | ```intmax_t``` | biggest possible integer
```limits.h```
| | ```INT_MAX``` | defined as current maximum integer
| | ```INT_MIN``` | defined as current minimum integer
| | ```UINT_MAX``` | defined as current maximum unsigned int
| | ```LONG_MAX``` | defined as current maximum long
```string.h```
| | ```strlen(char *A)``` | returns length of string A
| | ```strncpy(char *A, char *B, int length)``` | copy string B to A
| | ```strncat(char *A, char *B, int length)``` | concatenate strings
| | ```strncmp(char *A, char *B, int length)``` | compare strings
| | ```strcspn(char *A, char *B)``` | returns index of first occurrence of any char B in A
| | ```strstr(char *A, char *B)``` | returns pointer to first occurrence of string B in A
```ctype.h```
| | ```isdigit(char)``` | returns 0 if not a digit, else returns 1
| | ```islower(char)``` | returns 0 if not lowercase, else returns 1
| | ```isupper(char)``` | returns 0 if not uppercase, else returns 1
| | ```tolower(char)``` | returns lowercase character
```stdbool.h```
| | ```bool``` | boolean can be true=1 or false=0

## bit-operators
| Operator | Name | Usage |
| -- | -- | -- |
```&``` | AND | if (BitA == BitB == 1) -> 1; else -> 0
```\|``` | OR | if (BitA == BitB == 0) -> 0; else -> 1
```^``` | XOR (eXplicit OR) | if (BitA != BitB) -> 1; else -> 0
```~``` | NOT | 0->1; 1->0
```>>``` | shift right | = /2 (only for positiv numbers)
```<<``` | shift left | = *2 (might (buffer-)overflow)

## other operators
| Operator | Usage |
| -- | -- |
```sizeof(x)``` | returns used memory of x in bytes

## definitions
- define a constant: ```#define CONSTANT 5```
- define a macro: ```#define OUT printf(``` 
  - -> ```OUT "abc");```
- define a function: ```#define LOWER(x,y) ((x>y) ? y : x)```
  - -> ```LOWER(1,2);```
- undefine a constant: ```#undef CONSTANT```
- define if CONSTANT is defined: ```ifdef CONSTANT #define CONST2```
- define if CONSTANT is not defined: ```ifndef CONSTANT #define CONSTANT 5```
- define current OS:
    ```C
    #ifdef __unix__
        #define OS 1
    #elif __WIN32__
        #define OS 0
    #else
        #define OS -1
    #endif
    ```

## pointers
```C
int number = 1;
int *aPointerToNumber = &number;
int actualNumber = *aPointerToNumber;
```

## arrays
```C
int arr[5] = 0; //create array for 5 integers
arr[0] = 1;
arr[1] = 2;
arr[4] = 5
arr[5] = 6; //ERROR because arrays begin at 0

void function(int arr[]) {/* code */} //an array is just a pointer to the first element in memory
void function2(int *arr) {/* code */} //those functions are the same
```

## function pointers
```C
int (*PtrFunction)(const char*, ...); //"..." can be any number/ kind of Arguments
PtrFunction = printf;
(*PtrFunction)("input Num: ");
PtrFunction = scanf;
(*PtfFunction)("%d, &num");
```

## enums
```C
enum MONTHS {Jan, Feb = 2, March, April = 10, Mai};
//Jan = 0; Mai = 11;
enum MONTHS m = Feb;
enum MONTHS function(void) {return Mai;}

typedef enum {Mon, Tue, Wed} DAYS; //typedef can be used if you dont want to type enum everytime
Days d = Mon
Days function(void) {return Mon;}
```

## structs
A struct can hold variables
```C
struct ABC 
{
    char A = 'x';
    char B = 'b';
    char C = 'c';
};
struct ABC myFirstABC = malloc(sizeof(ABC)); //needed memory has to be allocated
myFirstABC.A = 'a';
free(myFirstABC);

typedef struct 
{
    int A = 'a';
    int B = 'b';
    char C;
} AB; //typedef can be used if you dont want to type struct everytime
AB mySecondAB = malloc(sizeof(AB));
mySecondAB.C = 'c';
&mySecondAB->C = 'c'; // use '->' when using a pointer to the struct
free(mySecondAB);
```

## typedef
```typedef``` can be used to create an alias
```C
typedef char BYTE;
typedef float TABLE[100];
```
also see [typedef for enums](#enums) and  [typedef for structs](#structs)

## other resources
| Source | About |
| -- | -- |
[The C Programming Language](https://archive.org/details/TheCProgrammingLanguageFirstEdition) | First edition written by the author of C
[C von A bis Z](https://openbook.rheinwerk-verlag.de/c_von_a_bis_z) | German openbook
=======
# C Cheat Sheet

> C is a low-level programming language designed for cross-platform programming

| **Table of Contents** |
| -- |
[console output](#console-output)
[console input](#console-input)
[datatypes and specifiers](#datatypes-and-specifiers)
[types of datatypes](#types-of-datatypes)
[functions](#functions)
[types of functions](#types-of-functions)
[conditionals](#conditionals)
[loops](#loops)
[jump statements](#jump-statements)
[includes](#includes)
[bit-operators](#bit-operators)
[other operators](#other-operators)
[definitions](#definitions)
[pointers](#pointers)
[arrays](#arrays)
[function pointers](#function-pointers)
[enums](#enums)
[structs](#structs)
[typedef](#typedef)
[other resources](#other-resources)

## console output

| Function | Explanation |
| -- | -- |
`printf("<text>")` | output text
`printf("%x %c\n", <decimal var>, <character var>)` | output a decimal in hex, a character and a new line

## console input

| Function | Explanation |
| -- | -- |
`scanf("%c %d", <pointer to var>, &<var>)` | wait for one character, a space and a decimal
`fgets(<string var>, <length of string>, stdin)` | input a string of a specific length (better for strings due to possible buffer overflow when using scanf)

## datatypes and specifiers

| Datatype | in C | Specifiers |
| -- | -- | -- |
short integer | `short` \| `short int` | `%d` \| `%i`
integer | `signed int` \| `int` | `%d` \| `%i`
unsigned integer (>= 0) | `unsigned` \| `unsigned int` | `%u`
long integer | `long` \| `long int` | `%ld` \| `%li`
long long integer | `long long` \| `long long int` | `%lld` \| `%lli`
float | `float` | `%f`
double | `double` | `%lf`
long double | `long double` | `%Lf`
character | `char` | `%c`
| | |
string | `char[]` | `%s`
pointer | `void *` | `%p`

## types of datatypes

| Type | Usage |
| -- | -- |
`static` | won't be deleted at the end of the scope
`auto` | will be automatically deletet at the end of the scope(default)
`extern` | used if variable is in another file
`register` | tells the compiler to save variable in cpu-register which is faster then RAM (compiler will still decide)
`volatile` | always read variable from memory (mostly used for driver software)
`const` | defines a constant variable that connot be changed

## functions

| Example | Usage |
| -- | -- |
`void Hey() {printf("Hey\n");}` | function to print "Hey"
`static int Add(int n1, int n2) {return n1 + n2;}` | static function to add two numbers
`int main(){Hey(); return 0;}` | default function that will start on program start and call Hey-function

When calling a function, the compiler has to already "know" that the function exists. This can be done by writing the function above the function-call or by declaring it before: `returnType functionName(datatype1, datatype2, ...);`

## types of functions

| Type | Usage |
| -- | -- |
`static` | function scope is limited to its object file
`extern` | function can be used by other files(default)
`inline` | compiler will put code of function on function calls

## conditionals

```C
if (condition) /* code */;
```

```C
if (condition || orCondition) { /* multi line code */ }
```

```C
if (condition1) { } else if (condition2 && condition3) { } else { }
```

```C
(condition) ? /* code */ : /* else code */; a = (true) ? 1 : 0;
```

```C
switch(int/char-Variable) {
    case 1:
        /* if variable is 1 */
        break;
    case 2:
        /* if variable is 2 */
    case 3:
        /* if variable is 2 or 3 */
        break;
    default:
        /* any other case */
        break;
}
```

## loops

| Loop | Usage |
| -- | -- |
`while(condition) { /* code */ }` | run code as long as condition is true
`do { /* code */ } while (condition)` | run code as long as condition is true but at least once
`for(int i=0; i<10; i++) { /* code */}` | run code 10 times

## jump statements

| Statement | Usage |
| -- | -- |
`continue;` | stop current running loop and jump to next one
`break;` | break out of current loop
`jump label;` | jump to `label:` (should not be used)
`return;` | break out of current function
`exit;` | exit program

## includes

- include header from compiler folder: `#include <filename.h>`
- include header from current directory: `#include "filename.h"`

| `#include <...>` | Useful example | Usage |
| -- | -- | -- |
`stdio.h`
| | `printf()` | output to console
| | `scanf()` | user input from console
| | `fgets()` | user input from console
| | `fopen(file, mode)` | open file in specified mode
| | `fclose(file)` | close previously opened file
`stdlib.h`
| | `wchar_t` | 16bit unicode character
| | `EXIT_SUCCESS` | "successful" return value
| | `EXIT_FAILURE` | "not successful" return value
| | `rand()` | returns pseudo-random number
| | `srand(n)` | create new seed for rand()
| | `*malloc(x)` | allocate x bytes of memory
| | `*calloc(n, x)` | allocate x bytes of memory for n items
| | `*realloc(*ptr, x)` | reallocate x bytes and copy previously allocated memory(ptr)
| | `free(*ptr)` | deallocate previously allocated memory(ptr)
`stdint.h`
| | `intN_t` | int with N bits
| | `uintN_t` | unsigned int with N bits
| | `int_fastN_t` | fastest int with at least N bits
| | `intmax_t` | biggest possible integer
`limits.h`
| | `INT_MAX` | defined as current maximum integer
| | `INT_MIN` | defined as current minimum integer
| | `UINT_MAX` | defined as current maximum unsigned int
| | `LONG_MAX` | defined as current maximum long
`string.h`
| | `strlen(char *A)` | returns length of string A
| | `strncpy(char *A, char *B, int length)` | copy string B to A
| | `strncat(char *A, char *B, int length)` | concatenate strings
| | `strncmp(char *A, char *B, int length)` | compare strings
| | `strcspn(char *A, char *B)` | returns index of first occurrence of any char B in A
| | `strstr(char *A, char *B)` | returns pointer to first occurrence of string B in A
`ctype.h`
| | `isdigit(char)` | returns 0 if not a digit, else returns 1
| | `islower(char)` | returns 0 if not lowercase, else returns 1
| | `isupper(char)` | returns 0 if not uppercase, else returns 1
| | `tolower(char)` | returns lowercase character
`stdbool.h`
| | `bool` | boolean can be true=1 or false=0

## bit-operators

| Operator | Name | Usage |
| -- | -- | -- |
`&` | AND | if (BitA == BitB == 1) -> 1; else -> 0
`\|` | OR | if (BitA == BitB == 0) -> 0; else -> 1
`^` | XOR (eXplicit OR) | if (BitA != BitB) -> 1; else -> 0
`~` | NOT | 0->1; 1->0
`>>` | shift right | = /2 (only for positiv numbers)
`<<` | shift left | = *2 (might (buffer-)overflow)

## other operators

| Operator | Usage |
| -- | -- |
`sizeof(x)` | returns used memory of x in bytes

## definitions

- define a constant: `#define CONSTANT 5`
- define a macro: `#define OUT printf(`
  - -> `OUT "abc");`
- define a function: `#define LOWER(x,y) ((x>y) ? y : x)`
  - -> `LOWER(1,2);`
- undefine a constant: `#undef CONSTANT`
- define if CONSTANT is defined: `ifdef CONSTANT #define CONST2`
- define if CONSTANT is not defined: `ifndef CONSTANT #define CONSTANT 5`
- define current OS:
    `C
    #ifdef __unix__
        #define OS 1
    #elif __WIN32__
        #define OS 0
    #else
        #define OS -1
    #endif`

## pointers

```C
int number = 1;
int *aPointerToNumber = &number;
int actualNumber = *aPointerToNumber;```

## arrays

```C
int arr[5] = 0; //create array for 5 integers
arr[0] = 1;
arr[1] = 2;
arr[4] = 5
arr[5] = 6; //ERROR because arrays begin at 0

void function(int arr[]) {/* code */} //an array is just a pointer to the first element in memory
void function2(int *arr) {/* code */} //those functions are the same
```

## function pointers

```C
int (*PtrFunction)(const char*, ...); //"..." can be any number/ kind of Arguments
PtrFunction = printf;
(*PtrFunction)("input Num: ");
PtrFunction = scanf;
(*PtfFunction)("%d, &num");
```

## enums

```C
enum MONTHS {Jan, Feb = 2, March, April = 10, Mai};
//Jan = 0; Mai = 11;
enum MONTHS m = Feb;
enum MONTHS function(void) {return Mai;}

typedef enum {Mon, Tue, Wed} DAYS; //typedef can be used if you dont want to type enum everytime
Days d = Mon
Days function(void) {return Mon;}
```

## structs

A struct can hold variables

```C
struct ABC
{
    char A = 'x';
    char B = 'b';
    char C = 'c';
};
struct ABC myFirstABC = malloc(sizeof(ABC)); //needed memory has to be allocated
myFirstABC.A = 'a';
free(myFirstABC);

typedef struct 
{
    int A = 'a';
    int B = 'b';
    char C;
} AB; //typedef can be used if you dont want to type struct everytime
AB mySecondAB = malloc(sizeof(AB));
mySecondAB.C = 'c';
&mySecondAB->C = 'c'; // use '->' when using a pointer to the struct
free(mySecondAB);
```

## typedef

`typedef` can be used to create an alias

```C
typedef char BYTE;
typedef float TABLE[100];
```

also see [typedef for enums](#enums) and  [typedef for structs](#structs)

## other resources

| Source | About |
| -- | -- |
[The C Programming Language](https://archive.org/details/TheCProgrammingLanguageFirstEdition) | First edition written by the author of C
[C von A bis Z](https://openbook.rheinwerk-verlag.de/c_von_a_bis_z) | German openbook
>>>>>>> 95703a0df7fba85d4967a9c1997b238e93420a75
