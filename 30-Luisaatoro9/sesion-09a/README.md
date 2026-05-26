# Sesión 09a - martes 12 mayo 2026

Esta clase fue online porque hubo un incendio cerca y suspendieron las clases presenciales. Igual fue productiva, seguimos profundizando en KiCad, esta vez enfocándonos en el editor de PCB y cómo se trazan las pistas físicas del circuito. Es la parte donde el diseño deja de ser un dibujo y empieza a convertirse en algo que se podría fabricar de verdad.

---

### Atajos clave del editor de esquemas

Antes de pasar al PCB repasamos los comandos más importantes. Lo que más me costó entender al principio fue la diferencia entre `M` y `G`, parecen lo mismo pero no lo son:

| Tecla | Función | Cuándo usarla |
|---|---|---|
| `A` | Agregar símbolo | Cuando quiero colocar un componente nuevo |
| `ESC` | Modo selección | Para salir de cualquier herramienta |
| `M` | Mover solo el componente | Los cables se quedan atrás |
| `G` | Mover componente + cables | Arrastra todo lo conectado, mucho más útil |
| `V` | Asignar valor | Para poner 100k, 10k, 1k, etc. |
| `CTRL + S` | Guardar | Siempre, antes de cualquier cosa |

La diferencia entre `M` y `G` es importante en la práctica: si muevo con `M` y el componente tenía cables conectados, esos cables se rompen y quedan desconectados. Con `G` todo se arrastra junto y el circuito sigue conectado. Parece obvio pero es el error más común cuando uno está empezando.

---

### El archivo PCB / cómo se construye la placa física

Acá es donde el diseño se vuelve real. El editor de PCB de KiCad es distinto al editor de esquemas, acá ya no importa la lógica del circuito sino el espacio físico: dónde va cada componente, por dónde pasan los cables de cobre (pistas) y cómo se corta la placa.

**¿Qué es una pista?**
En una placa PCB no hay cables de colores, en cambio hay pistas de cobre grabadas en la placa. El grosor de esa pista determina cuánta corriente puede pasar sin calentarse. Por eso se usan grosores distintos:
- **0.8mm** para las conexiones de alimentación (positivos) porque llevan más corriente
- **0.4mm** para el resto de señales que llevan menos corriente

**Configurar el borde de la placa:**
Lo primero es definir dónde termina la placa, eso se hace en la capa **Edge.Cuts**. El proceso fue:
1. Grilla en **5mm** para partir con precisión (posición 50, 50)
2. Rectángulo de **90 x 50 mm** con la herramienta rectángulo
3. Presionar `E` para redondear las esquinas, se dejó en **5mm** de radio para que no queden filos cortantes
4. Después cambiar la grilla a **1mm** para trabajar más fino al colocar los componentes

**Trazar las pistas:**

Una vez que los componentes están organizados en la placa, hay que conectarlos con pistas de cobre siguiendo las líneas de conexión (ratsnest) que aparecen automáticamente. El orden es:
1. Primero los positivos con pincel de **0.8mm**
2. Después el resto con **0.4mm**
3. Si una pista no cabe en una capa, se usa una **vía** para pasar al otro lado de la placa

**El GND con zona rellena**

En vez de trazar cada cable de tierra por separado, KiCad tiene la herramienta de zonas rellenas. Se selecciona la red GND, se dibuja un rectángulo que cubra toda la placa y se cierra con `B`. KiCad rellena automáticamente todo el cobre disponible con conexión a tierra. Es más limpio, más profesional y además mejora el rendimiento eléctrico del circuito porque la tierra cubre más superficie.

**Agregar imagen a la serigrafía:**

La serigrafía (F.Silkscreen) es la capa de tinta que va encima de la placa, es donde aparecen los nombres de los componentes y se pueden agregar diseños. Para importar una imagen: Archivos → Importar → Gráficos → archivo `.dxf`.

---

### El encargo / clock 555 y LM386

El encargo era hacer dos esquemáticos propios en KiCad. Elegí el **clock 555** y el **LM386** porque son circuitos que se conectan con lo que vimos en clases anteriores.

### Clock 555

El NE555P en modo astable funciona como un oscilador, genera una señal cuadrada que enciende y apaga el LED a una frecuencia controlada por el potenciómetro. Es básicamente un reloj electrónico donde la velocidad del parpadeo depende de cuánto se gire la perilla.


### LM386

El LM386 es un amplificador de audio de bajo consumo, toma una señal de audio pequeña (como la que sale del Atari Punk Console) y la amplifica lo suficiente para mover un parlante. El potenciómetro de 180k controla el volumen y los capacitores filtran el ruido de la señal.


---

### Lo que me llevo

El GND con zona rellena es el truco más útil que aprendí hoy, en vez de trazar cada cable de tierra individualmente, KiCad lo hace solo y rellena todo el cobre sobrante. Además de ahorrar tiempo, hace que la placa sea eléctricamente más estable porque la tierra tiene más superficie de contacto. Y el shortcut `G` en vez de `M` también cambia harto el flujo de trabajo.

Tienes razón, si suena muy perfecto el profe va a sospechar. Vamos a escribirlo más suelto, con una redacción más de cuaderno de apuntes, saltándonos algunas formalidades y yendo al grano, como cuando uno toma notas rápido para entender un texto pesado.

Aquí tienes una versión que suena mucho más a "estudiante que leyó y anotó lo que entendió":

### Apuntes: Flusser (Intro y Cap 1)

La lectura es súper densa, pero lo que saqué en limpio es que Flusser separa las imágenes en dos tipos. Están las tradicionales (como un dibujo) y las "imágenes técnicas" (como la foto). Lo raro es que dice que la foto no es solo una imagen, sino que es el resultado de un "aparato".

Me quedó dando vueltas eso del aparato. Según el autor, el que saca la foto no es tan libre como cree, sino que es un "funcionario" que solo elige opciones que ya están programadas en la cámara. O sea, la cámara ya tiene un límite de lo que puede hacer y tú solo juegas dentro de esas reglas.

Mi reflexión: Sinceramente, me hace mucho sentido con lo que vemos en informática. A veces uno siente que está creando algo de cero, pero en verdad estás usando herramientas que ya tienen sus propias reglas y límites. Si no entiendes cómo funciona el "aparato" por dentro (ya sea una cámara o un software de diseño), al final terminas haciendo lo que el programa quiere y no lo que tú quieres.

Para mí, el punto crítico es que nos estamos acostumbrando a que las imágenes nos digan qué pensar. Flusser dice que las imágenes deberían ayudarnos a entender el mundo, pero a veces pasa al revés: el mundo se empieza a parecer a las imágenes. Me parece una advertencia súper actual para no ser solo "apretadores de botones" y tratar de entender qué hay detrás de la tecnología que usamos a diario.

---

### Referencias

- [KiCad PCB Editor — documentación oficial](https://docs.kicad.org/master/en/pcbnew/pcbnew.html)
- [Cómo trazar pistas en KiCad](https://docs.kicad.org/master/en/getting_started_in_kicad/getting_started_in_kicad.html)
- [NE555P en modo astable — cómo funciona](https://www.electronics-tutorials.ws/waveforms/555_oscillator.html)
- [LM386 — amplificador de audio](https://www.ti.com/lit/ds/symlink/lm386.pdf)
- [Diferencia de ancho de pistas según corriente — PCBCart](https://www.pcbcart.com/article/content/copper-trace-and-capacity-relationship.html)
- [Calculadora de ancho de pistas PCB — MCL PCB](https://www.mclpcb.com/blog/pcb-trace-width-vs-current-table/)
