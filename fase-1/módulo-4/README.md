# Módulo 4: Administración de Usuarios, Grupos y Automatización de Tareas

## Descripción del Desafío

El objetivo de este desafío es gestionar usuarios y grupos en el sistema, configurar permisos, y utilizar herramientas de automatización para ejecutar comandos periódicamente. Además, se realizará una limpieza de usuarios para completar el ciclo.

## Administración de Grupos y Usuarios

1. **Creación de Usuarios:**
   - Crear los usuarios: Mariano, Luis y Jose, asegurando que sus directorios home sean creados.

2. **Creación de Grupos:**
   - Crear los grupos: Administradores, Desarrolladores y Operaciones.

3. **Modificaciones:**
   - Mariano: Miembro del grupo Administradores (primario).
   - Luis: Miembro del grupo Desarrolladores (primario).
   - Jose: Miembro de los grupos Administradores (primario) y Operaciones (secundario).

4. **Permisos de Sudo:**
   - Los miembros del grupo Administradores pueden ejecutar cualquier comando como sudo sin contraseña.
   - Los miembros del grupo Operaciones pueden ejecutar los comandos `mount` y `umount` como sudo, pero deben usar la contraseña.

5. **Estructura de Directorios y Archivos:**
   - **Mariano:**
     - `Scripts/ping.sh`: Script que hace ping a www.google.com.ar (Permisos 2770, owner Mariano, grupo Administradores).
     - `Scripts/kick.sh`: Script con permisos rwx-rwx- (owner Mariano, grupo Administradores).
     - `docs/test.txt`: Archivo con permisos rwxrwx--- (owner Mariano, grupo Administradores).
     - `docs/readme.txt`: Archivo con permisos 660 (owner Mariano, grupo Administradores).

   - **Luis:**
     - `feat-1/index.html`: Archivo HTML con permisos ugo=664 (owner Luis, grupo Luis).
     - `feat-1/readme.txt`: Archivo con permisos rwxrwxr-- (owner Luis, grupo Desarrolladores).
     - `feat-2/tests`: Archivo con permisos rwxrwxr-- (owner Luis, grupo Luis).

   - **Jose:**
     - `ops/script.sh`: Script con permisos 4770 (owner Jose, grupo Operaciones).
     - `ops/test.sh`: Script con permisos rwxr--r-- (owner Jose, grupo Operaciones).
     - `adm/mount.sh`: Script con permisos rwxrwxr-x (owner Jose, grupo Administradores), con un ACL que restringe la ejecución por Mariano.
     - `procedures/kick.txt`: Archivo con permisos rwxrwxr-- (owner Jose, grupo Operaciones).

6. **Acciones Adicionales:**
   - Bloquear el acceso del usuario Luis (sin borrar el usuario).
   - Forzar un cambio de contraseña para el usuario Jose en su próximo login.
   - Configurar el vencimiento de la contraseña del usuario Mariano en 7 días.

## Automatización de Tareas

1. **Crontab para Mariano:**
   - Agregar una línea para ejecutar el script `ping.sh` cada 5 minutos.

2. **Crontab para Jose:**
   - Agregar una línea para ejecutar `echo $USER > /procedures/kick.txt` a las 18:00 de cada día.

3. **Crontab General del Sistema:**
   - Agregar una línea para ejecutar `free -m` como Mariano a las 06:15, 12:30 y 18:45 de los lunes.
   - Agregar una línea para ejecutar `df -h` como Jose cada minuto entre las 15:30 y las 15:35 el día 17 del mes.

4. **Copia y Eliminación de Usuarios:**
   - Crear el archivo `/tmp/usuarios-eliminados.txt` y registrar los usuarios eliminados.
   - Automatizar la eliminación de usuarios con el comando `at`:
     - Eliminar a Jose y su home en 5 minutos.
     - Eliminar a Luis y su home en 10 minutos.
     - Eliminar a Mariano y su home en 15 minutos.

## Entregables

- **Instructivo:** Documento que describe detalladamente todos los pasos realizados.
- **Directorios Home:** Contenido de los directorios home de los usuarios Mariano, Jose y Luis, con todos los archivos y permisos.
- **Crontabs:**
  - `crontab-mariano.txt`: Crontab del usuario Mariano.
  - `crontab-jose.txt`: Crontab del usuario Jose.
  - `crontab-general.txt`: Crontab general del sistema.


