# Proyecto Final MLII

### Descripcion:

Mejorar la velocidad y la precisión de la detección y localización de tumores cerebrales en función de las imágenes por resonancia magnética

## Clase II
### Pre-requisitos

- python --version -> Python 3.11.4

- python -m venv envmlii -> Crear environment
- Set-ExecutionPolicy Unrestricted -Scope Process
- .\envmlii\Scripts\activate -> Activar (envmlii)

- pip install pandas -> pandas==2.0.3
- pip install opencv-python -> opencv-python==4.8.0.74
- pip install matplotlib -> matplotlib==3.7.2
- pip install nbformat -> nbformat==5.9.2
- pip install scikit-image -> scikit-image==0.21.0
- pip install seaborn -> seaborn==0.12.2
- pip install tensorflow -> tensorflow==2.13.0
- pip install -U scikit-learn -> scikit-learn==1.3.0
- pip install plotly -> plotly==5.15.0
- pip install ipython -> ipython==8.14.0
- pip install keras_preprocessing -> Keras-Preprocessing==1.1.2
- pip install ipykernel -> ipykernel==6.25.0

#### Shortcut

- pip install -r .\requirements.txt # Ejecuta todos los package

### Requisitos Kernel

- pip install -U scikit-learn # Successfully installed joblib-1.3.1 scikit-learn-1.3.0 threadpoolctl-3.2.0
- deactivate
- .\envmlii\Scripts\activate
- ipython kernel install --user --name=envmlii -> Kernel del proyecto: Installed kernelspec envmlii in C:\Users\nicom\AppData\Roaming\jupyter\kernels\envmlii


## Clase III 
### Comienzo de Actividades
#### Carga de Librerias y Dataframe
- Se cargan las librerias necesarias para el proyecto.
- Se crea un datafame con: id, path de imagen, path de mascara y valor de marcasa.
- Muestras no estan balanceadas, 65% sin tumor. Seria optimo mejor porcentaje con tumor.

#### Visualizacion de datos:
- Se muestra el archivo del dataframe: 3928 filas y 4 columnas. Marcara 0 sin tumor, Marcara 1 con tumor.
- Se realiza un grafico de barras que muestra la distribucion de datos de la mascara.
- Se comienzan a analizar las muestras, viendo imagenes junto con las imagenes de mascara.
- Se realizan muestras de imagenes aleatorias, juntando la imagenes y generar el resultado.

## Clase IV
### Entrenamiento de Modelo
#### Para detectar si existe o no el tumor en la imagen del paciente
- Se elimina la columna con el id del paciente y creamos un nuevo dataframe, no necesaria para el entrenamiento.
- Se convierten los datos del dataframe a string.
- Se dividen los datos para entrenamiento y para posterior testing(15%). 
- Se estandarizan el tamaño de las imagenes a utilizar. Los datos de entrenamiento a su vez, se reserva un 15% para validar el entrenamiento. 
- Usamos como base la ResNet50.
- Se agrega la cabecera de clasificacion.
- Se compila el modelo.
- Se realiza el entrenamiento. Se guarda los datos en un archivo tipo json.
- Se modifica la arquitectura y se vuelve a entrenar: 25 Epocas.  1803s 10s/step - loss: 0.2128 - accuracy: 0.9245 - val_loss: 0.2250 - val_accuracy: 0.9073. Se vuelve a guardar.
- Hacemos la prediccion con las imagenes de testeo: 
- Evaluamos el resultado del modelo entrenado, tasa de acierto: 0.9027777777777778
 				precision    recall  f1-score   support

           0       0.91      0.94      0.93       375
           1       0.88      0.83      0.86       201