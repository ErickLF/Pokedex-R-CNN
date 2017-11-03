# Introducción 
Para poder usar tu propio conjunto de datos en el API de Object Deteccion de Tensorflow necesitamos
archivos los archivos de prueba y entrenamiento en formato **TFRecord**

## Mapas de Etiqueta (Label Maps)
Cada imagen debe tener asociada a ella un label map para que funcione el entrenamiento.
Este label map define es el vinculo entre la imagen y la clase a la que pertenece.
es un **item** con los atributos **id** y **name** cabe mencionar que siempre comienza desde el id 1. 

Los mapas de etiquetas de muestra se pueden encontrar en el proyecto de [tensorflow/models](https://github.com/tensorflow/models) 
en la carpeta: **[object_detection / data](https://github.com/tensorflow/models/tree/master/research/object_detection/data).**

## Requisitos
Para cada imagen debes tener lo siguiente:
1. Una imagen en formato .jpg o .png con un cuadro donde indique a la clase a la que pertenece y un nombre
2. Tener una carpeta de imagens con las de entrenamiento y las de prueba (train y train)
3. Instalar Label Img para crear nuestros cuadros delimitadores.
4. Generar el .xml para cada imagen.
5. Generar un archivo .csv
5. Generar el .record para realizar el entrenamiento


## Generar el archivo .xml
Para poder generar el archivo .xml el cual es el que contendra la informacion de la imagen y el
rectangulo donde detectara a nuestro objeto (pokemon).
Hay muchas formas para poder generar los rectangulos en mi caso usare la herramienta label img,
la cual la puedemos conseguir [aquí](https://github.com/tzutalin/labelImg).
Si tu conoces otra forma utilizala.

Sigue las instrucciones descritas en ese github para instalarla.
Una vez instalada abriremos nuestras imagenes bajadas de internet y empezaremos a crear los
rectangulos.
Algo asi debería de aparecer:
![](imagenes/Ejemplo_cuadro.png)

Una vez guardada la imagen nos generara un archivo .xml