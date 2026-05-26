
# sesion-08a- lunes 28 abril 2026

Esta vez nos metimos de lleno en **KiCad** para diseñar el esquemático y la placa PCB del **Atari Punk Console**. Al principio se veía complicado pero una vez que se le agarra el ritmo tiene su lógica.

---

### ¿Qué es KiCad?

KiCad es un software gratuito y de código abierto para diseñar circuitos electrónicos y placas PCB. Tiene dos partes principales: el **editor de esquemas** (donde se dibuja cómo se conecta todo) y el **editor de PCB** (donde se diseña la placa física real).

<div align="center">

<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/68eaa548-e74a-430f-ae3a-3562e8c59a5d" />)
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/f616ea0f-a13e-47f0-bef5-8cf142666574" />
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/b992d8c8-2743-44f6-b66c-69fd399d32dc" />
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/8bbf9abf-fcec-4967-b539-5887335464ce" />
<img width="600" height="400" alt="image" src="https://github.com/user-attachments/assets/981ca00a-6a43-44c2-aa67-1e5010734aa3" />

</div>


---

### ¿Qué es el Atari Punk Console?

Es un circuito analógico clásico que genera sonidos electrónicos raros y distorsionados. Usa **dos chips NE555P** (temporizadores) conectados entre sí, uno controla la frecuencia del sonido y el otro el ancho del pulso. El resultado es ese sonido "punk" característico que se puede modificar girando dos potenciómetros.

---

### Lo que se hizo en KiCad

El proceso se dividió en pasos y había que seguirlos en orden para que todo cuadrara al final.

**Primer paso:** El esquemático

Se dibujó el circuito en el editor de esquemas de KiCad. Lo importante acá es colocar todos los componentes y después conectarlos con cables. Una vez colocados, hay que ponerles sus textos (valores) haciendo doble clic en modo selección, es recomendable que el texto sea igual al valor real del componente que se va a usar.

El circuito completo quedó con estos componentes:

| Referencia | Valor | Componente |
|---|---|---|
| BT1 | 9V | Batería |
| C1, C6 | 100n | Capacitor disco |
| C2, C7, C8 | 100u | Capacitor electrolítico |
| C3, C5 | 10n | Capacitor disco |
| D1 | LED | LED 5mm |
| LS1 | 8ohm / 3W | Parlante |
| R1, R3 | 1k | Resistencia |
| R2 | 10k | Resistencia |
| RV1, RV2 | 100k | Potenciómetro |
| U1, U2 | NE555P | Chip temporizador 555 |

**Segundo paso:** Las huellas (footprints)

Acá viene lo interesante: para pasar del diseño a la realidad hay que vincular cada símbolo del esquema con el componente físico real que se va a soldar en la placa. Eso se llama **huella** o *footprint*, básicamente le dice a KiCad qué tamaño tiene el componente real y cómo están sus patas.

La opción de huella se encuentra en la barra superior de herramientas del editor de esquemas.

<div align="center">
  
<img width="176" height="95" alt="image" src="https://github.com/user-attachments/assets/222e8bbe-5d5d-459e-af11-4153f369d37e" />

</div>

**Tercer paso:** El editor de PCB

Se abre el archivo PCB desde KiCad (o desde la barra de herramientas) y se presiona **F8** para añadir todos los componentes a la placa. Después con **ALT + 3** se puede ver el modelo 3D, ahí se ve si la placa quedó demasiado grande y hay que reducirla.

<img width="1290" height="763" alt="image" src="https://github.com/user-attachments/assets/6ac7e08f-9ff5-436d-af4c-1b0d7f53f4db" />

Para definir el borde de la placa se crea un cuadrado en la capa **Edge.Cuts** que encierre todos los componentes. Esa línea le dice a la fábrica dónde cortar la placa.

---

### Cómo quedó en 3D

Al abrir el visor 3D se puede ver la placa con todos los componentes encima, capacitores, resistencias, los dos chips NE555P, el LED y los potenciómetros. Así se puede verificar que todo esté bien ubicado antes de mandarla a fabricar.

<div align="center">

<img width="750" height="500" alt="image" src="https://github.com/user-attachments/assets/43542085-2307-4607-93eb-3b27fbafb231" />


</div>

Como dato extra: si se quiere añadir una imagen SVG a la serigrafía de la placa, se hace desde Archivo → Importar → Gráfico, y se selecciona la capa **F.Silkscreen**. Eso es opcional y cada uno lo personaliza como quiera.

---

### Lo que me llevo

KiCad tiene su curva de aprendizaje pero la lógica es clara: primero diseñas el esquema (cómo se conecta todo), después asignas las huellas (qué tamaño tiene cada componente físico) y por último armas la placa (dónde va cada cosa en el espacio real). Son tres mundos distintos pero que tienen que cuadrar entre sí.

### Investigación propia 
<img width="330" height="350" alt="image" src="https://github.com/user-attachments/assets/e9da4d69-3ea6-4419-a8ef-13f7f839c6cf" />
<img width="330" height="350" alt="image" src="https://github.com/user-attachments/assets/2b444e89-1d32-48f1-a935-bf08289d2326" />
<img width="330" height="350" alt="image" src="https://github.com/user-attachments/assets/0e6d840d-d678-4c62-b71e-9faffdb5d9fe" />

---

### Referencias

- [KiCad EDA — Software oficial](https://www.kicad.org/)
- [KiCad PCB Editor — Documentación oficial](https://docs.kicad.org/master/en/pcbnew/pcbnew.html)
- [NE555 Timer — datasheet y aplicaciones](https://www.ti.com/lit/ds/symlink/ne555.pdf)
- [Atari Punk Console — cómo funciona](https://www.instructables.com/Atari-Punk-Console/)
- [Footprints en KiCad — guía](https://docs.kicad.org/7.0/en/pcbnew/pcbnew.html)
- [Edge.Cuts en KiCad — definir borde de placa](https://docs.kicad.org/7.0/en/getting_started_in_kicad/getting_started_in_kicad.html)
