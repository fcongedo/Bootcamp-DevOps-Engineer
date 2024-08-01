# Módulo 5: Administración de Particiones y RAID

En este desafío, abordaremos la administración de particiones utilizando LVM (Logical Volume Manager) y RAID (Redundant Array of Independent Disks). Además, configuraremos conexiones SSH utilizando llaves en lugar de contraseñas para mejorar la seguridad.

## Objetivo

El objetivo de este desafío es:

- Administrar particiones utilizando LVM y RAID.
- Realizar tareas de backup y asegurar las conexiones remotas mediante SSH usando llaves en lugar de contraseñas.

## LVM (Logical Volume Manager)

1. **Agregar Discos y Crear Particiones**
   - Agregar 4 discos a la máquina virtual (mínimo 2 de 1GB y 2 de 2GB).
   - Crear una partición en cada disco que ocupe todo el espacio disponible y formatearla como LVM.

2. **Crear Volúmenes Físicos y Grupos de Volúmenes**
   - Crear 4 volúmenes físicos con las particiones creadas:
     - `pv-1`
     - `pv-2`
     - `pv-3`
     - `pv-4`
   - Crear 2 grupos de volúmenes:
     - `volgroup-1` con `pv-1` y `pv-2`.
     - `volgroup-2` con `pv-3` y `pv-4`.

3. **Crear Volúmenes Lógicos**
   - Crear 5 volúmenes lógicos:
     - `lv-1` (300M, `volgroup-1`)
     - `lv-2` (1.4G, `volgroup-1`)
     - `lv-3` (2.5G, `volgroup-2`)
     - `lv-4` (200M, `volgroup-2`)
     - `lv-5` (500G, `volgroup-2`)

4. **Formatear y Montar Volúmenes Lógicos**
   - Crear un sistema de archivos ext4 en `lv-2` y montarlo en `/home/<usuario>/desafio5`.
   - Crear un sistema de archivos ext3 en `lv-5` y montarlo en `/home/<usuario>/resize`.

5. **Guardar Información de LVM**
   - Guardar la salida de los siguientes comandos en un archivo llamado `lvinfo.txt`:
     - `pvdisplay`
     - `vgdisplay`
     - `lvdisplay`

6. **Modificar Volúmenes Lógicos**
   - Eliminar `lv-1`, `lv-2`, `lv-3` y `lv-4`.
   - Extender `lv-5` en 2.5G.
   - Remover `pv-1` y `pv-2` de `volgroup-1` y agregarlos a `volgroup-2`.
   - Extender `lv-5` en 2G.

7. **Guardar Información de LVM Después de Cambios**
   - Guardar la salida de los comandos en un archivo llamado `lvinfo-2.txt`.

8. **Limpiar Volúmenes Lógicos**
   - Eliminar todo lo relacionado con volúmenes lógicos (pv, vg y lv) y cambiar el tipo de partición de LVM a Linux.

## RAID

1. **Crear RAID 0**
   - Utilizar 2 particiones para crear un RAID 0, formatearlo como ext4 y montarlo en un directorio de tu elección.
   - Documentar la salida del comando `mdadm -D` para el dispositivo RAID.
   - Apagar la máquina virtual, remover uno de los 2 discos del RAID y verificar si el archivo sigue existiendo.

2. **Crear RAID 1**
   - Utilizar 2 particiones para crear un RAID 1, formatearlo como ext4 y montarlo en `/etc/servicio-crítico`.
   - Crear un directorio llamado "configuración" dentro del RAID 1.
   - Documentar la salida del comando `mdadm -D` para el dispositivo RAID.
   - Apagar la máquina virtual, remover uno de los 2 discos del RAID y verificar si el directorio sigue existiendo.

3. **Crear RAID 5**
   - Agregar 3 discos de 1GB cada uno, crear particiones de tipo Linux y utilizarlas para crear un RAID 5.
   - Formatear el RAID 5 como ext4 y montarlo en `/etc/servicio-web`.
   - Crear un directorio llamado "configuración" dentro del RAID 5.
   - Documentar la salida del comando `mdadm -D` para el dispositivo RAID.
   - Apagar la máquina virtual, remover uno de los 3 discos del RAID y verificar si el directorio sigue existiendo.

## SSH

1. **Configurar Conexiones SSH**
   - Crear un par de llaves SSH en una máquina secundaria o en el host.
   - Copiar la llave pública al host principal para permitir la conexión SSH sin contraseña.
   - Verificar la conexión SSH sin contraseña.
   - Deshabilitar el login SSH con contraseña y verificar que la conexión SSH con llave aún funcione.
   - Volver a habilitar el login SSH con contraseña y verificar que funcione nuevamente.

## Entregables

- **Instructivo:** Instrucciones detalladas para realizar todas las tareas del desafío.
- **Archivo `lvinfo.txt`:** Información de los volúmenes lógicos antes de modificaciones.
- **Archivo `lvinfo-2.txt`:** Información de los volúmenes lógicos después de modificaciones.
- **Archivos de Configuración de SSH:** Archivos de configuración modificados en el servidor (sin llaves).

Recuerda seguir las instrucciones al pie de la letra para los entregables.
