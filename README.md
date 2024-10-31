# VC_P4

El dataset Empleado se encuentra dentro de esté link:

https://drive.usercontent.google.com/download?id=1MDU3CP5dzjGVNTFoiTLUO-1amESQewtx&export=download&authuser=0

Al dataset se ha aplicado un tratamiento para adaptarlo al formato que YOLO procesa para el entrenamiento de un modelo, para la detección de mátriculas.

Para el seguimiento de objetos empleamos dos modelos uno existente para la detección de los coches y personas y otro entrenado para la detección de matriculas. Aplicamos el modelo existente con para 2 clases personas y coches. Una vez detectado el marco de un coche dentro de este marco (el area de la imagen donde está el coche) aplicamos el modelo de entrenado para la detección de mátriculas, una vez aplicado y obtenido el area de la mátricula, aplicamos el OCR para la lectura de las letras.

Probamos varios preprocesados antes de pasar la imagen por el OCR.
- Treshhold en 127
- Treshhold otsu
- Upscaling x2 x4 x8
- Canny
- Filtro gausiano

Al final no conseguimos mejorarlo mucho y nos quedamos con el upscaling, lo demás lo descartamos.


![Captura_desde_2024-10-31_11-18-23](https://github.com/user-attachments/assets/f468741f-6bb3-4c1f-a14b-35999d5efc07)

![image](https://github.com/user-attachments/assets/f73d4a49-21dc-43bd-a3db-4395f4872e37)

Estas son las gráficas de los resultados del entrenamiento, lo más destacable es el train/box_loss y el train/cls_loss.
En el box_loss, vemos que realmente nunca llega a ser tan bueno posicionando la matrícula, pero visualmente, parece que acierta mucho más.
Por otro lado en cls_loss, vemos que es bajo, casi siempre que es una matrícula la categoriza correctamente.

![results](https://github.com/user-attachments/assets/e7b65d02-6ed9-4bf5-99fb-5bcc8249545d)

Aquí está la matriz de confusión, vemos que acierta la mayoría de las veces, aunque también da bastantes falsos positivos.

![confusion_matrix](https://github.com/user-attachments/assets/6ec21286-4ee1-40ab-85a3-7450c79a073c)
