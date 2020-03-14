# Puzzle-slide-IA
Puzzle slide IA Photo



**Inteligencia Artificial Eduardo Zurek, PH.D** 🚀
***UNIVERSIDAD DEL NORTE***
**Abraham Lugo Ramírez**
**Elkin Rodríguez Pérez**
**Cristian Zapata Lázaro**
# 📋
En el presente reporte se va a hablar sobre el problema del 8-puzzle-Slide para ordenar una imagen y la respectiva solución. El programa se implemento usando **Jupyter** y desarrollado en **Google Collaboratory**, con el lenguaje **Python**. Se usaron las siguientes librerías:
- from PIL import Image
- from itertools import groupby
- import matplotlib.pyplot as plt
- import numpy as np
- import math
- import random
- import matplotlib.pyplot as plt
- import matplotlib.image as mpimg

Inicialmente, se sube una imagen de 300x300 pixeles en formato bmp, la cual se cortará en 9 pedazos. Después se crearán 9 imágenes tipo RGB a las cuales se le asignará a cada una un pedazo de la imagen cortada inicialmente. (Sección 1). Después de eso, se crea una nueva imagen con los pedazos que se crearon anteriormente. (Sección 2).

![enter image description here](https://raw.githubusercontent.com/AbrahamLugoRamirez/Puzzle-slide-IA/master/cuadro3x3.jpg)

En la siguiente sección se van a comparar los pixeles para ver cómo se puede ordenar la imagen. Primero se tienen los vectores **R, G, B**, estos se van a usar para comparar todas las imágenes que se crearon en lo último de la sección 1. ⚙️

Comparamos toda la ultima columna de la image1 con la primera columna de la imag2
![enter image description here](https://raw.githubusercontent.com/AbrahamLugoRamirez/Puzzle-slide-IA/master/Opc1.png)



Comparamos toda la ultima fila de la image1 con la primera fila de la imag2.
![enter image description here](https://raw.githubusercontent.com/AbrahamLugoRamirez/Puzzle-slide-IA/master/Opc2.png)


Comparamos toda la primera columna de la image1 con la ultima columna de la imag2.
![enter image description here](https://raw.githubusercontent.com/AbrahamLugoRamirez/Puzzle-slide-IA/master/Opc3.png)



Comparamos toda la primera fila de la image1 con la ultima fila de la imag2.
![enter image description here](https://raw.githubusercontent.com/AbrahamLugoRamirez/Puzzle-slide-IA/master/Opc4.png)

Las imágenes se van a comparar en grupos de 2 usando los pixeles. Primero se van a obtener los píxeles de cada imagen y luego se va a sacar la ***media*** y la ***varianza muestral***. La media se agregará a los respectivos vectores **R, G, B** para así poder hacer respectivas conclusiones. A partir de lo anterior se van a utilizar las imágenes creadas anteriormente para buscar el objetivo, con el cual se empezará a ordenar la imagen. (Sección 3)

$$RGB = [R,G, B]$$
$$ Media(RGB) =  \frac{Pixel1(RGB)+Pixel2(RGB)}{n}.$$
$$ Varianza(RGB) = \frac{(Pixel1(RGB)-Media(RGB))^{2}+(Pixel2(RGB)-Media(RGB))^{2}}{n-1}.$$
Ademas de usar la **media** y la **varianza muestral**, optamos por usar la **distancia euclidiana** entre estos dos puntos. Los valores de la matriz de salida representan la distancia entre cada píxel.
$$ DistanciaEuclidiana = \sqrt{\sum_{i=0}^{n}(pixel(RGB)-pixel2(RGB))^{2}}$$

Al final cuando el proceso de esta sección haya terminado con éxito, tendremos un vector con la posición inicial del **Puzzle Slide**

*Por ejemplo:*

>  **Objetivo finally** = ['4', '1', '6', '3', '8', '0', '5', '7', '2']


En la última sección se va resolver el problema planteado a partir del objetivo encontrado anteriormente. Inicialmente, se define el estado meta, el cual corresponde al estado en que la figura se encuentra totalmente ordenada.

  

>  **GOAL_STATE** = ['1', '2', '3', '4', '5', '6', '7', '8', '0']

Después de esto se va a resolver el 8-puzzle a partir del objetivo creado en la sección 3. Para resolver esto, se va a utilizar como heurística, la conocida distancia de Manhattan la cual se define como: $d(p,q) = abs(p1-q1) + abs(p2-q2).$ Aquí se van a utilizar el número de movimientos de cada pieza hasta llegar al estado meta, para ello se vá a utilizar una cola con los estados visitados. Si en los respectivos movimientos, la cola queda vacía y no se llega al estado meta, entonces, el 8-puzzle, no tendrá solución.
En lo siguiente se van a mostrar los respectivos movimientos para ordenar la imagen. En la última parte se muestra como se va ordenando la imagen a partir de los movimientos realizados anteriormente.(Sección 4).

> A* Misplaced tile solution found in: #.## seconds at # depth 
> Nodes explored: ##

**Github: [Link to respository](https://github.com/AbrahamLugoRamirez/Puzzle-slide-IA)**
