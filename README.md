Images were taken from this [dataset](https://www.kaggle.com/datasets/soumikrakshit/dark-face-dataset)


Procesado del histograma: 
mejor contraste y mas claridad. lo que hace es repartir el histograma maas uniformemente.
Se puede con ecualizacion del histo mejora el contraste ajustando los niveles de intensidad. Distribuye las intensidades uniformemente. Para imagenes oscuras o mal contrastadas. Si haciendo esto hay una parte que se queda muy clara y una parte que era oscura se ve mejor, podemos hacer clahe que evita que se quemen los blancos,ya que divide las imagenes en porciones que hace que se aplique la ecualizacion en varias partes separadas.

Suavizado y realce:
-suma: reducir el ruido pormediando un conjunto de imagenes ruidosas

-multiplicaciónm podemos odificar el brillo multiplicando un factor de escala. numpy.clip2543