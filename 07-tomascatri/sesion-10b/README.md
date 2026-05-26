# sesion-10b

Ya que falte ese día, me pondré al día con los apuntes de mi grupo.

Vierres 22 de mayo
## Apuntes

## Encargo
**Buscar información sobre transistores y 2 opciones de chip.**

### Transistor
Para empezar, ¿qué es un transistor?

Es en esencia un grifo de agua que permite o deniega el paso, en vez de la mano, sería la electricidad.

**Tiene 2 usos principales.**
Sirve como interruptor y gracias a esto permite hacer código binario, lo cual es esencial para casi todos los dispositivos electrónicos, ya que en eso se basa todo su funcionamiento (en 1 y 0).

* Permite también amplificar la señal que se le dé, por lo que podría servir para el CD4040, que el chip tira un "1" lógico (voltaje alto), satura el transistor, este se "cierra" como un switch mecánico y deja pasar toda la corriente necesaria desde la fuente de poder hacia la etapa del oscilador sin sobrecargar al chip, esto debido a que los CD4040 tienen una salida baja de voltaje y serviría para solucionarlo.

### Chip

Para este me pareció interesante el CD4015, ya que siento que se escuchará bien con ese efecto parecido al CD4017, pero a diferencia de este, prenden y apagan en serie.

![CD4015 funcionando.](./imagenes/4015.gif)

Esta información la repito de nuevo, ya que me pareció un buen chip, pero me gustaría profundizar en cómo funcionará con los transistores.

Al activarse varios potenciómetros a la vez podría hacer que el chip se queme, por lo que aquí los transistores serán claves y funcionan así:

* El chip envía un "1" lógico (voltaje alto, por ejemplo, 9V) hacia la base del transistor.
* Al recibir ese voltaje, el transistor se activa instantáneamente (la llave de paso se abre por completo).
* Al abrirse, deja pasar el voltaje específico que tú elegiste al girar el potenciómetro 1 desde el colector hacia el emisor.
* En teoría, se deberían escuchar las 4 notas combinadas de desplazamiento que maneja.

