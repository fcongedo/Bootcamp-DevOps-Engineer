# Módulo 2: Administración de Discos y Filesystems

## Descripción del Desafío

El objetivo de este desafío es administrar un nuevo disco en una máquina virtual. Esto incluye agregar un nuevo disco, particionarlo, formatearlo, montar los sistemas de archivos y realizar configuraciones adicionales de archivos y directorios.

## Pasos Realizados

1. **Agregar un Nuevo Disco:**
   - Se añadió un nuevo disco de al menos 2 GB a la máquina virtual.

2. **Creación de Particiones:**
   - Se crearon 4 particiones primarias:
     - 1 partición de tipo swap.
     - 3 particiones de tipo Linux (default).

3. **Formateo de Particiones:**
   - La partición de tipo swap fue formateada como swap.
   - Una partición fue formateada como `ext3`.
   - Otra partición fue formateada como `ext4`.
   - La última partición fue formateada como `xfs`. (En caso de no tener `xfs` disponible, se realizó la instalación correspondiente).

4. **Montaje de Filesystems:**
   - Los filesystems fueron montados automáticamente en `/etc/fstab` con la siguiente configuración:
     - `ext3` en `/data/manuales`
     - `ext4` en `/data/laboratorios`
     - `xfs` en `/data/exámenes`
   - Se guardó el contenido del archivo `/etc/fstab` en `salida-fstab.txt`.

5. **Creación de Enlaces Simbólicos:**
   - Se crearon los siguientes enlaces:
     - Softlink entre `/data/manuales` y `/home/fase1/modulo2/manuales`
     - Softlink entre `/data/laboratorios` y `/home/fase1/laboratorios`
     - Hardlink entre `/data/exámenes` y `/home/fase1/exámenes`

6. **Verificación de Enlaces Simbólicos:**
   - Se verificó el funcionamiento de los enlaces simbólicos. En caso de fallos, se documentaron los errores.
   - Se creó un hardlink entre `/data/exámenes/fase1/modulo1.txt` y `/data/exámenes/sysadmin/modulo1.txt` (creando el archivo original si era necesario).

7. **Documentación Adicional:**
   - Listado de particiones del nuevo disco junto con el directorio de montaje y el porcentaje de utilización.
   - Permisos de los enlaces simbólicos y hardlinks, y comparación con otros directorios.
   - Información de los directorios de los enlaces, incluyendo los inodos utilizados por el archivo original y el creado por el enlace.

## Archivos de Salida

- **`salida-fstab.txt`**: Contiene el contenido del archivo `/etc/fstab` después de agregar los nuevos sistemas de archivos.

Estos archivos se encuentran en esta carpeta y forman parte de los entregables del desafío. Para una guía detallada del proceso y capturas de pantalla, consulta el archivo instructivo proporcionado.

## Documentación Adicional

Consulta el archivo instructivo en la carpeta compartida para una guía paso a paso del proceso seguido para completar este desafío, incluyendo imágenes y comandos utilizados.
