# Ficha de análisis

## 1. Nombre del Space

* **Nombre:** wan2.2_14b_i2v_480p_lightning_nsfw_diffusers
* **Enlace:** [https://huggingface.co/spaces/EldMans/wan2.2_14b_i2v_480p_lightning_nsfw_diffusers](https://huggingface.co/spaces/EldMans/wan2.2_14b_i2v_480p_lightning_nsfw_diffusers)

---

## 2. ¿Qué hace el agente?

El sistema es un modelo de inteligencia artificial de imagen a video a partir de una imagen de referencia inicial y un prompt,
el agente genera una secuencia de video en resolución de 480p que simula el movimiento o la evolución visual de la escena planteada.

---

## 3. Análisis PEAS

| Elemento | Respuesta |
| :--- | :--- |
| **Performance** | Generar un video coherente, fluido y de alta calidad visual a 480p que refleje fielmente tanto la imagen estática de entrada como las instrucciones del prompt de texto|
| **Environment** | La plataforma de Hugging Face Spaces, la infraestructura de hardware con aceleración por GPU.|
| **Actuators** | La renderización y reproducción del archivo de video resultante en la interfaz de usuario, junto con la opción de descargar el video |
| **Sensors** | La imagen estática de entrada cargada, el prompt de lo que se quiere en el video, y los parámetros de configuración. |

---

## 4. Clasificación del entorno

Complete la siguiente tabla y justifique brevemente cada respuesta.

| Propiedad | Clasificación | Justificación |
| :--- | :--- | :--- |
| **Observable** | Parcial | El agente unifica la información proporcionada explícitamente por el usuario, pero no posee percepción ni contexto sobre el mundo real fuera de esos límites. |
| **Determinista** | No | Al basarse en procesos de probabilidades y seeds, la ejecución del modelo con las mismas entradas puede arrojar variaciones sutiles en los videos.|
| **Episódico** | Sí | Cada proceso de generación de video es un evento independiente; la creación de un video actual no afecta la ejecución de futuras solicitudes del usuario. |
| **Estático** | Sí | Durante el proceso de inferencia y generación, el entorno permanece sin cambios y no evoluciona de manera autónoma en segundo plano. |
| **Discreto** | No | El sistema procesa espacios continuos, tales como los valores flotantes de los embeddings semánticos del texto y las matrices de píxeles que componen la imagen y los fotogramas del video. |
| **Conocido** | Sí | Las leyes físicas, matemáticas y de procesamiento de datos que rigen el comportamiento del entorno y de la red neuronal están completamente definidas por sus creadores y la arquitectura del modelo.|

---

## 5. ¿Qué tipo de programa de agente creen que es?

Seleccione la opción que consideren más adecuada y explique por qué.

* [ ] Agente de reflejo simple
* [ ] Agente basado en modelo
* [ X ] Agente basado en objetivos
* [ ] Agente basado en utilidad
* [ ] Agente con aprendizaje

 Se clasifica como un **agente basado en objetivos**,el sistema recibe una imagen que funciona como la meta a alcanzar, y utiliza su arquitectura de red neuronal profunda para planificar y ejecutar paso a paso la transición de fotogramas, buscando minimizar el error entre la secuencia de video generada y el objetivo expresado por el usuario.

---

## Reto adicional

Encuentre un Space que pueda clasificarse como:
1. Totalmente observable, determinista y episódico: https://huggingface.co/spaces/huggingface-projects/QR-code-AI-art-generator

**justificacion: **Podemos definir este entorno como totalmente observable ya que el agente procesa una entrada directa y completa proporcionada en pantalla por el usuario, determinista porque la lógica matemática que da forma al código QR garantiza un funcionamiento estructural predecible ante las mismas variables, y episódico porque cada tarea de generación artística ocurre de forma aislada, sin que el resultado anterior condicione los trabajos futuros.

2. Parcialmente observable, estocástico y secuencial: https://huggingface.co/spaces/Qwen/Qwen3-TTS
**justificacion: **El entorno de este agente es parcialmente observable debido a que carece de una percepción total del mundo real más allá de los datos de audio y texto ingresados, es estocástico porque los componentes generativos de inteligencia artificial introducen un margen de aleatoriedad en el procesamiento del habla, y se cataloga como secuencial ya que cada paso de síntesis se construye sobre el flujo anterior, haciendo que las decisiones previas modifiquen el resultado de las ejecuciones sucesivas.


---

