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
-No por que cuando usamos el merge se ejecuto sin ningun problema, solo hizo que los cambios ejecutados al mismo tiempo se guardaran en las ramas nuevas, ademas 
se usa para definir el orden en el que se integran las actualizaciones 
