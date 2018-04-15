## 2- Preprocesado de hello2.c
### Se instaló el compilador minGW para windows se modifcaron variables de entorno de windows para poder utilizar el compilador gnu c,c ++
## se ejecutó el comando cpp hello2.c > hello2.i
### Se generó un extenso codigo, se observan path o rutas al include sobre todo a la biblioteca standard de entrada y salida
### Se observan definiciones de tipo , utilizando la palabra reservada typedef, como tambien definiciones de punteros a char
### Se oberva la salida del programa de la siguienta forma
### int main(void){
### int i=42;
### prontf("La respuesta es %d\n");
###
###Se removieron los comentarios /*medio*/ que estaban descriptos entre el int y el main


## 4- La semántica de int printf(const char *s, ...); indica su prototipo o declaración, en el que se escribe su nombre, su tipo de dato y los parametros que necesita
### en este caso la función es printf , de tipo integer y su parámetro descripto es un puntero a un tipo de dato char, los "..." nos indica que puede recibir n cantidad de parametros.

## 5- Se ejecutó el comando cpp hello3.c > hello3.i
### Son practicamente las mismas líneas excepto por :
### # 1 "hello3.c"
### # 1 "<built-in>"
### # 1 "<command-line>"
### # 1 "hello3.c"

## 6- compilar hello3.c sin ensamblar
### se Ejecutó el comandoo  gcc -s hello3.c
### El resultado obtenido es el error :
### hello3.c: In function 'main':
### hello3.c:4:1: warning: implicit declaration of function 'prontf' [-Wimplicit-function-declaration]
### prontf("La respuesta es %d\n");
### ^~~~~~
### hello3.c:4:1: error: expected declaration or statement at end of input

## EL mismo nos indica que no está implícita la declaración de la función prontf

## 7- Para generar el .s se ejecuto el comando gcc -masm=intel -S hello4.c 
### Se utilizó ese comando ya que gcc por defecto utiliza código ensamblador para un determinado procesador, 
### con el paramentro -masm=intel logramos que el codigo assembler sea el indicado para el procesador de mi computadora.

## 8- hace push del valor de la variable ebp en la pila.......

## 9- para ensamblar el archivo se utilizó el comando as -o hello4.o hello4.s

## 10- Para vinvular se utilizó el comando ld -o hello4 hello4.o , el cual generó el siguiente error:
### hello4.o:hello4.c:(.text+0xa): undefined reference to `__main'
### hello4.o:hello4.c:(.text+0x1e): undefined reference to `printf'
### Estos errores referen a que el archivo no tiene incluida la bliblioteca standard por ello el linker no puede encontrar la referencia a la funcion main y printf

## 11- Se agregó la linea #include<stdio.h>
## 12- se ejecuto el exe y se obtuvo como resultado "La respuesta es 4200768".
## 13- se corrigió en hello6.c y se inicia el proceso nuevamente.
## 14- Funciona aunque no tenga linkeada la blibioteca standar, pero en tiempo de compilación devuelve un warning que nos dice que la declaración de printf esta implícita. Ya que el lenguaje C supone automáticamente la declaración de printf
## como una función de tipo int que puede recibir varios argumentos.

