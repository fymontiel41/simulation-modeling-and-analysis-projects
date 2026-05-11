A continuación se presenta una descripción del contenido y funcionalidad de los códigos organizados por nombre de archivo.

### Histogramas_NumerosAleatorios_TransformadaFourier.ipynb

1. Código personal que calcule transformada de Fourier de una función f(x)

2. Muestra la transformada de Fourier de una Gaussiana con dispersión s y centrada en x0=0. 

    a) ¿Qué pasa si x0=1 con la transformada?
  
    b) Escoge varios valores de s, ¿Qué pasa si s=1?
  
    c) Compara lo obtenido con la función FFT 

3. Construye una caja de lado 1000 en 2 y 3 dimensiones de una distribución aletatoria de puntos.

4. Código que calcule histograma de distancias para 2d y 3d de una distribución de puntos aleatorios, 
escogiendo el tamaño de los bins, y normalizada a que su area sea 1.

### Funciones_Correlacion.ipynb

1. Crea una caja en 2d de tamaño 1000 con las siguientes distribuciones
 
    a) puntos en una malla cuadriculada de distancia (10x10 cada retícula)
  
    b) 1000 puntos sobre un disco de radio 300
  
    c) 1000 puntos sobre un anillo con radio mayor 300 y radio menor 290 
    
    d) 50 anillos con 100 untos cada uno cuyos centros están distribuidos aleatoriamente sobre la caja 

2. Algoritmo que calcula la función de correlación con DD/RR-1 con el mismo número de puntos aleatorios que datos, y comprueba que si usas muestras aleatorias la función de correlación es cero.

3. Calcula la función de correlación para cada una de las cajas de datos del inciso anterior, usando los estimadores de

    a) Peebles-Hauser
  
    b) Davis-Peebles
  
    c) Hamilton
    
    d) Landy-Szalay

Utilizando 10 veces el número de puntos en las muestras aleatorias que con los datos.

4. Se observa como cambia la función de correlación con el número de puntos aleatorios.
    a) Usando 1 archivo con 1, 5, 10 y 50 veces el número de puntos que los datos, y promedia los histogramas
    b) Usando 1 archivo con 1, 5, 10 y 50 veces el número de puntos que los datos, y promedia las funciones de correlación
    c) Usando 1, 5, 10 y 50 archivos de muestras aleatorias con el mismo número de puntos que los datos

5. Se integra la función de correlación sobre la distancia para cada estimaor del inciso 3 y considerando sólo los datos del inciso 1a, y 1d.

6. Modifica el tamaño de la caja a 2000 y 3000, manteniendo la densidad constante de puntos con respecto al inciso 1), calcula 
de nuevo las funciones de correlación para cada estimador del inciso 2) y las compara, considerando sólo los datos del inciso 1a, y 1d.

