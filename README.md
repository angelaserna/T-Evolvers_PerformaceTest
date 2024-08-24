##Introducción

Este proyecto es un reto técnico construido con la herramiento JMeter para realizar pruebas de performance al Api.
Para estas pruebas se utilizaron las api's de Restful Booker HerokuApp.

# Pruebas de API con JMeter

Este proyecto contiene scripts de pruebas diseñados para evaluar las API disponibles en [Restful Booker](https://restful-booker.herokuapp.com/apidoc/index.html). Se utiliza Apache JMeter para realizar estas pruebas.

## Contenido del Proyecto

- `performance_test_plan.jmx`: Archivo principal de JMeter que contiene la configuración de las pruebas.
- `README.md`: Este archivo con instrucciones sobre cómo ejecutar las pruebas.

## Requisitos

Para ejecutar las pruebas, necesitarás:

- [Apache JMeter](https://jmeter.apache.org/download_jmeter.cgi) instalado en tu máquina.
- [Java](https://www.oracle.com/java/technologies/javase-downloads.html) instalado, ya que JMeter requiere Java para ejecutarse.

## Configuración

1. **Descargar e Instalar JMeter**:

   - Descarga la última versión de JMeter desde [el sitio oficial](https://jmeter.apache.org/download_jmeter.cgi).
   - Descomprime el archivo descargado en una ubicación adecuada en tu sistema.

2. **Configurar JMeter**:

   - Asegúrate de que `JAVA_HOME` esté configurado correctamente en tu sistema.

3. **Cargar el Plan de Prueba**:

   - Abre JMeter.
   - Carga el archivo `performance_test_plan.jmx` desde el menú `File > Open`.

## Ejecución de Pruebas

Para ejecutar las pruebas, sigue estos pasos:

1. **Abrir JMeter**:

   - Ejecuta el script `jmeter` (en Linux/macOS) o `jmeter.bat` (en Windows) desde el directorio `bin` de la instalación de JMeter.

2. **Cargar el Plan de Prueba**:

   - En la interfaz gráfica de JMeter, ve a `File > Open` y selecciona `test-plan.jmx`.

3. **Configurar Parámetros de Prueba** (opcional):

   - Puedes ajustar los parámetros de prueba según sea necesario, como la cantidad de usuarios, el tiempo de ramp-up, etc., en el `Thread Group`.

4. **Ejecutar la Prueba**:

   - Haz clic en el botón de inicio (ícono de play) en la barra de herramientas para comenzar la ejecución de la prueba.

5. **Ver Resultados**:

   - Puedes ver los resultados en la interfaz de JMeter a través de diferentes listeners, como el `View Results Tree`, `Summary Report`, o `Aggregate Report`.

## Estructura del Archivo JMX

El archivo `performance_test_plan.jmx` está estructurado de la siguiente manera:

- **Thread Group**: Define el grupo de hilos que simulan a los usuarios concurrentes.
- **HTTP Request Sampler**: Configura las solicitudes HTTP a las APIs de Restful Booker.
- **Listeners**: Configuran cómo se recopilan y muestran los resultados de las pruebas.

## Ejemplos de Solicitudes

El plan de prueba incluye ejemplos de solicitudes a varios endpoints de la API Restful Booker, como:

- **Crear un token**: `POST /booking`
- **Crear una reserva**: `POST /booking`
- **Obtener lista reservas**: `GET /booking`

Consulta la documentación de la API en [Restful Booker API Documentation](https://restful-booker.herokuapp.com/apidoc/index.html) para más detalles sobre cada endpoint.

## Resultados y Reportes

Los resultados de las pruebas se almacenan en el archivo de salida especificado en los listeners del plan de prueba. Puedes analizar estos resultados para evaluar el rendimiento y la funcionalidad de las APIs.

## Contribuciones

Si deseas contribuir a este proyecto, por favor sigue estos pasos:

1. Realiza un fork del repositorio.
2. Crea una rama para tus cambios.
3. Envía un pull request con una descripción clara de tus modificaciones.

## Soporte

Para cualquier pregunta o problema relacionado con estas pruebas, por favor contacta a [tu contacto o soporte].

## Licencia

Este proyecto está licenciado bajo la Licencia [tu licencia].

---

# Estrategia de Pruebas de Rendimiento para Restful Booker API

## Requisitos No Funcionales (RNF)
1. Tiempo de respuesta < 2000 ms.
2. Manejo de al menos 1000 usuarios concurrentes.
3. Tasa de errores < 1%.
4. Capacidad de escalar bajo carga incremental.

## Entorno de Prueba
- *Herramienta*: Apache JMeter 5.4.1
- *Entorno*: Entorno controlado con acceso estable a Internet.

## Plan de Pruebas
### Configuración de JMeter
- *Thread Group*: 1000 usuarios, 60 segundos de ramp-up.
- *Endpoints probados*: GET /booking, POST /booking, PUT /booking/{id}, DELETE /booking/{id}.

### Escenarios de Prueba
1. Prueba de Carga
2. Prueba de Estrés
3. Prueba de Resistencia
4. Prueba de Pico

## Ejecución y Resultados
- Documentar resultados detallados aquí.

## Conclusiones
Conclusiones sobre el desempeño de la API y recomendaciones.