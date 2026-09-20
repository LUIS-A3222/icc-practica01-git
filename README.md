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

## Pregunta del reto 19
- ¿Que ventaja tiene utilizar el nombre v1.0 para identificar este punto del historial en lugar de utilizar solamente el hash del commit? hay menos etiquetas por lo que es mas facil identificar un tag que un commit, el hash del comit son numeros que no controlamos, a la etiqueta podemos asignar un valor especifico para un control preciso 

## Reflexion final

1. ¿Que información almacena un commit? Los cambios realizados en git add y un comentario 
2. ¿Que diferencia existe entre un repositorio local y un repositorio remoto? El local se guarda en el equipo y el remoto se encuentra externo
3. ¿Que ocurrió cuando modificaron archivos diferentes? Se guardan los cambios sin problemas porque no se modificaron 
4. ¿Que ocurrió cuando modificaron la misma región de un archivo? Entro el conflicto 
5. ¿Que diferencia existe entre commit y push? el commit se queda en el repositorio local y el push manda el comit al repositorio externo 
6. ¿Que función tuvo pull durante la practica? descarga los commits y actualizar los archivos de las ramas 
7. ¿Por que un push puede ser rechazado aunque no exista un conflicto de contenido? si los commits estan adelantados para proteger de cambios erroneos 
8. ¿Que representa una rama? una linea del repositorio con sus propios cambios independientes a la linea main 
9. ¿Que indica HEAD? Las secciones que tuvieron conflicto en la integracion de ramas
10. ¿Que hace merge? integra diferentes ramas en una 
11. ¿Por que Git pudo integrar algunos cambios automáticamente y otros no? porque los cambios no entraban en conflicto y modificaban archivos diferentes, al hacer modificaciones en el mismo archivo entraban en conflicto con la misma seccion
12. ¿Que representan los marcadores <<<<, ======= y >>>>? Las secciones de los commits que entran en conflicto  
13. ¿Que ventaja proporciona un tag? coloca una etiqueta en un punto especifico que lo hace mas facil de identificar 
14. ¿Como cambio su interpretación de los diagramas de historial después de utilizar git log –graph –oneline –all? las historias pueden ser mas complicadas y con mas cambios a los esperados 


