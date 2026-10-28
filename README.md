# Sistema de visión artificial para la seguridad vial en el entorno educativo

🌐 **Entorno web y tablero de control funcional**  
**Universidad Salesiana de Bolivia · Ingeniería de Sistemas**  
Proyecto Integrador · Equipo Error 505  

Sistema automatizado de visión artificial que genera evidencia objetiva del flujo vehicular frente a unidades educativas para apoyar las decisiones de seguridad de la comunidad escolar, protegiendo la privacidad desde el diseño (sin almacenar placas ni rostros)[cite: 2].

---

## 👥 Equipo de desarrollo (Grupo Error 505)

| # | Integrante | Materias integradas |
| :--- | :--- | :--- |
| 1 | Fernando Castro Vargas | Inteligencia Artificial I[cite: 2] |
| 2 | Juan Carlos Chavez Machaca | Metodología de la Investigación II[cite: 2] |
| 3 | Kevin Jheferson Jiménez Quisbert | Optativa II[cite: 2] |
| 4 | Erick Ivan Luna Tarqui | Ingeniería de Sistemas |
| 5 | Cristhian Juan Antonio Ramos Rojas | Ingeniería de Redes y Software |

---

## 📌 Descripción del proyecto

En las zonas educativas de Bolivia, los estudiantes cruzan las vías a pie o en bicicleta durante las horas de entrada y salida[cite: 2]. La dirección y las juntas escolares suelen carecer de datos objetivos de tránsito para solicitar medidas viales a la alcaldía, organizando brigadas de control sin experiencia previa[cite: 2].

Este sistema resuelve dicha problemática mediante:
* **Captura en red local:** Transmisión estable de video mediante redes ILAN con segmentación VLAN y políticas de Calidad de Servicio (QoS)[cite: 2].
* **Procesamiento inteligente:** Detección y conteo automatizado de vehículos mediante Python y OpenCV[cite: 2].
* **Privacidad desde el diseño:** El video se procesa en vivo y se descarta de inmediato; únicamente se almacenan conteos agregados por hora en PostgreSQL[cite: 2].
* **Visualización gerencial:** Un tablero web interactivo desarrollado con FastAPI para que la dirección, padres y regentes dispongan de métricas claras[cite: 2].

---

## 🎯 Objetivos del proyecto

* **Objetivo general:** Diseñar e implementar un sistema de visión artificial que genere evidencia de flujo vehicular, para apoyar decisiones de seguridad de la comunidad escolar[cite: 2].
* **Objetivos específicos[cite: 2]:**
  1. Diagnosticar el riesgo vial escuchando a regentes, padres y estudiantes, y diseñar la red y el punto de captura.
  2. Implementar la detección y el conteo de vehículos, con una meta de precisión $\ge 90\%$ frente al conteo manual.
  3. Implementar el tablero y las alertas visuales con una latencia menor a $3\text{ s}$.
  4. Evaluar con la comunidad la utilidad, privacidad y limitaciones, entregando un informe formal a la dirección.

---

## 🛠️ Herramientas y tecnologías

| Capa | Tecnología | Función / Uso principal |
| :--- | :--- | :--- |
| **Red** | ILAN, VLAN, QoS | Transmisión estable y priorizada del video[cite: 2]. |
| **Captura** | Cámara IP (IP Webcam), RTSP / HTTP | Captura del video de la vía pública[cite: 2]. |
| **Visión artificial** | Python, OpenCV | Detección y conteo automatizado de vehículos (sin leer placas)[cite: 2]. |
| **Base de datos** | PostgreSQL | Almacenamiento seguro de conteos agregados por hora[cite: 2]. |
| **Aplicación** | FastAPI, Interfaz web | Servidor backend, tablero de control y alertas[cite: 2]. |
| **Control de trabajo** | Git, Kanban, Scrumban | Gestión y control de versiones del equipo[cite: 2]. |

---

## 🧱 Estructura y flujo del sistema

### Arquitectura de datos
```text
Cámara IP (Video de la vía) ➔ Red ILAN (VLAN y QoS) ➔ Módulo de Visión (Detección y conteo) ➔ Base de datos PostgreSQL (Conteos por hora) ➔ Tablero FastAPI (Dirección y regentes)