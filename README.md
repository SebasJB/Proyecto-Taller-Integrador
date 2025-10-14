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

* *(Agrega aquí los nombres de los integrantes del equipo)*

---

## 3. Etapas de fabricación

> Reemplaza las rutas `images/sprint3/...` por tus fotos.
> Sugerencia de nombres: `01-drill.jpg`, `02-metalizacion.jpg`, `02-stencil.jpg`, `03-endmill-bottom.jpg`, etc.

### 3.1 Drill (Barrenado)

<p align="justify">
Objetivo: generar todos los taladros (PTH, montaje y fiduciales) conforme a los datos de fabricación.  
Criterios (QC): diámetros dentro de tolerancia, pads íntegros y sin desviaciones.
</p>

![Drill – Taladrado](images/sprint3/01-drill.jpg)

---

### 3.2 Metalización y Stencil

<p align="justify">
Objetivo: metalizar orificios (PTH) para continuidad entre capas y fabricar el stencil para deposición de pasta.  
Criterios (QC): continuidad eléctrica en PTH (muestras), adhesión uniforme, stencil sin rebabas ni deformaciones.
</p>

![Metalización de PTH](images/sprint3/02-metalizacion.jpg)
![Stencil de pasta](images/sprint3/02-stencil.jpg)

---

### 3.3 Endmill Bottom

<p align="justify">
Objetivo: fresado de contornos/cavidades en la <strong>cara inferior</strong>.  
Criterios (QC): bordes limpios, dimensiones dentro de tolerancia y ausencia de delaminación.
</p>

![Endmill Bottom](images/sprint3/03-endmill-bottom.jpg)

---

### 3.4 Verificación visual

<p align="justify">
Objetivo: inspección óptica intermedia para detectar rayas, pads dañados, desplazamientos y contaminación.  
Criterios (QC): máscara (si aplica) intacta, sin cortos visibles y registros correctos.
</p>

![Inspección Visual Intermedia](images/sprint3/04-visual-check.jpg)

---

### 3.5 Endmill Top

<p align="justify">
Objetivo: fresado en la <strong>cara superior</strong> (contornos, ranuras y ventanas).  
Criterios (QC): simetría respecto a la cara inferior y coincidencia con DXF/Gerbers mecánicos.
</p>

![Endmill Top](images/sprint3/05-endmill-top.jpg)

---

### 3.6 Verificación de aislamientos y cortos

<p align="justify">
Objetivo: comprobar <em>clearances</em> y ausencia de cortos en redes críticas.  
Criterios (QC): continuidad solo donde corresponde; aislamiento ≥ al clearance de diseño (mediciones spot con multímetro).
</p>

![Pruebas de aislamiento/continuidad](images/sprint3/06-insulation-shorts.jpg)

---

### 3.7 Recorte y recubrimiento con estaño

<p align="justify">
Objetivo: panelizado/corte final y recubrimiento con estaño (tin coating) en pads expuestos para mejorar soldabilidad.  
Criterios (QC): bordes sin astillas, recubrimiento uniforme y sin puentes metálicos.
</p>

![Recorte y tin coating](images/sprint3/07-tin-coating.jpg)

---

### 3.8 Soldermask y Silkscreen

<p align="justify">
Objetivo: aplicar soldermask (protección) y serigrafía (referencias, polaridades y marcación pin-1).  
Criterios (QC): registro correcto, silks legible y sin invadir pads.
</p>

![Soldermask](images/sprint3/08-soldermask.jpg)
![Silkscreen](images/sprint3/08-silkscreen.jpg)

---

### 3.9 Soldadura SMD

<p align="justify">
Objetivo: deposición de pasta mediante stencil, <em>pick & place</em> y reflow siguiendo el perfil térmico recomendado.  
Criterios (QC): mojado adecuado, ausencia de puentes, sin <em>tombstoning</em> y orientación correcta de componentes.
</p>

![Pasta + Colocación](images/sprint3/09-smd-paste-place.jpg)
![Reflow – Resultado](images/sprint3/09-smd-reflow.jpg)

---

## 4. Erros y desafios

<p align="justify">
<strong>Dimensional:</strong> contorno, taladros y grosor.  
<strong>Eléctrico básico:</strong> continuidad PTH y ausencia de cortos.  
<strong>Visual:</strong> pads íntegros, registro soldemask/silks.  
<strong>Soldabilidad:</strong> humectación, alineación de pines y voids aceptables en pads térmicos (si aplica).
</p>

---


## 5. Test Plan – Verificación y Validación de la PCB
<p align="justify"> Este plan de pruebas detalla las verificaciones eléctricas y funcionales realizadas sobre la tarjeta fabricada. Cada prueba se identifica por un código <strong>(T-N)</strong> y busca confirmar la correcta operación de los subsistemas antes y después del montaje del ASIC. Las pruebas se ejecutan siguiendo una secuencia lógica: desde conectividad básica hasta validaciones funcionales completas con firmware de diagnóstico. </p>

### 5.1 Conectividad por headers (T-0)
<p align="justify"> Antes de energizar la placa, se realiza una verificación minuciosa de continuidad utilizando los headers intermedios como puntos de prueba. Se confirma que cada módulo bufferizado (reguladores, LEDs, LCD, reloj y reset) tiene su camino eléctrico completo desde la entrada del buffer hasta la salida hacia la carga, y que no existen puentes inadvertidos a tierra o entre señales contiguas. Con el multímetro en modo continuidad y la placa sin alimentación, se comprueba cada par “entrada ↔ salida”, escuchando el pitido solo cuando corresponde según el esquemático. Se finaliza con una verificación de ausencia de corto entre rieles de alimentación y GND. <strong>Criterio de aceptación:</strong> toda la conectividad coincide con el diseño y no se detectan cortos. </p>

### 5.2 Fuentes al vacío (T-1)
<p align="justify"> Con la placa sin cargas conectadas, se alimenta desde la fuente de laboratorio con límite de corriente ajustado. Se verifica que los tres reguladores (1.0 V, 1.8 V y 3.0 V) establecen sus tensiones nominales de forma estable y sin rizado excesivo. Se mide cada riel con multímetro (DC) y osciloscopio (AC) observando rizado y picos de arranque. <strong>Criterio de aceptación:</strong> tensiones dentro de ±2 % / ±3 % según el riel, y rizado menor a 20 / 30 / 50 mVpp respectivamente. </p>

### 5.3 Fuentes con carga (T-2)
<p align="justify"> Se conectan cargas resistivas o electrónicas a cada riel, una por vez, para validar la capacidad de regulación y estabilidad bajo demanda. Se incrementa la corriente hasta el valor nominal de cada riel y se repiten las mediciones. Luego se aplica un escalón de carga observando la respuesta transitoria: la tensión no debe presentar sobre-/sub-tensión mayores al 5 % ni oscilar. <strong>Criterio de aceptación:</strong> tensiones dentro de tolerancia en régimen y transientes amortiguadas. </p>

### 5.4 Reset (T-3)
<p align="justify"> Se verifica que el circuito de reset genera un pulso limpio y responde ante condiciones de sub-tensión. Con la placa energizada, se mide en el header del reset mientras se acciona el pulsador. El nivel activo debe tener flancos definidos y duración suficiente para un reinicio completo. Luego se simula un brown-out bajando la entrada de la fuente y restaurándola, comprobando que el supervisor actúe correctamente. <strong>Criterio de aceptación:</strong> pulso estable (≥ 100 ms), sin rebotes, y correcta actuación ante sub-tensión. </p>

### 5.5 Reloj de cristal y buffer (T-4)
<p align="justify"> Se verifica que el oscilador arranca correctamente y entrega la frecuencia nominal, con distribución adecuada por el buffer. La señal medida en el header debe tener forma limpia, duty-cycle cercano al 50 % (40–60 % admisible) y frecuencia dentro de la tolerancia del cristal (± 50 ppm típicos). <strong>Criterio de aceptación:</strong> señal estable, libre de deformaciones y en frecuencia. </p>

### 5.6 LEDs bufferizados con Arduino (T-5)
<p align="justify"> Se valida la etapa de buffer y el camino hacia los LEDs utilizando un Arduino como generador de señales. Con tierra común, se inyectan señales ON/OFF y PWM (1 kHz) desde el header de control. Se observa que cada LED conmute y varíe de brillo sin parpadeos o incoherencias. <strong>Criterio de aceptación:</strong> todos los LEDs conmutan y modulan correctamente, sin anomalías de nivel. </p>

### 5.7 LCD/OLED bufferizado con Arduino (T-6)
<p align="justify"> El display se valida mediante el header intermedio, usando el Arduino para generar la secuencia de inicialización y los patrones de prueba. Si es SPI, se conectan MOSI/SCLK/CS/DC/RST respetando niveles de 3.3 V; si es paralelo (HD44780), se usa modo 4 bits. Se inicializa el controlador (p. ej., SSD1306, ST7735, ILI9341, HD44780) y se muestra un patrón o texto (“OK”, contador). <strong>Criterio de aceptación:</strong> el display inicializa correctamente, muestra contenido legible y sin artefactos. </p>

### 5.8 Memoria en base DIP con apoyo de Arduino (T-7)
<p align="justify"> Dado que la memoria no posee header intermedio, se prueba directamente sobre el zócalo DIP con un Arduino. Para memorias seriales (SPI/I²C), se realiza una escritura/lectura de patrones simples (0xAA, 0x55, 0x00, 0xFF). Para memorias paralelas, se controla un subconjunto de direcciones y datos con CE/OE/WE, verificando escritura y lectura correctas. <strong>Criterio de aceptación:</strong> coincidencia entre datos escritos y leídos; sin fallas ni comportamiento errático. </p>

### 5.9 Re-chequeo con ASIC montado (pre-funcional)
<p align="justify"> Con el ASIC soldado y revisado visualmente, se repiten brevemente las pruebas T-1, T-2, T-3 y T-4 bajo carga real. Se busca confirmar que el chip no introduce ruidos ni caídas adicionales. <strong>Criterio de aceptación:</strong> resultados dentro de márgenes definidos en las pruebas base. </p>

### 5.10 Arranque funcional con Siwa (T-8)
<p align="justify"> Con la placa validada eléctricamente, se programa un firmware de diagnóstico mediante la herramienta Siwa. Al encender, debe generar un parpadeo (heartbeat) en un LED, mostrar “OK” en pantalla y enviar una trama UART de saludo. Se repiten tres ciclos de arranque (incluyendo reset y power-cycle). <strong>Criterio de aceptación:</strong> comportamiento consistente en los tres intentos, sin bloqueos ni fallos en periféricos. </p>

### 5.11 Medición de consumo por riel (T-9)
<p align="justify"> Se mide la corriente de cada riel usando los headers de entrada/salida o shunt de medición. Se registran condiciones de reposo (idle) y actividad (ejecución del diagnóstico). <strong>Criterio de aceptación:</strong> cada riel dentro de ± 10 % del objetivo y sin caídas o rizado fuera de límites definidos en T-1/T-2. </p>

### 5.12 Cierre y criterios de aceptación globales
<p align="justify"> La tarjeta se considera lista cuando todas las pruebas se completan satisfactoriamente y los resultados son coherentes entre repeticiones. Cualquier desviación debe documentarse indicando condición de prueba, observación y acción correctiva (por ejemplo, ajustar RC de reset, mejorar desacoplo o secuencia de inicialización del display). </p>
---

## 6. Checklist de cierre del Sprint 3

* [ ] Evidencias fotográficas por etapa en `images/sprint3/`
* [ ] Registro de QC cumplido
* [ ] Test Plan creado y casos críticos ejecutados
* [ ] Incidencias documentadas y acciones definidas

---

> **Nota:** si las imágenes viven en otra carpeta del repo (p. ej. `docs/img/`), cambia únicamente las rutas en los `![...](...)` manteniendo nombres coherentes para facilitar la trazabilidad.
