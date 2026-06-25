# Analisis-Factibilidad-Radiofrecuencia-PtP
Diseño, simulación (Packet Tracer) y auditoría normativa de un enlace inalámbrico PtP de 2.5 km a 5GHz.
## 0. Contexto y Problema de Negocio (Caso GlobalNet)
La organización GlobalNet requiere interconectar de forma redundante su Sede Matriz y una Sucursal Operativa separadas por 2.5 kilómetros geográficos en un entorno urbano de alta densidad. 

**El desafío técnico:** Diseñar y auditar un enlace inalámbrico Punto a Punto (PtP) en la banda de 5 GHz capaz de:
1. Superar la atenuación del espacio libre y la interferencia física (reflexión por edificios de hormigón y difracción por parques).
2. Mantener un ancho de banda estable aislando ambas redes en Capa 2.
3. Operar estrictamente bajo el límite legal de potencia radiada (30 dBm) exigido por el ente regulador nacional (SUBTEL), evitando multas operativas.
# Auditoría y Diseño de Enlace Inalámbrico PtP a 5GHz

## 1. Resumen Ejecutivo
Análisis de factibilidad y diseño de ingeniería para un enlace punto a punto de 2.5 kilómetros en la banda de 5 GHz, emplazado en un entorno urbano denso. El proyecto evalúa la viabilidad electromagnética y aplica una auditoría de cumplimiento frente al marco regulatorio chileno (SUBTEL).

## 2. Arquitectura Lógica y Física
- **Topología:** Punto a Punto (PtP).
- **Controlador Matriz (Root Bridge):** Antena Parabólica de alta directividad con 19 dBi de ganancia.
- **Sucursal (Non-Root Bridge):** Antena Sectorial con 14 dBi de ganancia.
- **Modo de Operación:** Bridge transparente aislando segmentos en Capa 2.

## 3. Auditoría Normativa y Mitigación (SUBTEL)
El análisis del escenario base detectó una vulnerabilidad de cumplimiento. El EIRP original de 37 dBm superaba el límite legal fijado por la Resolución Exenta N° 1985/2017. 

**Solución Aplicada:**
Se forzó una reducción en la potencia de transmisión (Pt) a 13 dBm en el controlador lógico.

### Presupuesto de Enlace Ajustado (Link Budget)
- **Potencia de Transmisión (Pt):** 13 dBm
- **Pérdida por cableado (L):** 2 dB
- **EIRP Legal Obtenido:** 30 dBm (Cumplimiento estricto)
- **Atenuación de Espacio Libre (FSPL):** 114.39 dB
- **Potencia Recibida (Prx):** -72.38 dBm
- **Margen de Desvanecimiento (SNR):** 20.62 dB

> **Dictamen Final:** El SNR de 20.62 dB garantiza un enlace estable, capaz de absorber atenuaciones por factores climáticos o difracción, operando estrictamente dentro del marco legal chileno.

## 4. Fenómenos de Propagación Mitigados
El diseño en la banda de 5 GHz en entorno urbano contempla defensas pasivas contra:
1. **Reflexión Multitrayecto (Multipath):** Atenuación por rebotes en estructuras de hormigón.
2. **Difracción:** Curvatura de la onda al chocar con la biomasa de zonas arboladas, invadiendo el volumen de la primera Zona de Fresnel.

## 5. Simulación (Cisco Packet Tracer)
Debido a la ausencia de un motor RF tridimensional en el simulador (imposibilidad de calcular absorción o multipath), la factibilidad física se validó mediante el modelo de Espacio Libre (FSPL), mientras que el simulador garantizó el enrutamiento lógico de Capa 3.

<img width="1600" height="659" alt="WhatsApp Image 2026-06-23 at 21 52 48" src="https://github.com/user-attachments/assets/f8afb349-260f-41fe-8395-92c642fc682d" />
