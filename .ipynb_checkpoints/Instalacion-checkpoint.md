# Instalación


## Dependencias

La **API** de detección de objetos de Tensorflow depende de las siguientes bibliotecas:

- [x] Jupyter Notebook
- [x] Tensorflow
- [x] Pillow 
- [X] Matplotlib
- [X] lxml
- [x] tf Slim (which is included in the "tensorflow/models/research/" checkout)
- [x] Protobuf 2.6

Para más detalles sobre la instalacion de *tensorflow*, aquí [Instalación detallada de Tensorflow](https://www.tensorflow.org/install/). 
Pro lo general los comandos basicos para instalarlo son:

```
#Para CPU
pip install tensorflow

#For GPU
pip install tensorflow-gpu
```
En Ubuntu para descargar protobuf usamos:
```
sudo apt-get install protobuf-compiler python-pil python-lxml
pip install matplotlib
```

## Compilación de Protobuf

Esto nos ayuda a traducir el archivo de texto que hace tensorflow parseandolo para generar clases en C o Python.
Desde la carpeta principal hacemos lo siguiente:

```
protoc object_detection/protos/*.proto --python_out=
```
## Agregar librerias a PYTHONPATH
Es necesario para crear varios arhivos por ejemplo al crear el formato **TFRecord** para el entrenamiento, y se necesitan mandar llamar a archivos que sin esta libreria no los va a leer y nos causara muchos errores!!.

```
#From tensorflow/models/research/
export PYTHONPATH=$PYTHONPATH:`pwd`:`pwd`/slim
```
## Probando la instalación
Para corroborar si hemos instalado todo bien corremos la siguiente línea de código:
```
#From tensorflow/models/research/
python object_detection/builders/model_builder_test.py
```
Si todo salio bien nos arrojara un mensaje de que todo ha salido bien.
![](imagenes/ok.png)
