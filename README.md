# 🌡️ Proyecto: Mi primer sistema de monitoreo (Cámaras de Frío)

### ¿Por qué hice este proyecto?
Todo empezó porque tenía la sospecha de que la temperatura de la cámara de frío no estaba funcionando correctamente. Como no quería seguir adivinando, decidí extraer datos reales directamente del equipo. Este proyecto nace de la necesidad de pasar del "creer algo" al "verlo con datos", evitando así la pérdida de mercadería por descuidos o fallas técnicas.

---

### 🛠️ ¿Cómo lo armé? (Mis herramientas)
Para esta primera versión, usé componentes sencillos pero efectivos:

* **Cerebro:** ESP32 (mi primer contacto con este microcontrolador).
* **Sensores:** 2 sensores DS18B20 (modelos sumergibles para que resistan las condiciones del frío).
* **Conexión:** Una resistencia de 4.7kΩ y cables *jumper* en protoboard.

**El camino de los datos:**
Logré que el ESP32 se conecte al WiFi y envíe la señal a un script de Google (**Apps Script**), manteniéndome actualizado sobre las temperaturas de la cámara en tiempo real.

---

### 📈 Lo que aprendí (Rol de Analista Jr.)
* **La automatización es clave:** Dejé de anotar temperaturas a mano; ahora el sistema lo hace de forma autónoma cada ciertos minutos.
* **Visualización de datos:** Creé un gráfico dinámico en Google Sheets que se actualiza solo, permitiéndome identificar rápidamente las variaciones.
* **Estructura y Timestamp:** Entendí la importancia de que cada registro tenga su fecha y hora exacta (*timestamp*) para analizar el comportamiento histórico.

**Reflexión:** Analizar estos datos me permite entender con precisión a qué temperatura se apaga y se enciende el motor. Además, puedo medir el impacto térmico exacto de dejar la puerta abierta al sacar productos.

![Datos de Temperatura](img/excel%20temperatura.png)

---

### 🚀 Lo que quiero mejorar (Mi Hoja de Ruta)
Como este es mi primer prototipo, todavía tiene mucho camino por recorrer:

1.  **Migración a Base de Datos:** Actualmente subo datos cada 1 minuto, lo que hará que el Excel sea difícil de manejar a largo plazo. Mi siguiente paso es implementar una base de datos real.
2.  **Monitoreo Energético y Alertas:** Quiero agregar un sensor de corriente para medir el consumo eléctrico y calcular el "gasto por grado Celsius". También planeo añadir una batería de respaldo y un módulo 4G para recibir alertas al celular si hay cortes de luz.
3.  **Análisis Avanzado:** Con un histórico mayor, quiero responder preguntas clave: ¿Es eficiente la cámara? ¿Qué diferencia hay entre la temperatura real y la que muestra el sensor del equipo? ¿Cómo varía el consumo entre verano e invierno?
4.  **Ecosistema IoT:** Mi meta final es integrar una **Raspberry Pi** con comunicación **MQTT**, una base de datos estructurada y visualizaciones profesionales en **Grafana**.
