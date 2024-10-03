# Multicloud-X

# Proyecto RPA con Flask, Selenium y Gunicorn

Este proyecto es un Robot de Procesos Automatizados (RPA) que verifica el stock de productos en línea usando Selenium y Google App Engine. Se ha desarrollado como un demo para un webinar, donde se muestra cómo automatizar la consulta de stock de un producto en un sitio web como MercadoLibre o Amazon. Los resultados son enviados por correo electrónico y almacenados en Google Firestore para su registro.

**Tecnologías Utilizadas**
1. **Python** 3.12
2. **Flask:** Framework ligero para la creación de APIs y manejo de solicitudes.
3. **Selenium:** Para automatizar la navegación y scraping en los sitios web.
**Google Cloud Platform (GCP):**
5. **App Engine:** Para desplegar y ejecutar el RPA.
6. **Secret Manager:** Almacenamiento seguro de credenciales y secretos.
7. **Firestore:** Para registrar los resultados de la verificación de stock.
8. **Gunicorn:** Servidor WSGI para la producción.

**Funcionalidades Principales**
- **Verificación de Stock:** El RPA accede a la página de un producto en línea, verifica si hay stock disponible y obtiene el estado actual.
- **Almacenamiento en Firestore:** Cada consulta de stock se guarda en Firestore para su historial.
- **Envío de Correo:** Si se detecta un cambio en el stock, se envía una notificación por correo.
- **Seguridad:** Las credenciales y secretos se almacenan de forma segura usando Google Secret Manager.

## Requisitos previos

Antes de comenzar, asegúrate de tener instalado:

- **Google Cloud SDK**: Para desplegar la aplicación en Google Cloud.

## Ejecución en local

Este programa se puede probar a nivel local simplemente ejecutando el archivo **main.py** y enviando solicitudes mediante Postman o desde un navegador.

### Importante:

1. El programa está creado para un entorno de pruebas, por lo que se recomienda incorporar **Celery** o similar para un ambiente de producción que soporte de manera estable varios clientes en simultáneo y llamadas seguidas a la API.

2. Algunos sitios web implementan medidas anti webscraping, lo que es muy común en sitios de tiendas online como MercadoLibre. En caso de que el sitio arroje algún error, intentar nuevamente o con una URL de un sitio diferente.
