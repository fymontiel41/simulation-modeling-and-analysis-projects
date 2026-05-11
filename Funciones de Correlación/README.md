A continuación se presenta una descripción del contenido y funcionalidad de los códigos organizados por nombre de archivo.

### Histogramas_NumerosAleatorios_TransformadaFourier.ipynb

1. Código personal que calcula la transformada de Fourier de una función f(x)

2. Muestra la transformada de Fourier de una Gaussiana con dispersión s y centrada en x0=0. 

    a) ¿Qué pasa si x0=1 con la transformada?
  
    b) Escoge varios valores de s
  
    c) Compara lo obtenido con la función FFT

3. Construye una caja de lado 1000 en 2 y 3 dimensiones de una distribución aletatoria de puntos.

4. Código que calcula el histograma de distancias para 2d y 3d de una distribución de puntos aleatorios, 
escogiendo el tamaño de los bins, y normalizada para que su area sea 1.

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

### Espectro_Potencias.ipynb

1. Encuentra el espectro de potencias en 1d, 2d y 3d para la función de correlación 

<img src="https://latex.codecogs.com/gif.latex?\xi(r)=\left(\frac{r}{r_0}\right)^{-\gamma}" title="\xi(r)=\left(\frac{r}{r_0}\right)^{-\gamma}" /> 

2. Calcula el espectro de potencias para las distribuciones que se realizo en Funciones_Correlacion.ipynb

<img src="https://latex.codecogs.com/gif.latex?\hat{P}(\mathbf{k})=V\left&space;|&space;\frac{1}{N}\sum_{i=gal}^N&space;e^{-i&space;\mathbf{k\cdot&space;x}}\right&space;|^2&space;-\frac{V}{N}" title="\hat{P}(\mathbf{k})=V\left | \frac{1}{N}\sum_{i=gal}^N e^{i \mathbf{k\cdot x}}\right |^2 -\frac{V}{N}" />

  a) Determina un rango en k y usa 20-100 bins en kx y ky. 
  
  b) Obtiene la transformada de Fourier de estos espectros y comparas con las funciones de correlación de Funciones_Correlacion.ipynb
  

### Corrimiento_Rojo.ipynb

1.  Genera datos con “corrimiento al rojo” para los datos del Anillo en 2d. Para ello se crea un mapa de velocidad: 
en una vecindad de L/10 de cada punto "pivote" en los datos, encuentra el punto más cercano y generar una velocidad 
para este punto pivote en la dirección del punto más cercano proporcional a su distancia (v=100/dist). 
Guardar el nuevo punto con coordenadas    <img src="https://latex.codecogs.com/gif.latex?\mathbf{r}=(x,&space;y&plus;v\cdot\hat{i})" title="\mathbf{r}=(x, y+v\cdot\hat{i})" />. 


2. Cambiar el código de la función de correlación con estimador de Landy-Salay, para que sea anisotrópico y guarde la componente 
de cada distancia en X y Y. 

   a) Con este código calcula la función de correlación anisotrópica del inciso anterior 
   y la muestra la gráfica de densidad en 2d 


### Correlaciones_Pesadas.ipynb

1. Pesos en la función de correlación (estimador de Landy-Salay)

    a) Construye dos anillos concéntricos de radios distintos y ancho fijo, pero que el radio mayor del anillo más pequeño sea igual al radio menor del anillo más grande (ie ambos anillos se ven como un solo anillo del doble de ancho). La densidad de ambos anillos es igual. Grafica la distribución poniendo color rojo a los puntos del anillo pequeño y azul a los del grande.
        
    b) Mide la función de correlación asignando los siguientes pesos a cada punto: para puntos en el anillo pequeño (rojos) usa un peso de 2, mientras que para puntos en el anillo grande (azules) usa 1/2. Sobrepone en una gráfica la función de correlación sin pesos con la de pesos, y describe las diferencias en palabras.
        

2.  De partículas a una malla. Usa la rutina [scipy.interpolate.griddata](https://docs.scipy.org/doc/scipy/reference/generated/scipy.interpolate.griddata.html). 

    a) Crea una malla de 100x100, e interpola los datos del anillo y de los multiples anillos a esta malla. Grafíca los datos de la malla como gráfica de densidad y pon los puntos originales encimados. A esta malla y sus valores, se le dice el campo. Utiliza los tres métodos de interpolación: más cercano, lineal y cúbico 1D.
    
    b) Calcula la función de correlación (estimador de Landy-Salay) para ambas muestras de datos usando los putos de la malla, y asignando un peso en cada punto dado por el valor del campo en ese punto. Grafica la función de correlación obtenida por este método de malla y la compara en la misma gráfica con la obtenida en base a los puntos originales. 
    
    c) Calcula la transformada de Fourier de este campo discreto (ie de la malla) para ambas muestras de datos, y obtiene los espectros de potencia como el valor de expectación del producto de dos campos en este espacio de Fourier. Gráfica tanto el campo en el espacio de Fourier, como el espectro de potencias. 
    
    c) Utiliza la transformada de Fourier inversa para encontrar la función de correlación a partir de los espectros de potencia anteriores, y compára con los obtenidos en el inciso b).

