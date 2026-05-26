# Sesión 10a - martes 19 mayo 2026

Esta sesión fue súper completa porque mezclamos una charla inspiradora en el auditorio con un repaso técnico bien denso en la sala, enfocado en cómo vamos a armar el proyecto final de filtros.

1. Charla en el auditorio: Escaneo LiDAR 🌸

Vinieron Jim, Patrick y Simon a mostrarnos su trabajo. Lo que más me voló la cabeza fue el modelo 3D de una flor hecho con un escáner LiDAR.

* **Dato técnico:** El láser solo captura la superficie exterior (donde rebota), por lo que el interior queda vacío. Es como una "cáscara" de puntos con colores reales y transparencias.
* **Mi lectura:** Cada punto que marca el láser es como un dato que el sistema procesa. Me hizo clic con lo que vemos en electrónica: sensores que captan la realidad y la convierten en información.

2. Pensamiento Sistémico: El "Bosque" y no solo el "Árbol" 🌲

Antes de lanzarnos a los chips, hablamos de una metodología clave: el Pensamiento Sistémico.

* **¿Qué es? Entender que todo está conectado. Si mueves una pieza aquí, hay una consecuencia allá.**
* **Ejemplo práctico:** Si mi LED no prende, el pensamiento lineal dice "el LED está quemado". El pensamiento sistémico me hace preguntar: "¿Será el código?, ¿la conexión a internet?, ¿o es que la protoboard no tiene energía?".

3. Repaso de Chips para el Proyecto de Filtros 

Después de la charla, bajamos a tierra con el profe para ver qué integrados nos sirven para "limpiar" el audio.
Los osciladores y la lógica:

* **CD4046:** Es una máquina que convierte gestos en frecuencia. A mayor voltaje, frecuencia más rápida. Es un oscilador controlado por voltaje (VCO). Según lo que entendí, sirve más para secuenciadores, así que para mi grupo de filtros quizás no sea el protagonista.
* **CD4093:** Este es pura lógica. Convierte resistencia en frecuencia.
* **CD4040 (Binary Counter):** Este es interesante. Recibe un clock y sus salidas entregan la mitad de esa frecuencia (va dividiendo). Hace que el sonido cambie según la salida que elijas (0,1,2,3,40,1,2,3,4).

Los Amplificadores Operacionales (Op-Amps) - El corazón del filtro:

Como nuestro proyecto es de filtros, necesitamos "limpiar" la señal (input y output). Estas son las opciones que barajamos:

* **TL072 / TL082:** Mis favoritos. Son de bajo ruido (ideal para audio) y traen dos operacionales en un solo chip.
* **LM358:** El plan B. Consume poquísima batería, ideal si queremos que el filtro sea portátil, aunque no es tan "limpio" como el TL072.
* **LM324:** Si el filtro es muy complejo (de cuarto orden, por ejemplo), este nos salva porque trae cuatro operacionales adentro.

Lo que me llevo hoy 

Me quedo con la frase: "No te fijes solo en los árboles, fíjate en el bosque". Entre el escaneo 3D y el diseño de circuitos, todo se resume en cómo manejamos los datos y la energía dentro de un sistema. Para el proyecto de filtros, sigo convencida de que el TL072 es nuestra mejor apuesta para que el audio suene pro.

---

### Referencias

- [Polycam — app de escaneo 3D](https://poly.cam)
- [TL072 — datasheet y aplicaciones](https://www.ti.com/lit/ds/symlink/tl072.pdf)
- [LM358 — características y usos](https://wraycastle.com/es/blogs/knowledge-base/lm358-pinout)
- [LM324 — amplificador operacional cuádruple](https://www.ti.com/lit/ds/symlink/lm324.pdf)

