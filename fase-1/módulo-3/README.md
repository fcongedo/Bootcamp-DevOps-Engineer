# Módulo 3: Gestión de Servidores y Servicios

## Descripción del Desafío

El objetivo de este desafío es obtener información detallada de un servidor (en este caso, nuestra máquina virtual), agregar esta información a un inventario de servidores y luego instalar y configurar un servicio. Además, se verificará el funcionamiento del servicio y se revisarán los logs para asegurar que la rotación de logs se realice correctamente y evitar que se llene la partición.

## Parte 1: Inventario del Servidor

1. **Obtener Información del Servidor:**
   - **Hostname:** Nombre del servidor.
   - **IP:** IP fija del servidor.
   - **Memoria:** Cantidad de memoria asignada.
   - **Procesador:** Información sobre el número de núcleos disponibles (para máquinas virtuales).
   - **Almacenamiento:** Cantidad de almacenamiento asignado, particiones y filesystems.
   - **Sistema Operativo y Versión:** Detalle del sistema operativo y su versión.
   - **Notas:** Información adicional relevante, como si es una máquina virtual, tipo de virtualizador, etc.

2. **Archivo de Inventario:**
   - La información debe ser cargada en un archivo de Google Sheets llamado `server-inventory`. 
   - Se debe documentar el comando utilizado para obtener cada dato y agregar esta documentación al instructivo.

## Parte 2: Instalación y Configuración de Servicio

1. **Instalación del Servicio:**
   - Instala un servicio de tu elección, como un servidor web (Apache, Nginx), una base de datos (MySQL, MariaDB), un servicio de conexión remota (SSH), u otro.
   - Documenta cada paso del proceso de instalación en el instructivo.

2. **Verificación del Funcionamiento:**
   - Asegúrate de que el servicio se inicie automáticamente después de la instalación.
   - Verifica su funcionamiento mediante pruebas relevantes (acceso web, ejecución de consultas, etc.).
   - Revisa los logs para confirmar que se almacena la información de las pruebas realizadas.

3. **Configuración de Logrotate:**
   - Verifica si el servicio instalado ya tiene una configuración de logrotate. 
   - En caso contrario, crea una configuración y verifica su funcionamiento.
   - Documenta la configuración existente o la nueva, explicando cada sección y su propósito.

## Archivos de Salida

- **`server-inventory`**: Archivo con la información detallada del servidor.
- **Instructivo**: Documento detallado que incluye todos los pasos realizados, comandos utilizados, resultados obtenidos y configuración de logrotate si es necesario.

## Documentación Adicional

Consulta el archivo instructivo para una guía paso a paso del proceso seguido para completar este desafío, incluyendo imágenes y comandos utilizados.
