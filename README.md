# Proyecto: Mi primer sistema de monitoreo (Cámaras de Frío) 🌡️
¿Por qué hice este proyecto?
Todo empezó porque tenía la sospecha de que la temperatura de la cámara de frío no estaba funcionando bien. Como no quería seguir adivinando, decidí extraer datos reales directamente del equipo. Este proyecto nace de esa necesidad de pasar de "creer algo" a "verlo con datos" para evitar que se pierda mercadería por descuidos o fallas de los equipos.

¿Cómo lo armé? (Mis herramientas)
Para esta primera versión, usé componentes sencillos pero efectivos:

Cerebro: ESP32 (mi primer contacto con este microcontrolador).

Sensores: 2 sensores DS18B20 (los que son sumergibles para que aguanten el frío).

Conexión: Una resistencia de 4.7kΩ y cables jumper en protoboard.

El camino de los datos:
Logré que el ESP32 se conecte al WiFi, mande la señal a un script de Google (Apps Script) y me mantenga actualziado de la temperatura del exterior y interior de la camara de frio.

Lo que aprendí haciendo esto (Rol de Analista Jr):
Automatizar es mejor: Dejé de anotar temperaturas a mano. Ahora el sistema lo hace solo cada ciertos minutos.

Gráficos que ayudan: Hice un gráfico sencillo en Sheets que se actualiza solo. Así puedo ver rápido las variaciones de temperatura.

Orden de los datos: Entendí la importancia de que cada dato tenga su fecha y hora exacta (timestamp) para entender el comportamiento de los datos.

reflexion:entender el comportamiento de los datos me permite entender a que temperatura se apaga el motor y a que temperatura se prende el motor, ademas de saber cual es la temperatura al dejar la puerta abierta para sacar productos.
grafico en google sheet 
![Datos de Temperatura](img/excel%20temperatura.png)

Lo que quiero mejorar (Mi Hoja de Ruta) 🚀
Como este es mi primer prototipo, todavía tiene mucho por mejorar:

Migración a Base de Datos: Actualmente sube datos cada 1 minuto, lo que hará que el Excel sea difícil de manejar en poco tiempo. Mi siguiente paso es usar una base de datos real.

Monitoreo Energético y Alertas: Quiero agregar un sensor de corriente para medir el consumo de energía y calcular el "gasto por grado Celsius". También planeo añadir una batería y un módulo 4G para recibir alertas al celular si hay cortes de luz.

Análisis Avanzado: Con más datos, quiero responder preguntas clave: ¿Es eficiente la cámara? ¿Qué diferencia hay entre la temperatura real y la que muestra el sensor del equipo? ¿Cómo varía el consumo entre verano e invierno?

Ecosistema IoT: Mi meta es integrar una Raspberry Pi con comunicación MQTT, una base de datos estructurada y visualizaciones profesionales en Grafana.
