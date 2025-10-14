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

## 4. Controles de calidad (resumen)

<p align="justify">
<strong>Dimensional:</strong> contorno, taladros y grosor.  
<strong>Eléctrico básico:</strong> continuidad PTH y ausencia de cortos.  
<strong>Visual:</strong> pads íntegros, registro soldemask/silks.  
<strong>Soldabilidad:</strong> humectación, alineación de pines y voids aceptables en pads térmicos (si aplica).
</p>

---

## 5. Test Plan (estructura base)

> Aquí agregarás tus subsecciones, casos de prueba y resultados.

### 5.1 Objetivos de prueba

<p align="justify">
Verificar integridad eléctrica y mecánica tras la fabricación y el ensamble SMD, confirmando cumplimiento de tensiones, oscilador, memoria e interfaces críticas.
</p>

### 5.2 Alcance y supuestos

<p align="justify">
PCB ensamblada con componentes críticos; se cuenta con fuente limitada por corriente, multímetro, osciloscopio y <em>fixtures</em> mínimos.
</p>

### 5.3 Matriz de pruebas sugerida

| ID     | Área     | Caso de prueba           | Procedimiento breve                 | Criterio de aceptación                |
| ------ | -------- | ------------------------ | ----------------------------------- | ------------------------------------- |
| PWR-01 | Power    | Secuencia de encendido   | Limitar I, aplicar VIN, medir rails | Tensiones ±5%, sin sobrecorriente     |
| IO-01  | GPIO/LED | LED bufferizado          | Escribir patrón y observar          | Encendido correcto, sin calentamiento |
| CLK-01 | Reloj    | Oscilador de cristal     | Medir frecuencia/jitter/arranque    | Frecuencia dentro de tolerancia       |
| MEM-01 | Memoria  | Lectura/Escritura básica | Patrón march, verificación de datos | Sin errores, timing aceptable         |

### 5.4 Preparación y <em>fixtures</em>

<p align="justify">
Fuente c/limitación de corriente, multímetro, osciloscopio/probes, cables, conectores de prueba y jig/bed-of-nails (si aplica).
</p>

### 5.5 Pruebas sin ASIC

<p align="justify">
Conectividad (continuidad entre pads críticos y PTH a planos), fuentes (en vacío y con carga: 1.0 V, 1.8 V, 3.3 V; rizado y transitorios), reset (nivel y temporización), oscilador (frecuencia y amplitud), base DIP para memoria (R/W patrón) y verificación de LEDs/LCD bufferizados.
</p>

### 5.6 Pruebas con ASIC

<p align="justify">
Carga de programa/Siwa (placeholder), arranque/boot, medición de buses y relojes, consumo en <em>idle</em>/<em>run</em> vs presupuesto.
</p>

### 5.7 Criterios de aceptación

<p align="justify">
Todos los casos “Pasa/No pasa” dentro de especificación, sin sobrecorrientes ni calentamientos anómalos y con señales clave dentro de tolerancias.
</p>

### 5.8 Registro de resultados (evidencias)

<p align="justify">
Tablas con timestamp, lote de PCB y operador; adjuntar oscilogramas y fotografías.
</p>

![Scope – Rail 1V](images/sprint3/test/rail-1v-scope.jpg)
![Ilimitación de corriente](images/sprint3/test/current-limit.jpg)

### 5.9 Incidencias y acciones

<p align="justify">
Registro de ID, síntoma, causa raíz, corrección y verificación; lecciones aprendidas hacia el Sprint 4.
</p>

---

## 6. Trazabilidad

* **Entrada:** Gerbers/BoM/Stencil del Sprint 2 (commit/tag).
* **Salida:** PCB ensamblada y validada para el inicio de pruebas del sistema (Sprint 4).

---

## 7. Checklist de cierre del Sprint 3

* [ ] Evidencias fotográficas por etapa en `images/sprint3/`
* [ ] Registro de QC cumplido
* [ ] Test Plan creado y casos críticos ejecutados
* [ ] Incidencias documentadas y acciones definidas

---

> **Nota:** si las imágenes viven en otra carpeta del repo (p. ej. `docs/img/`), cambia únicamente las rutas en los `![...](...)` manteniendo nombres coherentes para facilitar la trazabilidad.
