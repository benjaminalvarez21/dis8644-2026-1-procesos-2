# sesion-08a

## KiCad

Este es un software para crear circuitos, desde su esquemático hasta el diseño final de la pcb.

En esta clase se trabajaron los primeros 3 pasos del proceso: 

---

**1. Dibujar esquemático (.kicad_sch)**

**2. Asociar huellas a símbolos**

**3. Abrir pcb new para interpretar esquemático**

---
4. Definir tamaño de pistas
   
5. Repartir componentes

6. Rutear
   
7. Adornar

Como antes ya hemos visto en placas, siempre se ubican letras pequeñitas. Estos son los componentes distribuidos.
En la librería para ubicarlos con nombre:

| Componentes | Nombre en librería |
|----|----|
| resistencia | r |
| capacitor | c |
| capacitor polarizado | c_polarized |
| potenciómetro | r_potenciometer |
| ground | gnd |
| positivo | vcc |
| circuito integrado | u |
| led | led |
| batería | battery_cell |
| parlante | speaker |

Una vez realizado el esquemático asociamos huellas a los símbolos.

**- E (Propiedades del símbolo)**
Huella > Selector de huellas
Aquí existe una biblioteca de huellas asociadas a símbolos. Usaremoa las de la biblioteca *THT*.

**Tipos de tecnología:**

THT: los componentes se sueldan a través de agujeros que tiene la pcb.

SMD: los componentes se sueldan sobre la superficie de la pcb.

**Huellas a utilizar:**

+ Condensador cerámico |	Capacitor_THT:C_Disc_D3.8mm_W2.6mm_P2.50mm
+ Condensador electrolítico	| Capacitor_THT:CP_Radial_D5.0mm_P2.50mm
+ Resistencia |	Resistor_THT:R_Axial_DIN0207_L6.3mm_D2.5mm_P10.16mm_Horizontal
+ Potenciómetro |	Potentiometer_THT:Potentiometer_Alps_RK163_Single_Horizontal
+ LED |	LED_THT:LED_D5.0mm

**Ahora pasamos al plano físico. *PCB new*.**

Es el botoncito verde en la parte superior derecha, aquí actualizamos desde el esquemático.

KiCad trabaja con una lógica similar a los softwares, que como diseñadores estamos acostumbrados a utilizar (AutoCad, Illustrator, etc) que es a través de capas.

Estaremos trabajando con 7 capas principalmente:

+ bordes: edge.cuts
+ cobre arriba: f.cu
+ máscara arriba: f.mask
+ serigrafía arriba: f.silks
+ cobre abajo: b.cu
+ máscara abajo: b.mask
+ serigrafía abajo: b.silks

Con alt + 3 se abre el *Visor 3D*
