## 2- Preprocesado de hello2.c
### Se instal� el compilador minGW para windows se modifcaron variables de entorno de windows para poder utilizar el compilador gnu c,c ++
## se ejecut� el comando cpp hello2.c > hello2.i
### Se gener� un extenso codigo, se observan path o rutas al include sobre todo a la biblioteca standard de entrada y salida
### Se observan definiciones de tipo , utilizando la palabra reservada typedef, como tambien definiciones de punteros a char
### Se oberva la salida del programa de la siguienta forma
### int main(void){
### int i=42;
### prontf("La respuesta es %d\n");
###
###Se removieron los comentarios /*medio*/ que estaban descriptos entre el int y el main


## 4- La sem�ntica de int printf(const char *s, ...); indica su prototipo o declaraci�n, en el que se escribe su nombre, su tipo de dato y los parametros que necesita
### en este caso la funci�n es printf , de tipo integer y su par�metro descripto es un puntero a un tipo de dato char, los "..." nos indica que puede recibir n cantidad de parametros.

## 5- Se ejecut� el comando cpp hello3.c > hello3.i
### Son practicamente las mismas l�neas excepto por :
### # 1 "hello3.c"
### # 1 "<built-in>"
### # 1 "<command-line>"
### # 1 "hello3.c"

## 6- compilar hello3.c sin ensamblar
### se Ejecut� el comandoo  gcc -s hello3.c
### El resultado obtenido es el error :
### hello3.c: In function 'main':
### hello3.c:4:1: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
### prontf("La respuesta es %d\n");
### ^~~~~~
### hello3.c:4:1: error: expected declaration or statement at end of input

## EL mismo nos indica que no est� impl�cita la declaraci�n de la funci�n prontf

## 7- Para generar el .s se ejecuto el comando gcc -masm=intel -S hello4.c 
### Se utiliz� ese comando ya que gcc por defecto utiliza c�digo ensamblador para un determinado procesador, 
### con el paramentro -masm=intel logramos que el codigo assembler sea el indicado para el procesador de mi computadora.

## 8- hace push del valor de la variable ebp en la pila.......

## 9- para ensamblar el archivo se utiliz� el comando as -o hello4.o hello4.s

## 10- Para vinvular se utiliz� el comando ld -o hello4 hello4.o , el cual gener� el siguiente error:
### hello4.o:hello4.c:(.text+0xa): undefined reference to `__main'
### hello4.o:hello4.c:(.text+0x1e): undefined reference to `printf'
### Estos errores referen a que el archivo no tiene incluida la bliblioteca standard por ello el linker no puede encontrar la referencia a la funcion main y printf

## 11- Se agreg� la linea #include<stdio.h>
## 12- se ejecuto el exe y se obtuvo como resultado "La respuesta es 4200768".
## 13- se corrigi� en hello6.c y se inicia el proceso nuevamente.
## 14- Funciona aunque no tenga linkeada la blibioteca standar, pero en tiempo de compilaci�n devuelve un warning que nos dice que la declaraci�n de printf esta impl�cita. Ya que el lenguaje C supone autom�ticamente la declaraci�n de printf
## como una funci�n de tipo int que puede recibir varios argumentos.

