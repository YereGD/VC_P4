# VC_P4

El dataset Empleado se encuentra dentro de esté link:

https://drive.usercontent.google.com/download?id=1MDU3CP5dzjGVNTFoiTLUO-1amESQewtx&export=download&authuser=0

Al dataset se ha aplicado un tratamiento para adaptarlo al formato que YOLO procesa para el entrenamiento de un modelo para la detección de mátriculas.

Para el seguimiento de objetos empleamos dos modelos uno existente para la detección de los coches y personas y otro entrenado para la detección de matriculas. Aplicamos el modelo existente con para 2 clases personas y coches. Una vez detectado el marco de un coche dentro de este marco (el area de la imagen donde está el coche) aplicamos el modelo de entrenado para la detección de mátriculas, una vez aplicado y obtenido el area de la mátricula Aplicamos el OCR para la lectura de las letras.



![image](https://github.com/user-attachments/assets/4617579f-55f0-42a7-8bbd-78fc183ba7b2)
