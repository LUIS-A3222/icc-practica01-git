# icc-practica01-git
//
- ¿Que informacion almacena un commit?
 La información actualizada de un documento
- ¿Que diferencia existe entre repositorio local y un repositorio remoto?
 Cuando es local es por que ejecutas en la maquina central y remoto es cuando te conectas a la maquina central a través de otro dispositivo
- ¿Que esperan que ocurra cuando ambos integrantes modifican archivos distintos?
 Los archivos se guardan al mismo tiempo
- ¿Que esperan que ocurra cuando ambos modifican exactamente la misma linea?
 Se suben ambos cambios por separado

## Comandos observados 
 - git pull
 - git fetch
 - git clone
 - git remote
 - git add
 - git commit 

## Planeacion
- Los pull se antes de realizar cualquier modificacion
- Los push se haran despues de cada modificacion con su respectivo comentario 
- El orden de los push y pull sera 1 a 1, empezando por programador A, al terminar el su push respectivo, el programador B hara su pull y push respectivos antes y despues de cada modificacion
- Los turnos se iran rolando 1 a 1

## Historial Esperado

```text
       --<-binario.md
      /
A--B--C--D--F <-- main
      \
       --<-decimal.md
```

## Preguntas COLABORAR, ROMPER Y REPARAR
- ¿Por qué Git rechazo el primer push de Developer B?
 Porque ya existia un commit que no estaba en el push que intento hacer DevB
- ¿Existía un conflicto de contenido?
 Porque diferentes archivos estaban a destiempo   
- ¿Qué ocurrió cuando ejecutaron pull?
 No se actualizaron los documentos que no tenian cambios 
- ¿Qué diferencia observan entre un push rechazado y un conflicto?
 El push rechazado es cuando los documentos no estan sincronizados un conflicto es cuando se generan diferentes problemas ajenos a la sincronizacion de los archivos 

## ¿Realizar un merge implica necesariamente que exista un conflicto?
No por que cuando usamos el merge se ejecuto sin ningun problema, solo hizo que los cambios ejecutados al mismo tiempo se guardaran en las ramas nuevas, ademas 
se usa para definir el orden en el que se integran las actualizaciones 

## Preguntas primer conflicto
1. ¿Que representa HEAD en este momento?
      Las secciones que tuvieron conflicto en la integracion de ramas 
2. ¿Que representa el contenido entre <<<< y =======?
      La diferencia en el primer commit al integrar las ramas 
3. ¿Que representa el contenido entre ======= y >>>>?
      La diferencia en el segundo commit al integrar las ramas 
4. ¿Por que Git no pudo decidir automáticamente que contenido conservar?
      No da mas importancia a alguno de commit y no puede decir que cambios conservar

## Historial real

```text
            --<-binario.md                                                   Y--<--Conflicto Binario A
           E--<-decimal.md     O--<-Conflicto Decimal A                     /   Z<--Conflicto---------\----
          / \                 / \                                          /   /    Binario B          \   \
A--B--C--D--F--(G--J)--K--M--N--P--Q--S------------------------------U--V--X--AA------------------------AB--AC--<-- main
                       \ /          \  \                            /  /
                        L--<-Rama    \  T--<--Conflicto Decimal D--/---
                             Binario  R--<--Conflicto -------------
                                            Decimal C
```

## Preguntas del reto 18
- ¿En que se parece al dibujo inicial?
	Tiene una estructura lineal similar
- ¿En que es diferente?
	Aumento bastante la cantidad de commits y de ramas hechas durante el proceso
- ¿Que partes del historial no habían anticipado?
	Los errores que se cometieron durante la realizacion de la practica como los errores minimos (ortograficos o estructurales) o errores grandes como cuando creamos una rama extra para el reto 14 por que salio inverso o cuando el desarrollador B tuvo problemas para que la maquina ejecutara correctamente los commits
- ¿Que entienden ahora que no entendían cuando realizaron el primer dibujo?
	La integracion de las ramas, el problema merge por que ya vemos que el sistema no le da prioridad a nadie y no elimina nada mantienendo las 2 versiones hasta que se decida cual sera la version oficial
