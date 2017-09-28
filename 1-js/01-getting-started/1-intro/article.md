# Una introducción a JavaScript

Veamos qué tiene de especial JavaScript, qué podemos lograr con él y qué otras tecnologías funcionan bien con él.

## ¿Qué es JavaScript?

*JavaScript* fue creado inicialmente para *"hacer que las páginas web vivan"*.

Los programas en este idioma se llaman *scripts*. Pueden ser escritos directamente en el HTML y ejecutarse automáticamente a medida que la página se carga.

Los scripts se proporcionan y ejecutan como texto plano. No necesitan una preparación especial o una compilación para funcionar.

En este aspecto, JavaScript es muy diferente de otro lenguaje llamado [Java](https://es.wikipedia.org/wiki/Java_(lenguaje_de_programaci%C3%B3n)).


```smart header="¿Porqué <u>Java</u>Script?"
Cuando se creó JavaScript, inicialmente tenía otro nombre:"LiveScript". Pero el lenguaje Java era muy popular en ese momento, así que se decidió que posicionar un nuevo lenguaje como "hermano menor" de Java ayudaría.

Pero a medida que evolucionó, JavaScript se convirtió en un lenguaje totalmente independiente, con su propia especificación llamada [ECMAScript](http://en.wikipedia.org/wiki/ECMAScript), y ahora no tiene ninguna relación con Java.
```

Actualmente, JavaScript puede ejecutarse no sólo en el navegador, sino también en el servidor, o en cualquier dispositivo donde exista un programa especial llamado [intérprete de JavaScript](https://es.wikipedia.org/wiki/Int%C3%A9rprete_de_JavaScript).

El navegador tiene un intérprete de JavaScript incrustado, al que también se le llama "máquina virtual de JavaScript".

Distintos motores tienen diferentes "nombres en clave", por ejemplo:

- [V8](https://en.wikipedia.org/wiki/V8_(JavaScript_engine)) -- en Chrome y Opera.
- [SpiderMonkey](https://en.wikipedia.org/wiki/SpiderMonkey) -- en Firefox.
- ... Hay otros nombres en código como "Trident" o "Chakra" para diferentes versiones de IE, "ChakraCore" para Microsoft Edge, "Nitro" y "SquirrelFish" para Safari etc.

Es conveniente recordar los términos anteriores, porque se usan en artículos de desarrolladores en Internet y porque nosotros los usaremos también. Por ejemplo, si "una característica X es soportada por V8", entonces probablemente funciona en Chrome y Opera.

```smart header="¿Cómo trabaja el intérprete de JavaScript?"

Los intérpretes son complicados. Pero lo básico es fácil.

1. El intérprete (integrado si es un navegador) lee ("analiza") el script.
2. Luego convierte ("compila") el script en el lenguaje de la máquina.
3. Y entonces el código máquina se ejecuta, bastante rápido.

El intérprete aplica optimizaciones en cada etapa del proceso. Incluso observa el script compilado mientras se ejecuta, analiza los datos que fluyen a través de él y aplica optimizaciones al código máquina basadas en ese conocimiento. Al final, los scripts son bastante rápidos.
```

## ¿Qué puede hacer JavaScript en el navegador?

El JavaScript moderno es un lenguaje de programación "seguro". No proporciona un acceso de bajo nivel a la memoria o CPU, ya que inicialmente fue creado para navegadores que no lo requieren.

Las capacidades dependen en gran medida del entorno donde se ejecuta JavaScript. Por ejemplo, [Node. JS](https://wikipedia.org/wiki/Node.js) soporta funciones que permiten a JavaScript leer/escribir archivos arbitrarios, realizar peticiones de red, etc.

JavaScript en el navegador puede hacer todo lo relacionado con la manipulación de páginas web, interacción con el usuario y el servidor web.

Por ejemplo, JavaScript en el navegador es capaz de:

- Añadir nuevo HTML a la página, cambiar el contenido existente, modificar estilos.
- Reaccionar a las acciones del usuario, como ejecutar un código con un clic del ratón, movimientos del ratón o pulsaciones de teclas.
- Enviar peticiones a través de la red a servidores remotos, descargar y cargar archivos (llamadas tecnologías [AJAX](https://en.wikipedia.org/wiki/Ajax_ (programming)) y [COMET](https://en.wikipedia.org/wiki/Comet_ (programming)).
- Obtener y configurar cookies, hacer preguntas al visitante, mostrar mensajes.
- Recordar los datos en el lado del cliente ("almacenamiento local").

## ¿Qué NO PUEDE hacer JavaScript en el navegador?

Las capacidades de JavaScript en el navegador están limitadas por razones de seguridad del usuario. El objetivo es evitar que una página web maligna acceda a información privada o perjudique los datos del usuario.

Los ejemplos de tales restricciones son:

- JavaScript en una página web no puede leer/escribir archivos arbitrarios en el disco duro, copiarlos o ejecutar programas. No tiene acceso directo a las funciones del sistema operativo.

    Los navegadores modernos le permiten trabajar con archivos, pero el acceso es limitado y sólo se proporciona si el usuario realiza ciertas acciones, como "soltar" un archivo en una ventana del navegador o seleccionarlo a través de una etiqueta `<input>`.
    
    Hay maneras de interactuar con la cámara/micrófono y otros dispositivos, pero requieren el permiso explícito del usuario. Por lo tanto, una página habilitada para JavaScript no puede activar la cámara web, observar el entorno y enviar la información a la [NSA](https://en.wikipedia.org/wiki/National_Security_Agency).
- Las diferentes pestañas/ventanas generalmente no se conocen entre sí. A veces lo hacen, por ejemplo cuando una ventana usa JavaScript para abrir la otra. Pero incluso en este caso, JavaScript de una página no podrá acceder a la otra si provienen de sitios diferentes (de un dominio, protocolo o puerto diferente).

  Esto se llama "Política del mismo origen". Para evitarlo, *ambas páginas* deben contener un código JavaScript especial que administre el intercambio de datos.

    La limitación es otra vez para la seguridad del usuario. Una página de `http://algunsitio.com` que un usuario ha abierto no debe poder acceder a otra pestaña del navegador con la URL `http://gmail.com` y robar información de la misma.
- JavaScript puede comunicarse fácilmente a través de la red con el servidor de donde proviene la página actual. Pero su capacidad para recibir datos de otros sitios/dominios está paralizada. Aunque es posible, requiere un acuerdo explícito (expresado en cabeceras HTTP) desde el lado remoto. Una vez más, esas son limitaciones de seguridad.

![](limitations.png)

Tales límites no existen si se utiliza JavaScript fuera del navegador, por ejemplo en un servidor. Los navegadores modernos también permiten instalar plugin/extensiones que pueden obtener permisos extendidos.

## ¿Qué hace que JavaScript sea único?

Hay por lo menos tres grandes cosas sobre JavaScript:

```comparar
+ Integración completa con HTML/CSS.
+ Las cosas simples se hacen de forma sencilla.
+ Compatible con los principales navegadores y habilitado por defecto.
```

Combinadas, estas tres cosas existen sólo en JavaScript y no en ninguna otra tecnología de navegador.

Eso es lo que hace único a JavaScript. Por eso es la herramienta más extendida para crear interfaces de navegador.

Mientras planifica aprender una nueva tecnología, es beneficioso comprobar sus perspectivas. Así que pasemos a las tendencias modernas que incluyen nuevos lenguajes y capacidades de navegación.

## Idiomas "sobre" JavaScript

La sintaxis de JavaScript no se adapta a las necesidades de todos. Diferentes personas quieren diferentes características.

Eso es de esperar, porque los proyectos y requisitos son diferentes para todos.

Así que recientemente apareció una plétora de nuevos lenguajes, que son *transpilados* (convertidos) a JavaScript antes de que se ejecuten en el navegador.

Las herramientas modernas hacen que la transpilación sea muy rápida y transparente, permitiendo a los desarrolladores codificar en otro idioma y autoconvertirla "bajo el capó".

Ejemplos de estos idiomas:

- [CoffeScript](http://coffeescript.org/) es un "dulcificador de sintaxis" para JavaScript, introduce una sintaxis más corta, permitiendo escribir código más preciso y claro. Normalmente a los desarrollores de Ruby les gusta.
- [TypeScript](http://www.typescriptlang.org/) se concentra en la adición de "tipos de datos estrictos", para simplificar el desarrollo y soporte de sistemas complejos. Está desarrollado por Microsoft.
- [Dart](https://www.dartlang.org/) es un lenguaje autónomo que tiene su propio intérprete que funciona en entornos que no son navegadores (como las aplicaciones móviles). Inicialmente fue ofrecido por Google como un reemplazo de JavaScript, pero estos momentos los navegadores requieren que sea transpilado a JavaScript al igual que los anteriores.

Hay más. Por supuesto, aunque usemos uno de esos lenguajes, también deberíamos conocer JavaScript, para entender realmente lo que estamos haciendo.

## Sumario

- Javascript fue creado inicialmente como un lenguaje exclusivo del navegador, pero ahora también se utiliza en muchos otros entornos.
- En este momento, JavaScript tiene una posición única como el lenguaje de navegador más adoptado con una integración completa con HTML/CSS.
- Hay muchos lenguajes que se "transpilan" a JavaScript y proporcionan ciertas características. Se recomienda echarles un vistazo, al menos brevemente, después de dominar JavaScript.
