# sesion-08b

- ## KiCad pt3
  - Revisamos problemas/errores en clases que tuvimos haciendo la PCB
    - Yo tuve uno sobre "Alivio termico" e "Islas aisladas", no entendí pero me ayudaron en clases
  - Que es un boton/switch/tecla/timbre/palanca???????
    - Que es momentario/toggle/permanente????
      - Que es SPST/SPDT/DPST/DPDT?????
  - Hablamos sobre la entrega 2
    - Hacer grupos
    - Ver que hace cada grupo
    - Organizarse


- ## Revisión error
  - ![errores](./imagenes/errores.png)
    - al leer el error no entendia que significaba
      - al ver donde estaba la flecha que indica la ubicación del error no veía nada malo
        - ![pcb-error-1](./imagenes/pcb-error-1.png)
    - en clases misaaaaa me pidió ver solo la capa "B.Cu" de la placa
      - ![pcb-error-3](./imagenes/pcb-error-3.png)
        - ahí se ve que el conector del componente solo tiene 1 aliviador termico (los conectores del GND a los hoyos donde se soldan los componentes) bien conectado
          - esto ya que hay 2 pistas muy cerca de los hoyos que hacen que el GND se corte
    - al mover las pistas el problema se arregla
      - ![pcb-isla](./imagenes/pcb-isla.png)
      - ![no-errores](./imagenes/no-errores.png)
     
- ## Que es un boton/palanca?
  - vimos los distintos botones y palancas que hay
    - **botones/button** permanentes y momentarios
      - permanentes/latching se quedan en el estado al que uno lo cambia, mientras que el momentario/momentary se queda en dicho estado por un cierto momento antes de volver a la su forma común/base/normal
        - usos de los momentarios serian; timbres, botones dispensadores de bebida, click del ratón, subir el volumen etc...
        - usos de los permanentes serian; luces, emergencias, 
    - **palancas/switch**
      - estas suelen ser permanentes, como las palancas de minecraft (gracias persona que dijo eso no recuerdo quién fue exactamente)
        - usos serían; consolas de cabinas/vehículos
    - la diferencia entre ambas:
      - "Tanto los botones como los interruptores están diseñados para interrumpir o conectar un circuito eléctrico con el fin de controlar un dispositivo específico."
        - (https://www.tme.com/cl/es/news/library-articles/page/59080/interruptores-y-botones-diferencias-aplicaciones-y-principio-de-funcionamiento/)
    - buena imagen que distingue entre los distintos tipos de botones/palancas
      - ![spst-spdt-dpst-dpdt](./imagenes/spdt.jpg)
     

- ## Entrega 2
  - cada grupo (5 personas) se encarga de un modulo de los sintetizadores
    - a mi grupo nos tocó la entrada/piezo
      - ideas posibles
        - cuando el piezo detecta una señal permite que el synth avance en su sequenciador
        - que funcione más como "Taiko no Tatsujin"
          - juego de ritmo de tambores
        - que se use el input del piezo como sidechain para la señal del synth
          - (https://github.com/polykit/kosmo-sidechain/tree/main como ejemplo)
         
- ### mini extra musica importante
  - ![drug bug](./imagenes/drug-bug.jpg)
  - https://drugbug1.bandcamp.com/album/hell-for-a-basement
    - "Hell for a Basement" - drug bug
      - indie rock / art rock / alternativo / fuzzy
        - me encanta la portada
          - pintada a mano con una paleta de colores perfecta y con esos brillos y el ciervo/pudú(?)
        - me gustan mucho las progreciónes que tienen las canciónes
           - como "Hell for a Basement" en el minuto 8:45 - 10:53
    - recomiendo: "Not Worth It", "Star Sick" y "Between Months"
      - eso sí todas tienen un momento que se queda pegado en tu cabeza
        - ninguna canción se siente como si fuera de relleno
