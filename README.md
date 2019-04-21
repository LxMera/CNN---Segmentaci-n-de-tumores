# U3-Proyecto-Redes-Convolucionales-Detección de tumores (meningiomas)
La clasificación automática del tejido canceroso en una región de interés (ROI), desempeña un papel importante en el diagnóstico asistido por computadora. En el presente estudio, nos centramos en la segmentación de tumores cerebrales de tipo meningioma, en imágenes de resonancia magnética (MRI) potenciadas en T1. El data set usado cuenta con 708 imágenes, adquiridas de una basa de datos abierta del hospital general Tianjing Medical University de China, entre los años 2005 a 2010. Las imágenes tienen una resolución en el plano de 512 × 512. El borde del tumor fue delineado manualmente por tres radiólogos experimentados, generando las máscaras de los tumores. Dentro del dataset nombrado como l1, se encuentran subcarpetas nombradas mediante números que indican la pertenencia a un paciente especifico. A su vez, esta contiene dos carpetas: imagen y mask. La carpeta imagen contiene la imagen de resonancia magnética estructural con extensión bmp, en cuanto a la carpeta mask contiene la imagen binaria de la máscara que delimita el tumor.

El proceso se llevó a cabo mediante la siguiente secuencia de trabajo.

1. Se busco un dataset con imágenes de resonancia magnetica, el dataset seleccionado fue: https://figshare.com/articles/brain_tumor_dataset/1512427/1

2. El dataset contenía la información en archivos .mat, fue necesario separar la información de estos archivos y guardarla en carpetas separadas.

3. Se uso el algoritmo Extraer_imagen_mascaraV2.ipynb que se encuentra en este repositorio. El algoritmo además de extraer la imagen y su correspondiente mascara, se encarga de dividir la información en train y test con una proporción de 70% para train y 30% para test de manera aleatoria. 

4. El algoritmo mencionado en el punto 3 presento problemas de kernel al ejecutarse en una máquina virtual, se recomienda dividir las imágenes en tandas de 400 imágenes por cada proceso de extracción o ejecutar el código directamente sobre una computadora.

5. Después de terminar la ejecución de este código se obtienen tres carpetas, en el caso de segmentación de tumores de tipo meningioma corresponderá a la carpeta l1. Esta carpeta se compartió como dataset de análisis y se carga de manera automática en el notebook u3.Proyecto.

6. El notebook U3.Proyecto es el algoritmo encargado de la segmentación de los tumores. En el se describe de manera detallada el proceso que se llevó a cabo para ejecutar la tarea de segmentación.

7. El porcentaje de concordancia promedio obtenido en las 212 imágenes de test fue de 77%. Se considera que este promedio es representativo para ser aceptado como un algoritmo de segmentación de apoyo para la detección de cáncer de tipo meningioma.
