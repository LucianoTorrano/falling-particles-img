# falling-particles-img
<h3>English:</h3>
<br>
Falling particles effect made with HTML5 canvas and JS. You need to transform the image from PNG format to base64 in order to use this animation and work right.
The idea of using this format (base64) its becouse you need to store information from every pixel in a matrix and then animate every pixel depending on the information
you have. If the pixel brightness is high the particle will fall slowly and you will be able to see the animation better.
<br>
<br>
<b>Here's a GIF of the particle effect (In reality the effect is more fluent, but the only way to show the effect here is with a GIF)</b>
<br>

![ezgif com-gif-maker](https://user-images.githubusercontent.com/91889090/166394861-8a6abe2e-0b53-4e4a-9064-6faa5416a962.gif)


<h3>Español:</h3>
<br>
Efecto de particulas hecho con HTML5 (canvas) y Javascript(POO). Para que la animacion funcione hay que transformar el formato original (en este caso PNG) a formato base64. Este formato es necesario ya que brinda información detallada de los pixeles, la cual es necesaria para que las funciones de renderizado del objeto canvas funcionen de forma correcta.
<br>
<br>
<b>¿Cómo funciona la animación?</b>
<br>
<br>
1) La parte del HTML es muy sencilla, simplemente creamos un objeto canvas para luego utilizar sus métodos con Javascript.<br>
2) Desde Javascript creamos un objeto 'image()' y le asignamos el código base64 donde está almacenada la imagen.<br>
3) Creamos el evento para que la animación comience cuando la imagen carge en su totalidad.<br>
4) Usamos el metodo 'drawImage()' para dibujar la imagen en el canvas. Luego la función 'getImageData()' almacenamos la informacion de cada pixel dentro de una matriz (Cada elemento de la matriz es un objeto con información).<br>
5) Descomponemos la información del color de cada pixel y dentro de un arreglo al que llamamos 'cell' guardamos en su primer posicion el brillo relativo de cada pixel (Se calcula con una formula dependiente de sus colores). Esta informacion la guardamos dentro de otro arreglo al que llamamos 'row'. Esto se repite por cada fila de pixeles (Recordá que habiamos guardado la imagen dentro de una matriz).<br>
6) Creamos la clase Particula. Cada objeto que pertenezca a esta clase tendrá una posición random en el eje X (Para dar el efecto de lluvia) y una posicíon fija en el eje Y (Queremos que todas las particulas se creen arriba de imagen). Y tendran una velocidad con la que caerán. Esta velocidad cambiara a medida que la particula caiga y dependerá del brillo que tenga cada pixel.<br>
 Esta parte es un poco confusa pero si ven en el metodo update() de la clase Particle, cuando asignamos el valor a speed
 con 'mappedImg[this.position1][this.position2][0]' En esa posición habiamos almacenado el brillo en el paso 5).<br>
7) En la función init() creamos el arreglo de particulas y finalmente en la función animate llamamos a los metodos de la clase Particle para que se actualice la posición de cada particula en la imagen.
