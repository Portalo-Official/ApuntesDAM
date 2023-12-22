---
sticker: lucide//settings
---

## ¿De que rollo va TypeScript? 

TypeScript tiene la misión de tipar los datos, cosa que no se hace en javaScript. Cuando escribimos en ts (typescript), a la hora de la verdad, lo que acaba de ejecutandose es un archivo js ( javaScript). Cuando acabamos un archivo tsc, lo convertimos a js mediante el comando tsc.

![[tscmanual.png]]

en este ejemplo pasamos de un archivo ts a js:

![[pasarTsAJs.png|350]]


## Configuración Directorios

Al la hora de montar una aplicación o proyecto, debes tener en cuenta que estos archivos y directorios tienes que estar al mismo nivel de la carpeta raíz

![[configuracion_directorios.png]]

La imagen es un ejemplo de un proyecto, donde tenemos en el **mismo nivel** los siguientes elementos:
- Archivo de configuración *tsconfig.json*
- *src* (archivos typescript)
- *bin* (otra convención para los archivos javaScript)
- *.vscode* (carpeta para depuraciones)
- *node_modules* (carpeta de paquetes de node.js).

## Configuración de TypeScript 

TypeScript tiene una configuración customizable, esto quiere decir que podemos cambiar la forma de escribir en él para ser más permisivos o menos permisivos. 

Para ello, se usa un archivo de configuración llamado tsconfig.json, este archivo se genera con el comando: 

`{bash}tsc -init                                                          `


![[tsc-init_tsconfig.png]]

Una vez hecho esto, tendremos en nuestro directorio el archivo 

![[archivo_tsconfigJSON.png]]

En este archivo nos encontraremos tantas opciones que ni los de TypeScript se las saben…
Cuando tengamos que cambiar alguna la cambiaremos.

#### Comando tsc

- el comando *tsc* sin nada mas hará las conversiones necesarias, con la configuración asignada

*Nota*: Si ahora tuviéramos un ts fuera de src (menos en dist), en el mismo nivel de tsconfig.json, nos saltara error de que no todos los archivos están en src.

### Parámetros básicos en tsconfig.json

- línea 14 target: indicar a que versión de js se está transcribiendo.
- línea 29 rootDir: indica al proyecto, donde se encuentran los archivos de Typescript. 
- línea 58 outDir: indica dónde se generan los archivos js transcritos.
- línea 59 removeComments: eliminar comentarios del ts en el archivo js.
- línea 71 noEmitOnError: Si el código fuente de ts tiene algún error, este parámetro indicará si se transcribe o no a js.

##### target

Indica la version en la que se transcriben los archivos javaScript.
![[parametro-target.png|500]]

##### strict

Obliga de manera **estricta** todas las opciones estrictas de verificación de tipo

![[parametro-strict.png]]

##### rootDir

Indica donde están los archivos typeScript del proyecto.

![[parametro-rooDir.png|500]]

##### outDir y removeComments

OutDir -> indica donde se almacenan los archivos js transcritos.

El directorio *dist es una convención*.

removeComments -> Elimina los comentarios del archivo Ts en el archivo Js.

![[parametro-outDir.png|500]]


##### noEmitOnError

No se puede emitir el archivo js si hay errores de tipado.
Desactiva el poder convertir a js si hay algún error en los type-checking.

![[parametro-noEmitError.png|500]]


### Otros Parámetros

Aquí se nombrarán otros parámetros usados a lo largo de los apuntes.
##### sourceMap

indicara a VsCode como se mapea los archivos de ts a los archivos de js.

![[parametro-sourceMap.png]]

compilar el código con este parámetro en true, genera un archivo .js.map.

Este archivo no esta en alto lenguaje, es para que lo entienda la maquina, no el humano.

##### noImplicitAny

True -> Arroja Error cada vez que este un tipo any de manera implícita.

False -> Permite que las variables sean tipo [[02 Tipo any|any]] de manera implícita. 
**Nota**: Es totalmente desaconsejable esto. Pues pierde la misión de TS.

![[parametro-noImplicitAny.png]]

Al esta en false tanto *strict* como este, si generamos aposta una variable any de manera implícita, no nos arroja error pero el sistema nos aconseja no hacer esto.
![[consejo-anyimplicito.png]]

##### noUnusedParameters

Lanza un error cuando una función no usa un parámetro. 
Se habilita para las [[07 Funciones#Undefined|funciones]].

![[parametro-noUnusedParameters.png]]

##### noImplicitReturns

Lanza error si la función manda un error de manera implícita.
Se habilita para las [[07 Funciones#Undefined|funciones]].

![[parametro-noImplicitReturns.png]]