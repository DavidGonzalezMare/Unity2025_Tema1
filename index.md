
# Tema 1. Primer contacto con 2D

[1. Nuestro primer Proyecto](#_apartado1)
   
[2. El Entorno de Unity](#_apartado2)

[3. Imagen de fondo](#_apartado3)

[4. Nave. Nuestro primer script](#_apartado4)

[5. Creación de un enemigo con movimiento independiente](#_apartado5)

[6. Primer contacto con los prefabs](#_apartado6)

[7. Un Sprite animado](#_apartado7)

[8. Aplicando cambios al Prefab](#_apartado8)

[9. Editar propiedades desde el inspector.](#_apartado9)

[10. RigidBody 2D](#_apartado10)

[11. Añadir un disparo. Instantiate](#_apartado11)

[12. Explosión usando un sistema de partículas](#_apartado12)

[13. Reproducir un sonido](#_apartado13)

[14. Disparo de enemigos. Corrutinas](#_apartado14)

[15. Interfaz de usuario](#_apartado15)

[16. Pantalla de bienvenida](#_apartado16)

[17. Mejoras propuestas](#_apartado17)

<br>

# 1. <a name="_apartado1"></a> Nuestro primer Proyecto

Una vez tengamos instalado Unity Hub y la versión elegida de Unity, normalmente nuestra forma de empezar a trabajar será mediante Unity Hub.
Cuando entremos en Unity Hub, iremos a la pestaña Projects, que nos permitirá abrir los proyectos que tengamos, así como crear nuevos proyectos pulsando el botón New:

![Nuevo Proyecto](./images/imagen01a.jpg)

<br>

Introduciremos en la siguiente pantalla el nombre y tipo del proyecto (es posible que tengamos que descargar la plantilla):

![Template](./images/imagen01b.jpg)

<br>

Y ya podremos crearlo, en nuestro caso nuestro proyecto se va a llamar Marcianos y será un juego en 2D:

![Nuevo Proyecto](./images/imagen01c.jpg)

<br>

Durante unos instantes se cargará nuestro proyecto en el entorno de Unity…

<br>

# 2. <a name="_apartado2"></a>El Entorno de Unity

Vamos a describir brevemente las distintas zonas de la pantalla por defecto de Unity.

Si no os sale de la siguiente manera podéis cambiar en el desplegable de arriba a la derecha el Layout a Default.

![Default](./images/imagen02a.jpg)

<br>

- La zona central de la pantalla está ocupada por la zona Escena (**Scene**). En ella tendremos la parte visible de nuestro juego. Nos podremos mover por la misma y acercarnos o alejarnos para ver en detalle elementos que formarán parte del juego.
En esa misma zona, en la pestaña **Game**, se ejecutaría el juego.

- La jerarquía (**Hyerarchy**). Situada a la izquierda, contendrá los objetos que forman parte del juego. Al iniciar el proyecto únicamente nos aparece una cámara.
  
- En la parte derecha aparece el **Inspector**. En él podremos ajustar las propiedades de los objetos.

- En la parte inferior aparece el **Project**, donde estarán situados los ficheros que forman parte de nuestro proyecto, entre ellos los Assets, que como dijimos en el tema 1 son elementos que componen un juego (modelos, texturas, scripts, sonidos, animaciones…)

- La barra superior nos permite mover, rotar y cambiar el tamaño de los objetos. De momento únicamente vamos a utilizar el botón Play que nos permite ejecutar nuestro juego (de momento únicamente nos saldrá una pantalla en azul).

![Play](./images/imagen02b.jpg)

Para parar el juego pulsamos el botón Stop:

![Stop](./images/imagen02c.jpg)

<br>

# 3. <a name="_apartado3"></a>Imagen de fondo

A continuación, vamos a cambiar el **fondo** de nuestro juego (recordad que estamos realizando un juego 2d) y encuadraremos nuestra **cámara**.

Vamos a crear una carpeta en nuestro proyecto para guardar imágenes. 

En el panel inferior, dentro de **Assets**, pulsaremos el botón derecho y elegiremos la opción **Create->Folder**. Crearemos una carpeta llamada **Sprites**.

![Crear carpeta](./images/imagen03a.jpg)

<br>

Para introducir imágenes en esta carpeta las arrastraremos desde el explorador de Windows a la carpeta dentro de Unity. Se os ha dejado un fichero llamado SpaceHawks donde tenéis algunos recursos.

En nuestro caso añadiremos el fichero **fondo960.png**.
En ese momento veremos la miniatura dentro de la carpeta:

![Fondo](./images/imagen03b.jpg)

<br>

A continuación, vamos a crear un **objeto de juego (Game Object)** a partir de esa imagen. Una posible forma, y la más sencilla es arrastrar la imagen desde el panel inferior a la escena (**Scene**). De momento no queda centrado:

![Fondo](./images/imagen03c.jpg)

<br>

Para centrar la imagen vamos a utilizar el panel **Inspector** que aparece a la derecha. Recordad que el panel inspector nos permite modificar las propiedades de un **objeto**.

En este caso vamos a cambiar la propiedad transform. El **Transform** es usado para almacenar la posición, rotación y escala de un **GameObject**.

En Unity, el centro de la pantalla corresponde a las coordenadas (0,0), por lo que bastaría con cambiar el valor de X y el de Y en la posición, para hacer que ambos sean cero:

![Coordenadas](./images/imagen3d.jpg)

<br>

Una forma más rápida de hacer esto es desplegar los tres puntos que aparecen a la derecha del Transform y elegir la opción **Reset**:

![Reset](./images/imagen3e.jpg)

<br>

También vamos a cambiar el nombre del objeto de fondo960 a Fondo:

![Cambio](./images/imagen3f.jpg)

<br>

Si volvemos a lanzar el juego, se verá el fondo centrado, pero con un borde azul alrededor:

![Azul](./images/imagen3g.jpg)

<br>

Para cambiar esto, vamos a elegir la cámara (**Main Camera**) dentro de la jerarquía (panel izquierdo **Hierarchy**) y el inspector nos mostrará sus propiedades:

![Main Camera](./images/imagen3h.jpg)

<br>

Para que la cámara se ajuste mejor a nuestro fondo podemos cambiar su tamaño en el inspector con la propiedad **Size**, bien dándole un valor, o más sencillo, haciendo click con el ratón y desplazando a izquierda/derecha:

![Size](./images/imagen3i.jpg)

<br>

Quedará algo de margen por los lados, ya que el fondo está diseñado para 4:3, en lugar de 16:9.

Podemos pulsar **Play** para ver cómo está quedando el juego con el nuevo fondo…
Podemos desanclar la pantalla **Game** para verla más grande e incluso maximizarla:

![Desanclar](./images/imagen3j.jpg)

<br>

Incluso podemos elegir **Play Maximized** para ver el juego a pantalla completa.

Podemos también cambiar el color de fondo de la cámara para, por ejemplo, tener un color gris similar al del fondo:

![Color Fondo](./images/imagen3k.jpg)

Utilizamos para ello la propiedad **Background**.
Debemos ser cuidadosos a la hora de no hacer cambios durante la ejecución del juego, ya que puede ocurrir que esos cambios no se mantengan al detener la ejecución.

<br>
<br>

# 4. <a name="_apartado4"></a>Nave. Nuestro primer script.

Vamos a añadir una imagen que representará la nave que vamos a manejar.
Para ello inicialmente añadimos su imagen a la carpeta **Sprites** dentro de **Project**.

A continuación, la añadiremos como Game Object a nuestro juego. Esto lo podemos hacer arrastrando directamente a la escena, o bien arrastrando a la jerarquía (**Hierarchy**).

Al arrastrar a la escena se colocará en el sitio donde soltemos, mientras que al arrastrar a la jerarquía lo hará centrado en la posición (0, 0).

En este punto podría ocurrir que se nos solapara la imagen de la imagen con la del fondo y que no se viera. Para evitar esto (más adelante lo haremos con Layers) podemos cambiar en el inspector el **Order in Layer** a 1 de la nave.

![Order in Layer](./images/imagen4a.jpg)

<br>

Ahora vamos a mover la nave a su posición inicial en el juego. Eso lo podemos hacer de varias formas. 

Una de ellas es en el inspector, como hemos visto antes a través del **transform**, con su coordenada Y.

También lo podemos hacer utilizando la herramienta **Mover**, que tenemos en la barra de herramientas.

Aparecerán entonces dos flechas sobre el objeto que nos permitirán moverlo en horizontal o en vertical (o ambas si utilizamos el recuadro):

![Mover](./images/imagen4b.jpg)

<br>

## Moviendo la nave. Nuestro primer Script.

Para añadir comportamientos a los objetos deberemos crear un Script. En Unity los scripts determinan el comportamiento de los objetos y están escritos en **C#**.

En primer lugar, crearemos una carpeta Scripts dentro de Assets.

![Carpeta Scripts](./images/imagen4c.jpg)

<br>

Ahora seleccionaremos la nave y en el inspector pulsaremos el botón **Add Component**:

![Add Component](./images/imagen4d.jpg)

<br>

Y en el desplegable que aparece elegiremos New Script:

![New Script](./images/imagen4e.jpg)

<br>

Al cual le daremos el nombre **Nave** y lo guardaremos en la carpeta **Scripts**. Si hacemos click sobre el script **Nave**, nos aparece su contenido en el inspector:

![Script Inspector](./images/imagen4f.jpg)

<br>

Y haciendo **doble click** sobre el mismo se nos abrirá para poder editarlo.

![Visual Studio](./images/imagen4g.jpg)

<br>

En principio se debería abrir en el **Visual Studio**. En el menú **Edit->Preferences->External Tools** nos permite elegir el editor de Scripts.

Es muy posible que el editor de Visual Studio no nos haga “sugerencias” respecto al código de Unity (por ejemplo, sugerirnos los métodos del objeto transform que ya estudiaremos más adelante).

Para conseguir tener esas sugerencias debemos instalar desde el Visual Studio Installer:

![Visual Studio Installer](./images/imagen4h.jpg)

<br>

E instalar los componentes para Desarrollo de juego con Unity:

![Visual Studio Installer](./images/imagen4i.jpg)

<br>

Volviendo de nuevo al **Script** aparece la clase `Nave` que hereda de `MonoBehaviour` y con dos métodos: `Start` (se lanza al crear el objeto), y `Update` (que se lanza una vez para cada fotograma del juego).

Para mover la nave podríamos mirar las teclas individuales, pero en este caso es más útil mirar el desplazamiento horizontal que haya hecho el usuario con las teclas tanto las WASD como las flechas del teclado:

```csharp
float horizontal = Input.GetAxis("Horizontal");
```
Ese valor será negativo si el usuario ha indicado que desea moverse hacia la izquierda y positivo si ha indicado que desea moverse hacia la derecha. 

En el caso del teclado, los valores serían -1 o +1 (o 0, si no se ha indicado movimiento), pero en un joystick o gamepad analógico, podría haber valores intermedios (por ejemplo, 0.35). Si no deseamos valores intermedios, sino sólo -1, 0, +1, podríamos usar `Input.GetAxisRaw`.

Para desplazar la nave utilizaremos su posición, que forma parte de su componente `Transform`.

Utilizaremos `transform.Translate` indicando el desplazamiento en X (horizontal), en Y (vertical, que no habrá para la nave), y en Z (que no tiene sentido para el juego 2D).

```csharp
transform.Translate(horizontal, 0, 0);
```

El problema es que en las nuevas versiones de Unity esta línea no funcionaría ya que ahora por defecto se utiliza el nuevo **Input System**.

El código para poder hacer lo que queremos sería el siguiente:

```csharp
using UnityEngine;
using UnityEngine.InputSystem;

public class Nave : MonoBehaviour
{
    // Objeto al que le asignaremos el asset con el Input System
    public InputActionAsset inputActions;
    private InputAction moveAction;
    private float velocidad = 2;


    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        // Recogemos el mapa de acciones asignadas al Player
        var playerActionMap = inputActions.FindActionMap("Player");

        // Recogemos la acción mover
        moveAction = playerActionMap.FindAction("Move");
        moveAction.Enable();

    }

    // Update is called once per frame
    void Update()
    {
        Vector2 move = moveAction.ReadValue<Vector2>();
        // Si el usuario mueve en horizontal
        float horizontal = move.x;

        transform.Translate(horizontal, 0, 0);
    }
}
```

Para comprobar el resultado tendremos que **Grabar los cambios** en Visual Studio.

Y debemos asignar **en el inspector** sobre el Script del objeto Nave, el asset del nuevo Input System que se creó por defecto al crear el proyecto:

![Input System](./images/imagen4j.jpg)


Si probamos el juego ahora, veremos que el movimiento resultante es demasiado rápido, ya que dependemos de los fotogramas por segundo.

Se podría hacer que se muevan más lento, por ejemplo, multiplicando ese valor “horizontal” por un número menor que uno:


```csharp
transform.Translate(horizontal * 0.1f, 0, 0);
```

pero eso sigue sin ser una buena solución: es un movimiento que depende de la velocidad del equipo en el que se pruebe. Por eso, veremos un par de formas de hacer que ese movimiento sea estable.

## Movimiento de la nave independiente del equipo

La frecuencia con la que se llama a `Update` no será constante. 

En unos equipos más potentes se puede llamar con más frecuencia que en otros, e incluso en un mismo equipo puede ocurrir que baje la tasa de fotogramas por segundo en un momento puntual por saturación del sistema. 

Por eso, Unity ofrece formas de conseguir un movimiento estable.

Una de ellas es mirar el valor de `Time.deltaTime`, que es la cantidad de segundos que ha transcurrido desde el anterior fotograma. 

Por ejemplo, si el juego se moviese a **60 fps**, el valor de `Time.deltaTime` sería cercano a 0.01666 segundos.

De hecho, una prueba rápida puede ser mostrar en la consola de Unity el valor de `Time.deltaTime` (tiempo desde el último fotograma) y quizá también el de `1/Time.deltaTime`, que sería la cantidad de fotogramas por segundo:

```csharp
    void Update()
    {
        Debug.Log(Time.deltaTime + " seg, " + (1.0f / Time.deltaTime) + " FPS");
    }
```

La consola nos mostraría datos como estos:

![FPS](./images/imagen4k.jpg)

<br>

Como vemos, varía mucho la cantidad de fotogramas por segundo.

Para utilizar ese valor en nuestros juegos como forma de lograr una velocidad estable, crearemos un atributo para la velocidad, medida en “unidades” de pantalla por segundo, y lo multiplicaremos por el tiempo que ha transcurrido en cada fotograma, de modo que si se pasa muchas veces por “Update”, se avanzará pocos píxeles, pero si hay un retardo y se tarda más tiempo en llamar a “Update”, se avanzará puntualmente más píxeles, y la velocidad resultante será la misma, aunque el movimiento en pantalla sea más brusco:

- Si el juego va a 100 fotogramas por segundo, pasarán 10 milisegundos entre cada par de fotogramas. Si el usuario ha pulsado hacia la izquierda, la nave se moverá: -1 (valor del eje horizontal) * 2 (velocidad) * 0.010 (tiempo entre fotogramas). El movimiento en cada fotograma sería -0.020 unidades de pantalla, y al cabo de un segundo se habría movido -0.020 * 100 = -2 unidades (hacia la izquierda).
  
- Si puntualmente el juego va a 20 fotogramas por segundo, pasarán 50 milisegundos entre cada par de fotogramas, de modo que la nave se moverá: -1 (valor del eje horizontal) * 2 (velocidad) * 0.050 (tiempo entre fotogramas) = -0.100 unidades de pantalla. Después de un segundo, se habría movido -0.100 * 20 =-2 unidades, igual que en el caso anterior, pero el movimiento en pantalla sería más brusco.

Quedaría de la siguiente forma el Script:

```csharp
using UnityEngine;
using UnityEngine.InputSystem;

public class Nave : MonoBehaviour
{
    // Objeto al que le asignaremos el asset con el Input System
    public InputActionAsset inputActions;
    private InputAction moveAction;
    private float velocidad = 2;


    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        // Recogemos el mapa de acciones asignadas al Player
        var playerActionMap = inputActions.FindActionMap("Player");

        // Recogemos la acción mover
        moveAction = playerActionMap.FindAction("Move");
        moveAction.Enable();
    }

    // Update is called once per frame
    void Update()
    {
        Vector2 move = moveAction.ReadValue<Vector2>();
        // Si el usuario mueve en horizontal
        float horizontal = move.x;

        transform.Translate(horizontal * velocidad * Time.deltaTime, 0, 0);
    }
}
```

<br>
<br>

# 5. <a name="_apartado5"></a>Creación de un enemigo con movimiento independiente.

Vamos a crear un enemigo que se va a mover por sí mismo. Los pasos para hacerlo son similares a los vistos para crear la nave:

- Arrastrar su imagen a la carpeta **Sprites**.
- Crear un objeto a partir de esa imagen, y si es necesario cambiarle el nombre.
- Elegir su orden en la capa actual con la propiedad **Order in Layer**. De momento nos basta que quede por encima del fondo.
- Elegir su posición inicial en la pantalla.
- Crear un script para controlar su comportamiento. En ese script le daremos un movimiento con una velocidad determinada y cambiaremos de signo la velocidad cuando llegue a los bordes.
- Moveremos ese script a la carpeta de **Scripts**.

Si queremos que se mueva en diagonal, de modo que recorra una buena parte de la superficie de la pantalla y que pueda llegar a tocar a nuestra nave (lo que nos permitirá aprender a comprobar colisiones), podríamos preparar una velocidad en X y otra velocidad en Y, sumarlas a la posición del enemigo y cambiar su signo si alcanza algún extremo de la pantalla.

El script podría ser algo así:

```csharp
public class Enemigo : MonoBehaviour
{
    private float velocidadX = 2;
    private float velocidadY = -1.1f;

    // Start is called before the first frame update
    void Start()
    {
    }

    // Update is called once per frame
    void Update()
    {
        transform.Translate(velocidadX * Time.deltaTime,
                            velocidadY * Time.deltaTime, 0);
        if ((transform.position.x < -4) || (transform.position.x > 4))
            velocidadX = -velocidadX;
        if ((transform.position.y < -2.5) || (transform.position.y > 2.5))
            velocidadY = -velocidadY;

    }
}
```

Para las coordenadas máximas y mínimas en las que puede moverse, se puede comprobar la “rejilla” que aparece superpuesta en la escena, o bien directamente mover algún elemento, como nuestra nave, con el ratón (tras escoger la herramienta de “Mover”) a distintos puntos de la pantalla y ver qué coordenadas aparecen en el Inspector.

El centro de la pantalla coincide inicialmente con la posición (0,0), las coordenadas X crecen hacia la derecha y las Y crecen hacia arriba. Por ejemplo, en el caso de nuestro juego, tras ajustar el tamaño de la cámara, la Y de la zona visible en la cámara va desde -3 hasta +3, mientras que la X va aproximadamente desde -5 hasta +5.

<br>

## Más enemigos. Grupos de objetos.

Una posible forma de aumentar el número de objetos (enemigos en este caso), es duplicar a partir del primero en la jerarquía, mediante el botón derecho o bien con la combinación de teclas Ctrl + D:

![Duplicar](./images/imagen5a.jpg)

<br>

Los objetos quedarán al duplicarlos en la misma posición que el objeto original. Podemos moverlos:

![Duplicado](./images/imagen5b.jpg)

<br>

De momento añadiremos hasta tener 4 enemigos en total. Más adelante veremos otra forma más adecuada de realizar esto…

Conforme se vayan añadiendo objetos la jerarquía puede quedar algo saturada. Podemos crear un objeto vacío (botón derecho sobre la jerarquía, **Create Empty**) darle un nombre, por ejemplo, Enemigos, y arrastrar los enemigos a él:

![Grupo objetos](./images/imagen5c.jpg)

Cuando creemos un objeto vacío para poner en su interior otros objetos, es interesante hacer un reset de sus coordenadas, ya que las coordenadas de los objetos interiores las pone de manera “relativa”.

<br>
<br>

# 6. <a name="_apartado6"></a>Primer contacto con los prefabs.

Duplicar los objetos como hemos visto tiene un problema importante. Si en un momento dado nos interesa hacer algún cambio tendríamos que ir a los 4 objetos y hacerlo uno por uno. Imaginemos por ejemplo el caso que no hubiéramos puesto todavía el Script o quisiéramos ponerle una animación.

Para evitar ese problema podemos crear **prefabs**. Los prefabs son algo así como objetos prefabricados, a partir de los cuales podremos después crear nuevos objetos.

- En primer lugar, vamos a crear en el proyecto una **nueva carpeta llamada Prefabs** que nos va a permitir tener ordenado nuestros elementos. Borrar también los 3 enemigos nuevos que habíamos creado.
  
- A continuación, vamos a arrastrar el objeto Enemigo desde la Jerarquía, a la nueva carpeta Prefabs. Esta es la forma de crear el prefab y veremos como nuestro objeto Enemigo en la jerarquía cambia a color azul, indicando que está basado en un prefab.
  
![Carpeta prefabs](./images/imagen6a.jpg)

<br>

- Si ahora queremos crear objetos basados en ese prefab, tendremos que hacer el **proceso inverso** y arrastrar desde la carpeta Prefabs a nuestra Jerarquía (o bien a la escena):

![Crear de prefab](./images/imagen6b.jpg)

A continuación, veremos cómo modificar todos los elementos basados en un prefab, y más adelante como crear objetos desde código, en vez desde el diseño.

<br>
<br>

# 7. <a name="_apartado7"></a>Un sprite animado.

En este apartado vamos a iniciarnos en conseguir animar nuestros objetos.

Podemos hacer que los objetos del juego tengan una secuencia de fotogramas que darán una sensación de movimiento. De momento únicamente vamos a *animar* con dos imágenes. 

Abriremos la ventana de animación desde el menú **Windows->Animation->Animation** (no Animator):

![Animation](./images/imagen7a.jpg)

<br>

Aparecerá la ventana Animation y si tenemos seleccionado algún objeto o lo hacemos ahora aparecerá un botón Create:

![Animation](./images/imagen7b.jpg)

<br>

Al pulsar el botón **Create** daremos un nombre (`enemigoVolando`) a nuestra animación, aprovechando para crear y guardar la animación en una carpeta llamada **Animation** (dentro de **Assets**).

A continuación, seleccionaremos de la carpeta **Sprites** las dos o más imágenes que tenemos preparadas y las arrastraremos debajo de la línea de tiempo:

![Animation](./images/imagen7c.jpg)

<br>

Por cada fotograma que introduzcamos aparecerán dos rombos azules, que podremos desplazar para cambiar el tiempo de cada uno de ellos, para que la animación sea más o menos rápida.

Tenemos un botón Play que nos permite ver cómo está quedando la animación.
De momento solo tendrá animación el objeto que hemos elegido. En el siguiente apartado veremos cómo aplicar esta animación al resto de los enemigos.

En temas posteriores ampliaremos la utilización de animaciones.

<br>
<br>

# 8. <a name="_apartado8"></a>Aplicando cambios al prefab.

Como hemos visto en el apartado anterior los cambios que se hacen en un objeto (por ejemplo, aplicarle una animación), solamente se aplican a ese objeto.

Si queremos que ese cambio se aplique a **todos** los enemigos, lo podemos hacer aplicando los **cambios al Prefab** en el que se basan.
Si seleccionamos el enemigo que contiene la animación, podemos ver en el Inspector que la tiene, sin embargo, el resto no.

En la parte superior del inspector nos aparece indicado que ese objeto está basado en un prefab:

![Cambios Prefab](./images/imagen8a.jpg)

<br>

Si desplegamos **Overrides** nos permite aplicar los cambios que hemos realizado sobre el objeto al prefab. O revertirlos…

![Cambios Prefab](./images/imagen8b.jpg)

Al aplicarlo, todos los demás enemigos, que están basados en el prefab, también tendrán la animación, y si creamos algún enemigo nuevo, a partir del prefab, la tendrán también.

<br>
<br>

# 9. <a name="_apartado9"></a>Editar propiedades desde el inspector.

El concepto que vamos a ver en este apartado lo hemos hecho en apartados anteriores cuando asignábamos el asset de las acciones del Input System.

Unity nos permite hacer que propiedades que hayamos declarado en los Scripts de los objetos sean accesibles no solo desde código, sino también desde el editor, de manera que las podamos cambiar de forma más ágil.
Se puede hacer de dos formas:

- Declarando la propiedad como public, aunque esto hace que se pueda modificar desde otros objetos del juego.
- Etiquetando la propiedad como `[SerializeField]`, que es la que utilizaremos más a menudo.

`[SerializeField] float velocidad = 2;`

Así en el script de nuestra nave podemos cambiar la velocidad de private a `[SerializeField]`, apareciendo luego en el inspector:

![Serialize Field](./images/imagen39.jpg)

<br>
<br>

# 10. <a name="_apartado10"></a>Rigidbody 2D.

A continuación, vamos a ver cómo podemos detectar **choques** entre elementos de nuestro juego, por ejemplo, si un enemigo choca con nuestra nave.

Para ello uno de los dos objetos que chocan deben tener un cuerpo rígido (**RigidBody2d**) asociado.

Vamos a ver el objeto **Nave** centrado en la pantalla. Para ello hacemos doble click sobre la misma.

![Nave](./images/imagen10a.jpg)

<br>

Ahora, en el inspector pulsamos **AddComponent** y nos dirigimos al apartado **Physics 2D**:

![Add component](./images/imagen10b.jpg)

Y dentro de Physics 2D elegiremos **Rigidbody 2D**:

![Rigid Body](./images/imagen10c.jpg)

Si en este momento ejecutamos el juego, tenemos un pequeño problema, y es que nuestra nave se "caerá" por la fuerza de la Gravedad, ya que al añadirle un RigidBody, nuestro objeto ha pasado a tener **propiedades físicas**.

Para arreglar este "problema" podemos hacer dos cosas. 
Una es cambiar el tipo de cuerpo para que en vez de ser dinámico (dynamic), pase a ser cinemático (kinematic), de manera que no le afecten las fuerzas:

![Kinematic](./images/imagen10d.jpg)

<br>

Otra posible solución, que es la que utilizaremos, es dejar el cuerpo como Dynamic, pero hacer que no le afecte la gravedad:

![Gravity](./images/imagen10e.jpg)

## Comprobación de colisiones. BoxCollider2D

Ahora que nuestra nave ya tiene un cuerpo rígido vamos a utilizar un componente que nos va a permitir comprobar colisiones. 

Como tanto nuestra nave como los enemigos tienen aproximadamente una forma rectangular, vamos a utilizar el **BoxCollider2D**.

De nuevo lo haremos en el Inspector con **AddComponent->Physics 2D ->BoxCollider2D**.

![Box Collider](./images/imagen10f.jpg)

Alrededor del objeto aparecerá un recuadro verde que indica el collider.
Podemos ajustarlo, pero normalmente se ajustará bastante bien de manera automática…

![Recuadro](./images/imagen10g.jpg)

Solo **uno** de los elementos que participa en la colisión necesita un RigidBody, pero **ambos elementos necesitan tener un Collider** y por lo tanto, a nuestro enemigo le añadiremos un BoxCollider2D.

Es interesante hacerlo sobre el prefab, para que el cambio afecte a todos los enemigos.

Si ejecutamos el juego y la nave choca con algún enemigo, veremos que se mueve o gira.

Este comportamiento lo cambiaremos en el siguiente apartado.

## Detección de colisiones (Trigger)

En este juego no vamos a querer que los objetos se desplacen o se muevan al chocar o al ser disparados, sino que queremos que “desaparezcan” al ser tocados.

Para ello vamos a evitar que se desencadenen reacciones físicas cuando ocurra. 

Para ello activaremos el checkbox **Is Trigger** en el **BoxCollider** de la nave.

![Recuadro](./images/imagen10h.jpg)

Y además vamos a aprender a detectar la colisión en el Script correspondiente a la nave.

Lo haremos implementando el método **OnTriggerEnter2D**, en el cual de momento simplemente escribiremos un aviso en la consola.

```csharp
private void OnTriggerEnter2D(Collider2D collision)
{
    Debug.Log("Golpeado!");
}
```

![Golpeado](./images/imagen10i.jpg)

<br>
<br>

# 11. <a name="_apartado11"></a>Añadir un disparo. Instantiate.

Para empezar a crear un disparo en nuestro juego vamos a seguir unos pasos que ya hemos seguido con objetos anteriores:

- Añadir la imagen del disparo a la carpeta **Sprites** de nuestro Proyecto. Cambiar su Order in Layer.
  
- Arrastrarlo desde la carpeta Sprites a la escena, o bien a la jerarquía para crear un objeto (Game Object) a partir de la imagen.
- Añadir un **BoxCollider2D**, para que se puedan comprobar colisiones con él. Además, lo marcaremos como **IsTrigger**, ya que no queremos rebotes, sino únicamente detectar la colisión.
- Al menos uno de los objetos que participen en la colisión deben tener un **RigidBody2D**. Como los enemigos no lo tienen se lo pondremos al disparo, y le pondremos 0 en su **Gravity Scale**.

![Disparo](./images/imagen11a.jpg)

<br>

El siguiente paso consistirá en arrastrar el disparo desde la jerarquía al panel inferior para **crear un prefab**. 

A continuación, lo eliminaremos de la jerarquía ya que ahora lo crearemos **en tiempo real** de juego.

Vamos a crear un disparo cuando el jugador pulse una tecla determinada. Esto lo haremos desde el Script de la nave, mediante la sentencia Instantiate.

La sentencia Instantiate tiene tres parámetros:

- El tipo del objeto a crear.
- La posición en la que queremos que aparezca.
- Su rotación.

Esto supone una serie de pasos que tenemos que realizar para poder instanciar el nuevo disparo:

- Para crear el objeto lo haremos con un atributo accesible desde el editor con `[SerializeField]`:

`[SerializeField] Transform prefabDisparo;`

Y daríamos valor a este atributo desde el editor arrastrando el prefab de disparo hasta esa casilla:

![Arrastrar](./images/imagen11b.jpg)

<br>

- Para instanciar el disparo, la posición será la misma de la nave (`transform.position`).
  
- La rotación será **ninguna** (`Quaternion.identity`).
  
Sería por tanto algo así:

`Instantiate(prefabDisparo, transform.position, Quaternion.identity);`

Y, para detectar el momento en el que el usuario pulsa la tecla de disparo, vamos a utilizar el Input System que ya habíamos utilizado para detectar el movimiento de la nave.

Para ello vamos a detectar la acción `Attack` del playerActionMap y detectar en Update cuándo se ha disparado:

```csharp
public class Nave : MonoBehaviour
{
    // Objeto al que le asignaremos el asset con el Input System
    public InputActionAsset inputActions;
    private InputAction moveAction;
    private InputAction fireAction;

    ...

    // Start is called once before the first execution of Update after the MonoBehaviour is created
    void Start()
    {
        // Recogemos el mapa de acciones asignadas al Player
        var playerActionMap = inputActions.FindActionMap("Player");

        // Recogemos la acción mover
        moveAction = playerActionMap.FindAction("Move");
        moveAction.Enable();

        // Recogemos la acción atacar
        fireAction = playerActionMap.FindAction("Attack");
        fireAction.Enable();        
    }

    // Update is called once per frame
    void Update()
    {
        Vector2 move = moveAction.ReadValue<Vector2>();
        // Si el usuario mueve en horizontal
        float horizontal = move.x;

        transform.Translate(horizontal * velocidad * Time.deltaTime, 0, 0);

        // Detectamos en Update cuando se ha disparado
        if (fireAction.triggered)
        {
            Instantiate(prefabDisparo, transform.position, Quaternion.identity);
        }            
    }

    private void OnTriggerEnter2D(Collider2D collision)
    {
        Debug.Log("Golpeado!");
    }

}

```

Otra posibilidad es asignar un método al momento que se ejecute el `Attack` (ya no lo detectaríamos en `Update`):

```csharp
    ...
    void Start()
    {
        ...
     
        // Recogemos la acción atacar
        fireAction = playerActionMap.FindAction("Attack");
        fireAction.Enable();
        // Le asignamos un método
        fireAction.performed += ctx => OnAttack();
    }

    void OnAttack()
    {
        Instantiate(prefabDisparo, transform.position, Quaternion.identity);
    }
    ...
```
Al pulsar el botón de ataque (la tecla Enter o el botón izquierdo del ratón) aparecerá nuestro disparo (aunque de momento no se moverá, debemos mover la nave para poder verlo…):

![Disparo](./images/imagen11c.jpg)

<br>

## Movimiento del disparo. GetComponent.

En el apartado anterior hemos aprendido a crear un disparo, pero el mismo se quedaba detenido en el sitio donde se creaba. 

Vamos a hacer que se mueva cambiando sus propiedades, en este caso la velocidad.

Para poder cambiar las propiedades del disparo necesitamos guardar en una variable el objeto que genera `Instantiate`, que es del tipo `Transform`.

```csharp
Transform disparo = Instantiate(prefabDisparo, 
                    transform.position, Quaternion.identity);
```

Ahora tendremos que buscar la velocidad, del componente RigidBody2D, del GameObject asociado al disparo y decir que sea una velocidad vertical:

```csharp
disparo.gameObject.GetComponent<Rigidbody2D>().linearVelocity = 
                            new Vector3(0, velocidadDisparo, 0);
```

Siendo `velocidadDisparo` una variable privada:

`private float velocidadDisparo = 2;`

Utilizaremos en el futuro `GetComponent` para poder acceder a propiedades de objetos de nuestro juego.

Si ejecutamos nuestro juego veremos que los disparos suben verticalmente tras ser creados:

![Disparo](./images/imagen11d.jpg)

<br>

Hay un pequeño problema con los disparos y es que estos no se “destruyen” nunca, sino que siguen subiendo, aunque se salgan de la pantalla.

Para solucionar esto vamos a crear un **Script** en el prefab de Disparo.

Para crear un Script en un Prefab, simplemente lo seleccionamos y seguimos los mismos pasos que al crearlo con un objeto.

En este nuevo Script simplemente vamos a hacer que el objeto se destruya cuando supere una cierta posición:

```csharp
    void Update()
    {
        if (transform.position.y > 5)
            Destroy(gameObject);
    }
```

No es una solución demasiado elegante. Más adelante colocaremos un **collider**, y destruiremos el objeto cuando toque ese collider. 

Otra opción es utilizar el método `OnBecameInvisible` que se ejecuta cuando el objeto deja de ser visible por la cámara:

```csharp
    private void OnBecameInvisible()
    {
        //Debug.Log("Posicion: " + transform.position);
        Destroy(gameObject);
    }
```

Ya que estamos trabajando con el Script del disparo podríamos haberle puesto la velocidad en el mismo en vez de al instanciarlo en la nave, dentro de `Start`:

```csharp
    void Start()
    {       
        GetComponent<Rigidbody2D>().linearVelocity = new Vector3(0,
velocidadDisparo, 0);
    }
```
<br>

## Destruir enemigos.

Es fácil conseguir que un disparo destruya un enemigo. 

Podría bastar comprobando si el disparo colisiona con algo utilizando el método OnTriggerEnter2D en el **script del disparo** y destruyendo el objeto correspondiente:

```csharp
private void OnTriggerEnter2D(Collider2D other)
{
    Destroy(other.gameObject);
}
```

Si probamos ahora nuestro juego nos encontramos que al disparar **la Nave también se destruye**, cosa lógica ya que el disparo sale de ella.

Para solucionar este problema vamos a añadir una **etiqueta** a los Enemigos, para luego poder, mediante esa etiqueta, comprobar si el objeto con el que colisiona el disparo es de tipo Enemigo.

**Importante**. Lo vamos a hacer en el prefab. Para ello lo elegimos y nos vamos en el Inspector justo debajo del nombre donde aparece un desplegable Tag donde ya hay definidas una serie de etiquetas.

Nosotros vamos a crear una nueva:

![Etiqueta](./images/imagen11e.jpg)

<br>

Y crearemos una nueva con el nombre Enemigo:

![Etiqueta](./images/imagen11f.jpg)

<br>

Podemos elegir ahora esa etiqueta:

![Etiqueta](./images/imagen11g.jpg)

<br>

Una vez que el prefab (y por tanto todos los objetos creados a partir de él) tiene la etiqueta, podemos discriminar en el Script del disparo si el objeto colisionado es un Enemigo.

Además, destruiremos también el propio disparo:

```csharp
private void OnTriggerEnter2D(Collider2D other)
{
    if (other.tag == "Enemigo")
    {
        Destroy(other.gameObject);
        // Destruimos también el propio disparo
        Destroy(gameObject);
    }
}
```

<br>
<br>

# 12. <a name="_apartado12"></a>Explosión usando un sistema de partículas.

Vamos a crear un efecto de **explosión** usando un **sistema de partículas de Unity**.

Para ello en la jerarquía, pulsaremos el botón derecho y elegiremos la opción **Effects->Particle System**.
 
![Particulas](./images/imagen12a.jpg)

<br>

En la pantalla aparecerán unas partículas que suben hacia arriba y que como todo lo que hacemos en Unity podremos personalizar en el Inspector, donde tenemos muchas opciones para ello.
 
![Particulas2](./images/imagen12b.jpg)

<br>

Vamos a retocar algunas de estas opciones.
Para que las **partículas** no salgan solo hacia arriba, podemos usar como forma (Shape) una **Sphere** en vez de un **Cone**.
Y también podemos cambiar su **Start Color** para que sean amarillas en vez de blancas: 
 
![Particulas2](./images/imagen12c.jpg)

<br>

Podemos hacer que no se repita quitando la propiedad **Looping**, y bajar el tiempo de duración **Duration** a 1 o incluso 0.5 segundos:

![Particulas3](./images/imagen12d.jpg)

<br>

También podemos cambiarle el tiempo de vida para que las partículas no avancen tanto, de 5 a 0,2 segundos:
 
![Particulas4](./images/imagen12e.jpg)

<br>

Y para que salgan más partículas podemos cambiar dentro del apartado **Emission**, la propiedad **Rate over time** de 10 a 30:
 
![Particulas5](./images/imagen12f.jpg)

<br>

Es muy posible que necesitemos cambiar el **Order in Layer** para que aparezca por encima del fondo:
 
![Particulas6](./images/imagen12g.jpg)

<br>

Por último, nos queda **instanciar** ese sistema de partículas cuando nos interese. Para ello haremos algo parecido a lo que hicimos con el disparo.

En primer lugar, **crearemos un prefab** a partir del objeto.

A continuación, en la clase `Disparo` le añadiremos un atributo accesible desde el editor:

`[SerializeField] Transform prefabExplosion;`

Arrastraremos desde le prefab a la casilla que nos aparece ahora en Disparo para vincularlo:
 
![Particulas7](./images/imagen12h.jpg)

Y, por último, en el evento OnTriggerEnter2D de la clase disparo instanciamos para que se lance la explosión en el sitio donde está el enemigo:

```csharp
Instantiate(prefabExplosion,     
                other.transform.position, Quaternion.identity);
```

De hecho, deberíamos **destruir también el objeto explosión**.

Lo vamos a hacer con `Destroy`, que nos permite indicar cuánto tiempo debe transcurrir. Nosotros le pondremos 1 segundo, quedando así finalmente `OnTriggerEnter2D`:

```csharp
private void OnTriggerEnter2D(Collider2D other)
{
    if (other.tag == "Enemigo")
    {
        // Instanciamos la explosión.
        Transform explosion = Instantiate(prefabExplosion,
                    other.transform.position, Quaternion.identity);

        Destroy(other.gameObject);
        Destroy(explosion.gameObject, 1f);
        // Destruimos también el propio disparo
        Destroy(gameObject);
    }
}
```

<br>
<br>

# 13. <a name="_apartado13"></a>Reproducir un sonido.

Una de las formas de reproducir un sonido en Unity es hacerlo asociado a un objeto (`GameObject`). Para ello necesitamos:

- Un **Audio Listener**, encargado de lanzar la reproducción de los sonidos. Este Audio Listener viene incorporado, ya que tenemos uno en la cámara principal
  
- Un **Audio Source**, que se añade al elemento del juego que nos interese. En nuestro caso lo vamos a añadir a la nave para que haga un sonido cuando dispare. 
Lo añadiremos en el Inspector mediante el botón Add Component, buscandolo en la categoría, o tecleando en el buscador:

![Sonido1](./images/imagen13a.jpg)

<br>

El **Audio Source** tiene al incorporarlo propiedades que le permiten meter un clip de sonido (**AudioClip**), silenciarlo (**Mute**) o ejecutarlo en bucle (**Loop**):

![Sonido2](./images/imagen13b.jpg)

<br>

Para añadir el sonido crearemos una carpeta **Sounds** en los Assets y arrastraremos los clips de sonido que queramos utilizar:

![Sonido3](./images/imagen13c.jpg)

<br>

Y arrastraremos ese sonido a la propiedad AudioResource del AudioSource de la nave:

![Sonido4](./images/imagen13d.jpg)


Ya únicamente nos queda añadir el código para que se reproduzca el sonido. Lo podemos hacer dentro del método que habíamos asignado al `Attack`:

```csharp
    void OnAttack()
    {
        // Reproducimos el sonido
        GetComponent<AudioSource>().Play();

        Transform disparo = Instantiate(prefabDisparo, transform.position, Quaternion.identity);

        disparo.gameObject.GetComponent<Rigidbody2D>().linearVelocity =
                            new Vector3(0, velocidadDisparo, 0);
    }

```

Más adelante veremos otra forma de reproducir el sonido, ya que, si nuestro objeto fuera destruido, el sonido se cortará bruscamente…

<br>
<br>

# 14. <a name="_apartado14"></a>Disparo de Enemigos. Corrutinas.

Sabemos muchos de los pasos que debemos hacer para que un enemigo dispare, ya que es similar a lo que hicimos para conseguir que fuera la nave la que disparara:

- Buscar un **Sprite** que represente el disparo
  
- Crear un **GameObject** a partir de él.
- Ajustar su capa para que esté por encima del fondo.
- Añadir un **Collider**, y si fuera necesario un **RigidBody**. 
- Convertirlo en un **prefab**.
- **Instanciar** ese prefab cuando queremos que aparezca el disparo.
- Añadirle **velocidad** tras instanciarlo
- Comprobar si **colisiona** con nuestra nave.

Pero hay dos cosas que de momento no sabemos hacer:
- Cómo contar las vidas restantes cuando un disparo impacte sobre la nave, y los puntos obtenidos al darle a un enemigo. Esto lo aprenderemos más adelante.
  
- Cómo hacer que los enemigos disparen cada cierto tiempo al azar. Esto lo veremos a continuación:
  
Podríamos hacerlo generando un número al azar en el Update y si ese número supera un valor creamos el disparo. 
El problema que nos plantea es que estaríamos generando muchos números y además dependemos del número de *fps*.

Lo que vamos a hacer es **generar un número al azar** que representará un tiempo que hay que esperar, y transcurrido ese tiempo lanzaremos un método.

En Unity esto se hace:
- Llamamos a la función con `StartCoroutine`.
  
- La función que llamemos debe ser de tipo `IEnumerator`.
  
- Para hacer las pausas utilizamos `yield return new WaitForSeconds(n)`.
  
Para empezar a familiarizarnos vamos a ver en primer lugar como hacer aparecer (en el script del enemigo) un mensaje en la consola tres segundos después de que se cree un enemigo:

```csharp
void Start()
{
    StartCoroutine(Disparar());
}

IEnumerator Disparar()
{
 	yield return new WaitForSeconds(3);
    Debug.Log("Hola");
}
```

**Vamos a hacer ahora que aparezca un disparo cada cierto tiempo:**

En primer lugar, tendremos que hacer los pasos para **crear el prefab de disparo** del enemigo. 

Ya los conocemos porque son similares a los que hicimos con el disparo de nuestra nave: **crear** el objeto a partir del Sprite, asignarle un **RigidBody** con gravedad 0, crear el **prefab**, y añadirle un **script** para darle velocidad y **eliminarlo** cuando salga de la pantalla…

Una vez realizados esos pasos vamos a **instanciar el disparo** desde el Script de Enemigo. 

Lo vamos a hacer generando un **valor aleatorio entre dos valores**, e instanciaremos el prefab (recordad ponerlo como **SerializeField**) y volveremos a llamar a la función para el siguiente disparo:

```csharp
IEnumerator Disparar()
{
    float pausa = Random.Range(5.0f, 11.0f);
    yield return new WaitForSeconds(pausa);

    Transform disparo = Instantiate(prefabDisparoEnemigo,
                    transform.position, Quaternion.identity);

    // Esta línea no es necesaria si lo hemos hecho en el Start del disparo enemigo
    disparo.gameObject.GetComponent<Rigidbody2D>().linearVelocity =
                      new Vector3(0, velocidadDisparo, 0);

    // Volvemos a llamar a la Corrutina
    StartCoroutine(Disparar());
}

```
Tendríamos que implementar también qué ocurre cuando colisionamos con la nave, y destruir el disparo enemigo cuando se salga de la pantalla.

<br>
<br>

# 15. <a name="_apartado15"></a> Interfaz de Usuario.

Vamos a utilizar las herramientas de creación de interfaces de usuario dentro de la jerarquía para poder añadir un texto en el que demos información de nuestro juego (puntos, vidas, nivel…). Para ello vamos a utilizar el componente Text Mesh Pro:

![Interfaz1](./images/imagen15a.jpg)

<br>

A continuación, nos pedirá que instalemos los componentes esenciales. También se puede instalar ejemplos y extras aunque de momento no será necesario:

![Interfaz2](./images/imagen15b.jpg)

Al hacerlo aparece un **Canvas** y también un **EventSystem**. El canvas actuará como contenedor de toda la interfaz de usuario.

Si hacemos doble click sobre el **Canvas**, este aparecerá en grande y la escena de juego en pequeño abajo a la izquierda:

![Interfaz3](./images/imagen15c.jpg)

El texto puede aparecer en el centro o en un lado (podemos resetear su Transform para que aparezca centrado.)

Podemos cambiar propiedades de ese texto como su alineación, su tamaño y su color, así como el texto que aparece en el mismo:

![Interfaz4](./images/imagen15d.jpg)

Si queremos mover la posición del texto lo podemos hacer con la Herramienta mover:

![Interfaz5](./images/imagen15e.jpg)

<br>

Y podemos **anclarlo** para que no tengamos problemas con distintas configuraciones de pantalla con la propiedad **Rect Transform**. De momento lo vamos a anclar a la parte superior izquierda:

![Interfaz6](./images/imagen15f.jpg)

<br>
También podemos hacer que el **Canvas** se escale con el tamaño de pantalla:

![Interfaz7](./images/imagen15g.jpg)

<br>

A continuación, vamos a ver cómo **modificar el texto desde código**. 

Para ello debemos asociarlo a un **Game Object**. 

Como de momento no hemos creado ningún objeto que represente a toda la aplicación, lo vamos a hacer con el objeto Nave.

En el script de Nave crearemos un atributo de ese tipo. Podría ser público si lo queremos modificar desde otra clase, en otro caso nos bastaría con 

`[SerializeField] TextMeshProUGUI textoSaludo;`

Para cambiar el texto utilizaríamos la propiedad text, por ejemplo en el evento de Ataque:

```csharp
    void OnAttack()
    {
        ...

        textoSaludo.text = "Hola. Se ha pulsado el disparo";
    }

```
Pero antes de probarlo, debemos enlazar el elemento de texto que habíamos creado con el atributo en el Script de la Nave en el interfaz:

![Interfaz7](./images/imagen15h.jpg)

 
En el futuro ese texto nos servirá para poner información relevante del juego como número de vidas, puntos…

# 16. <a name="_apartado16"></a> Pantalla de Bienvenida.

Unity nos permite tener **distintas escenas** en nuestro juego, para poder por ejemplo tener varios niveles o ventanas adicionales, como bienvenida, puntuación…

Vamos a empezar cambiando el nombre de la pantalla que tenemos actualmente de SampleScene a **Nivel1**. Es importante haber **guardado** antes los cambios o se perderán.

Lo haremos en la ventana de proyecto dentro de **Assets->Scenes**.

A continuación, crearemos una nueva escena dando al botón derecho **Create->Scene**. Le podemos dar el nombre **Menu**:

![Bienvenida1](./images/imagen16a.jpg)

<br>

Al hacer doble click en ella vemos que la jerarquía está lógicamente vacía:

![Bienvenida2](./images/imagen16b.jpg)

<br>

Vamos a **añadir un texto**, y cambiar su tamaño, posición, color, texto…

![Bienvenida3](./images/imagen16c.jpg)

<br>

Ahora vamos a añadir un botón. Los pasos son parecidos. En la jerarquía pulsaremos botón derecho UI->Button - TextMeshPro.

![Bienvenida3](./images/imagen16d.jpg)

<br>

Nos aparecerá un botón con el aspecto por defecto. Vamos a cambiarle el texto, color, tamaño, posición hasta ajustarlo a lo que nos apetezca.
 
![Bienvenida5](./images/imagen16e.jpg)

<br>

Para poder cambiar el texto del botón se hace con el **Text** que “cuelga” del mismo.

Ahora debemos asociar el **evento click** de ese botón. Creamos un **script** para ese botón tal y como hemos hecho para el resto de Game Objects.

En ese script añadiremos el siguiente using:

`using UnityEngine.SceneManagement;`

y el siguiente método:

```csharp
public void LanzarJuego()
{
    SceneManager.LoadScene("Nivel1");
}
```

Ahora, **al seleccionar el botón** en la jerarquía, aparecerá en el inspector un apartado llamado **OnClick** con un símbolo + que nos permite añadir comportamientos. 

Al pulsar **+**, aparece un apartado llamado **Runtime object** en el que debemos indicarle en qué objeto tiene que buscar las funciones que se puedan asociar a ese evento **OnClick**. 

Arrastraremos el botón desde la jerarquía:

![Bienvenida6](./images/imagen16f.jpg)

<br>

Y ahora podemos desplegar la lista de funciones disponibles entre las que debería estar LanzarJuego(). La elegimos y de esa manera se asocia al click del botón:

![Bienvenida6](./images/imagen16g.jpg)

<br>

Si probamos nuestro juego, lanzándolo desde la escena **Menú**, al pulsar el botón de **Jugar** debería cargar la escena de **Nivel1**.

Podemos tener problemas a la hora de cargar escenas. Nos aparecerá el siguiente mensaje:

![Bienvenida7](./images/imagen16h.jpg)


<br>

Para solucionarlo debemos entrar en **File -> Build Profiles**.
 
Y, en el perfil de Windows añadir todas nuestras escenas:

![Bienvenida8](./images/imagen16i.jpg)

![Bienvenida9](./images/imagen16j.jpg)


 
 
# 17. <a name="_apartado17"></a> Mejoras propuestas.


Vamos a plantear una serie de mejoras que podéis realizar con los conocimientos actuales:

- Evitar que la nave salga por los **laterales**.
  
- **Sumar puntos** (por ejemplo 10) cada vez que matemos a un enemigo.
  
- Que haya más enemigos. Los podemos crear en diseño, o mediante **Instantitate**.
- Cada vez que nos golpee un disparo enemigo o un enemigo en sí, **perdamos una vida** (de un total de 3).
- Mostrar en pantalla los **puntos** y las **vidas** actuales
- Volver a la pantalla inicial si se pierden todas las vidas
- Tener **varios niveles**. Al terminar con todos los enemigos de un nivel, pasaremos al nivel siguiente. De momento para poder guardar los puntos y las vidas podemos utilizar atributos static. En el futuro veremos cómo manejar esto de otra manera.












