# Plataforma de interconexión y pruebas del SIWA


## EL-5610 – Taller Integrador

[![Estado](https://img.shields.io/badge/estado-en_progreso-blue.svg)]()
[![Sprint](https://img.shields.io/badge/sprint-3-important.svg)]()
[![Fabricación](https://img.shields.io/badge/etapa-fabricaci%C3%B3n_PCB-brightgreen.svg)]()
[![Tecnolog%C3%ADa](https://img.shields.io/badge/tecnolog%C3%ADa-EDA%20%7C%20Stencil%20%7C%20Reflow-lightgrey.svg)]()

---

## 1. Introducción

<p align="justify">
Este sprint documenta la construcción física de la PCB del proyecto, desde el barrenado inicial (<em>drill</em>) hasta la soldadura SMD posterior al reflow. El objetivo es registrar, con trazabilidad, cada etapa del proceso junto con criterios de aceptación y evidencias visuales, de manera que la tarjeta quede lista para el plan de pruebas eléctricos y funcionales del siguiente sprint.
</p>

---

## 2. Integrantes

- Samuel Valdivia Mejias
- Sebastian Barrantes Perez
- Christopher Quiros Cisneros

---

## 3. Etapas de fabricación

### 3.1 Drill

<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/Drill.jpeg" alt="PCB: Post drill" width="600">
</p>
<p align="center">
PCB: Post drill

---

### 3.2 Metalización y Stencil


<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/metalizacion.jpeg" alt="PCB: Post metalizacion" width="600">
</p>
<p align="center">
PCB: Post metalizacion

---

### 3.3 Endmill Bottom


<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/EMB1.jpeg" alt="PCB: Post Endmill Bottom" width="600">
</p>
<p align="center">
PCB: Post Endmill Bottom

---


### 3.4 Endmill Top


<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/EMT1.jpeg" alt="PCB: Endmill top durante fabricacion" width="600">
</p>
<p align="center">
PCB: Endmill top durante fabricacion

<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/EMT2.jpeg" alt="PCB: Post Endmill Top" width="600">
</p>
<p align="center">
PCB: Post Endmill Top

---

### 3.5 Verificación de aislamientos y cortos


<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/rev1.jpeg" alt="PCB: Revision de cortos" width="600">
</p>
<p align="center">
PCB: Revision de cortos
 
<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/rev2.jpeg" alt="PCB: Revision de cortos" width="600">
</p>
<p align="center">
PCB: Revision de cortos
 
<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/rev3.jpeg" alt="PCB: Revision de cortos" width="600">
</p>
<p align="center">
PCB: Revision de cortos

---


### 3.6 Soldermask y Silkscreen


<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/soldertop.jpeg" alt="PCB: Post Soldermask Top" width="600">
</p>
<p align="center">
PCB: Post Soldermask Top

<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/solderbot.jpeg" alt="PCB: Post Soldermask Bottom" width="600">
</p>
<p align="center">
PCB: Post Soldermask Bottom

---

### 3.7 Soldadura SMD



<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/pasta%20de%20soldadura.jpeg" alt="PCB: aplicacion de pasta de soldadura" width="600">
</p>
<p align="center">
PCB: aplicacion de pasta de soldadura
 
<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/pre%20soldadura.jpeg" alt="PCB: Presoldadura, componentes ya colocados" width="600">
</p>
<p align="center">
PCB: Presoldadura, componentes ya colocados

<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/horno.jpeg" alt="PCB: Proceso de soldado en el horno" width="600">
</p>
<p align="center">
PCB: Proceso de soldado en el horno

<p align="center">
  <img src="https://github.com/SebasJB/Proyecto-Taller-Integrador/blob/main/Documentaci%C3%B3n%20SIWA/post%20soldadura.jpeg" alt="PCB: Post Soldadura" width="600">
</p>
<p align="center">
PCB: Post Soldadura

---

## 4. Erros y desafios

<p align="justify">
...
</p>

---


## 5. Test Plan – Verificación y Validación de la PCB
<p align="justify"> Este plan de pruebas detalla las verificaciones eléctricas y funcionales realizadas sobre la tarjeta fabricada. Cada prueba se identifica por un código <strong>(T-N)</strong> y busca confirmar la correcta operación de los subsistemas antes y después del montaje del ASIC. Las pruebas se ejecutan siguiendo una secuencia lógica: desde conectividad básica hasta validaciones funcionales completas con firmware de diagnóstico. </p>

 ### 5.1. Instrumentación

- Fuente de laboratorio
- Multímetro digital (DMM)
- Osciloscopio 
- Cargas resistivas para 1 V, 1.8 V y 3 V
- Arduino para pruebas dinámicas
- Jumpers, divisores de tensión y convertidores de nivel

### 5.2 Conectividad por headers (T-0)
<p align="justify"> Antes de energizar la placa, se realiza una verificación minuciosa de continuidad utilizando los headers intermedios como puntos de prueba. Se confirma que cada módulo bufferizado (reguladores, LEDs, LCD, reloj y reset) tiene su camino eléctrico completo desde la entrada del buffer hasta la salida hacia la carga, y que no existen puentes inadvertidos a tierra o entre señales contiguas. Con el multímetro en modo continuidad y la placa sin alimentación, se comprueba cada par “entrada ↔ salida”, escuchando el pitido solo cuando corresponde según el esquemático. Se finaliza con una verificación de ausencia de corto entre rieles de alimentación y GND. </p>

**Objetivo:** Verificar continuidad entre headers, buffers y cargas, asegurando que no existan cortos entre rieles.

**Procedimiento:**
- Placa sin energía, DMM en continuidad.  
- Verificar headers intermedios y rieles de alimentación.  
- Confirmar ausencia de corto con GND.

**Criterio:**  
Todos los caminos coinciden con el esquemático y no hay cortos entre rieles.

### 5.3 Fuentes sin carga (T-1)
<p align="justify"> Con la placa sin cargas conectadas, se alimenta desde la fuente de laboratorio con límite de corriente ajustado. Se verifica que los tres reguladores (1.0 V, 1.8 V y 3.0 V) establecen sus tensiones nominales de forma estable y sin rizado excesivo. Se mide cada pista con multímetro (DC) y osciloscopio (AC) observando rizado y picos de arranque.</p>

**Objetivo:** Confirmar tensiones nominales y estabilidad sin carga.

| Riel | Tensión esperada | Ripple máx | Estado |
|:--|:--:|:--:|:--:|
| 3.0 V | 3.00 ± 3 % | < 50 mVpp | ☐ |
| 1.8 V | 1.80 ± 2 % | < 30 mVpp | ☐ |
| 1.0 V | 1.00 ± 2 % | < 20 mVpp | ☐ |

**Procedimiento:**
- Alimentar desde la fuente de laboratorio.  
- Medir cada riel en su header de salida con Multímetro y osciloscopio (AC acoplado).
  
**Criterio:** Las tres salidas están dentro de tolerancia y con rizado menor al límite.

### 5.4 Fuentes con carga (T-2)
<p align="justify"> Se conectan cargas resistivas a cada pista, una por vez, para validar la capacidad de regulación y estabilidad bajo demanda. Se incrementa la corriente hasta el valor nominal de cada pista y se repiten las mediciones. Luego se aplica un escalón de carga observando la respuesta transitoria: la tensión no debe presentar sobre-/sub-tensión mayores al 5 % ni oscilar. </p>

**Objetivo:** Evaluar regulación bajo corriente nominal y respuesta a transientes.

**Procedimiento:**
- Conectar carga resistiva a cada riel.  
- Medir caída de tensión y rizado.  
- Realizar un **step-load de 10 % a 100 % a 10 %** y observar overshoot < 5 %.  
 Para el step-load: **Conmutador y resistencias**
- 2 resistencias que representen 10 % y 100 % de carga (R1 y R2).
- 1 transistor NPN (2N2222, 2N3904) o MOSFET N (IRLZ44N, 2N7000).
- Una señal cuadrada con generador de señales.

**Criterio:** Tensiones y rizados se mantienen dentro del rango permitido.

### 5.5 Reset (T-3)
<p align="justify"> Se verifica que el circuito de reset genera un pulso limpio y responde ante condiciones de sub-tensión. Con la placa energizada, se mide en el header del reset mientras se acciona el pulsador. El nivel activo debe tener flancos definidos y duración suficiente para un reinicio completo. </p>

**Objetivo:** Verificar forma de pulso

**Procedimiento:**
1. Medir en el header de **RESET** con osciloscopio.  
2. Pulsar el botón para verificar duración (≥ 100 ms).  

**Criterio:** Pulso limpio, sin rebotes y a nivel correcto

### 5.6 Reloj de cristal y buffer (T-4)
<p align="justify"> Se verifica que el oscilador arranca correctamente y entrega la frecuencia nominal, con distribución adecuada por el buffer. La señal medida en el header debe tener forma limpia, duty-cycle cercano al 50 % (40–60 % admisible) y frecuencia dentro de la tolerancia del cristal (± 100 ppm ). </p>

**Objetivo:** Confirmar frecuencia y duty-cycle del oscilador con buffer.

**Procedimiento:**
- Alimentar el circuito y medir en el header de salida del buffer.  
- Verificar que la frecuencia sea de **20.000 MHz ± 50 ppm**, un ciclo de trabajo entre 40–60 %, amplitud cercana a 3 Vpp.  

**Criterio:** Señal estable, libre de deformaciones y en frecuencia correcta.

### 5.7 LEDs bufferizados con Arduino (T-5)
<p align="justify"> Se valida la etapa de buffer y el camino hacia los LEDs utilizando un Arduino como generador de señales. Con tierra común, se inyectan señales ON/OFF y PWM (1 kHz) desde el header de control. Se observa que cada LED conmute y varíe de brillo sin parpadeos o incoherencias. </p>

**Objetivo:** Validar respuesta de buffers y polaridad de LEDs.

**Procedimiento:**
- GND común entre Arduino y placa.  
- Enviar secuencias de ON/OFF para probar encendido y apagado
- Enviar un PWM de 1 kHz para probar el brillo.

**Criterio:** Todos los LEDs encienden, varían brillo y no presentan parpadeo.
### 5.8 LCD/OLED bufferizado con Arduino (T-6)
<p align="justify"> El display se valida mediante el header intermedio, usando el Arduino para generar la secuencia de inicialización y los patrones de prueba. SSe conectan MOSI/SCLK/CS/DC/RST respetando niveles de 3.3 V. Se inicializa el controlador y se muestra un patrón o texto. </p>

**Objetivo:** Confirmar inicialización y escritura básica vía Arduino.

**Procedimiento:**
- Conectar Arduino a SDA/SCL/RES del header con resistencias de pull-up de 4.7 kΩ.
- Usar librerías y comandos básicos del dispositivo en US2066.
- Enviar un PWM de 1 kHz para probar el brillo.

**Criterio:** Pantalla inicializa y muestra texto sin artefactos o pérdida de contraste.


### 5.9 Memoria en base DIP con apoyo de Arduino (T-7)
<p align="justify"> Dado que la memoria no posee header intermedio, se prueba directamente sobre el zócalo DIP con un Arduino. Para memorias seriales (SPI/I²C), se realiza una escritura/lectura de patrones simples (0xAA, 0x55, 0x00, 0xFF). Para memorias paralelas, se controla un subconjunto de direcciones y datos con CE/OE/WE, verificando escritura y lectura correctas. </p>

**Objetivo:** Confirmar lectura/escritura/erase básicos con Arduino.

**Procedimiento:**
- Conectar Arduino a SDA/SCL/RES del header con resistencias de pull-up de 4.7 kΩ.
- Conectar GND común.
- Enviar secuencia SPI para comprobar escritura y lectura
**Criterio:** Coincidencia entre datos escritos y leídos, sin fallas ni comportamiento errático y sin errores en verificación 

### 5.10 Revisión con ASIC montado
<p align="justify"> Con el ASIC soldado y revisado visualmente, se repiten brevemente las pruebas T-1, T-2, T-3 y T-4 bajo carga real. Se busca confirmar que el chip no introduce ruidos ni caídas adicionales. <strong>Criterio de aceptación:</strong> resultados dentro de márgenes definidos en las pruebas base. </p>

### 5.11 Arranque funcional con Siwa (T-8)
<p align="justify"> Con la placa validada eléctricamente, se programa un firmware de diagnóstico mediante la herramienta Siwa. Al encender, debe correr los programas cargados previamente. Se repiten tres ciclos de arranque incluyendo reset y ciclo de poder. <strong>Criterio de aceptación:</strong> comportamiento consistente en los tres intentos, sin bloqueos ni fallos en periféricos. </p>

### 5.12 Medición de consumo por pista (T-9)
<p align="justify"> Se mide la corriente de cada pista usando los headers de entrada y salida de medición. Se registran condiciones de reposo y actividad . <strong>Criterio de aceptación:</strong> cada riel dentro de ± 10 % del objetivo y sin caídas o rizado fuera de límites definidos en T-1/T-2. </p>


## 6. Checklist de cierre del Sprint 3

* [ ] Evidencias fotográficas por etapa en `images/sprint3/`
* [ ] Registro de QC cumplido
* [ ] Test Plan creado y casos críticos ejecutados
* [ ] Incidencias documentadas y acciones definidas

---

> **Nota:** si las imágenes viven en otra carpeta del repo (p. ej. `docs/img/`), cambia únicamente las rutas en los `![...](...)` manteniendo nombres coherentes para facilitar la trazabilidad.
