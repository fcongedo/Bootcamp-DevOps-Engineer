# Módulo 1: Instalación y Configuración de Linux

## Descripción del Desafío

El objetivo de este desafío es realizar la instalación y configuración de una distribución de Linux en una máquina virtual siguiendo una serie de pasos específicos. Esto incluye la instalación del virtualizador, la creación y configuración de la máquina virtual, la instalación del sistema operativo, y la gestión de discos y particiones.

## Pasos Realizados

1. **Instalación de Virtualizador:**
   - Se instaló VirtualBox para crear y gestionar la máquina virtual.

2. **Creación de la Máquina Virtual:**
   - Se creó una máquina virtual con las siguientes especificaciones recomendadas:
     - **CPU:** 2
     - **Memoria:** 4096 MB
     - **Disco:** 10 GB
   - Se configuró el adaptador de red como adaptador puente.

3. **Instalación del Sistema Operativo:**
   - Se instaló una distribución de Linux desde una imagen ISO.
   - Se configuró una IP estática para la máquina virtual.

4. **Clonación de la Máquina Virtual:**
   - Se realizó un clon de la máquina virtual para tener una copia de respaldo.

5. **Obtención de Información del Usuario:**
   - Utilizando el comando `grep`, se extrajo información del usuario desde el archivo `/etc/passwd`.
   - La salida del comando se guardó en el archivo `user-info.txt`.

6. **Configuración de Disco Adicional:**
   - Se añadió un segundo disco de al menos 2 GB a la máquina virtual.
   - Se crearon las siguientes particiones:
     - Partición primaria de al menos 1 GB de tipo Linux.
     - Partición SWAP de al menos 500 MB.
   - La información de la tabla de particiones se guardó en el archivo `partition-table.txt`.

## Archivos de Salida

- **`user-info.txt`**: Contiene la información del usuario extraída del archivo `/etc/passwd` usando `grep`.
- **`partition-table.txt`**: Contiene la información de la tabla de particiones del disco adicional.

Estos archivos se encuentran en esta carpeta y forman parte de los entregables del desafío. Para una guía detallada del proceso y capturas de pantalla, consulta el archivo instructivo proporcionado.

## Documentación Adicional

Consulta el archivo instructivo en la carpeta compartida para una guía paso a paso del proceso seguido para completar este desafío, incluyendo imágenes y comandos utilizados.
