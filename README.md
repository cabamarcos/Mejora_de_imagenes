Images were taken from this [dataset](https://www.kaggle.com/datasets/soumikrakshit/dark-face-dataset)


Procesado del histograma: 
mejor contraste y mas claridad. lo que hace es repartir el histograma maas uniformemente.
Se puede con ecualizacion del histo mejora el contraste ajustando los niveles de intensidad. Distribuye las intensidades uniformemente. Para imagenes oscuras o mal contrastadas. Si haciendo esto hay una parte que se queda muy clara y una parte que era oscura se ve mejor, podemos hacer clahe que evita que se quemen los blancos,ya que divide las imagenes en porciones que hace que se aplique la ecualizacion en varias partes separadas.

Suavizado y realce:
-suma: reducir el ruido pormediando un conjunto de imagenes ruidosas

-multiplicaciónm podemos odificar el brillo multiplicando un factor de escala. numpy.clip


# Métodos aritméticos para mejorar la visibilidad de una imagen oscura
1. Suma o Promedio de Imágenes
Puedes sumar o promediar dos imágenes para aumentar la luminosidad. Por ejemplo:

Imagen A: Imagen original (oscura).
Imagen B: Otra versión modificada, como una imagen en la que se ha aumentado el brillo o contraste.
```python

import cv2
import numpy as np

# Cargar imágenes
image1 = cv2.imread('oscura.jpg', cv2.IMREAD_GRAYSCALE)
image2 = cv2.imread('brillante.jpg', cv2.IMREAD_GRAYSCALE)

# Sumar las imágenes
result = cv2.addWeighted(image1, 0.5, image2, 0.5, 0)

cv2.imshow('Mejorada', result)
cv2.waitKey(0)
cv2.destroyAllWindows()
``` 

Este método ayuda a combinar ambas imágenes para obtener una imagen mejor expuesta.

2. Mejora de Contraste
Otra técnica es ajustar el contraste de la imagen, aumentando las diferencias entre las sombras y las luces:

``` python
# Ajustar contraste
alpha = 1.5  # Control del contraste
beta = 30    # Control del brillo

contrast_image = cv2.convertScaleAbs(image1, alpha=alpha, beta=beta)

cv2.imshow('Contraste Mejorado', contrast_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
``` 

3. Filtro de Promedios o Fusión de Imagen (Blending)
Se pueden fusionar imágenes mediante métodos como el fusión de imágenes, que mezcla partes específicas para mejorar la visibilidad:

``` python
# Fusión de imágenes
blended_image = cv2.addWeighted(image1, 0.7, image2, 0.3, 0)

cv2.imshow('Fusión', blended_image)
cv2.waitKey(0)
cv2.destroyAllWindows()
```