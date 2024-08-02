# Módulo 6: Creación e Interacción con Servicios Básicos de AWS

## Objetivo

El objetivo de este desafío será crear algunos servicios básicos en nuestra cuenta de AWS e interactuar con ellos. Primero tendremos que verificar los prerrequisitos, en caso de ya cumplirlos, aclararlo en el instructivo. Luego crearemos una instancia EC2, un bucket S3 y un volumen de EBS.

## Desafío

### Prerrequisitos:

1. Crear cuenta de AWS (si ya la tienen, no es necesario crear una nueva) (pueden crearla siguiendo el instructivo enviado por mail previamente).
2. Crear un usuario con permisos de administrador (admin full access).
3. Loguearse a la cuenta como este usuario.
4. Definir una serie de tags que agreguen información a nuestros recursos, por ejemplo:
   - Owner: Zdenko
   - Email: zdenko.hraste@educacionit.com
   - Team: Cloudops
   - Project: Desafio-M6
5. Todos los recursos los crearemos en la región us-east-1 en la AZ us-east-1a a menos que se especifique lo contrario.
6. Todos los recursos que crearemos tendrán que tener los tags que definimos más arriba, además de un nombre descriptivo.

### Elastic Cloud Compute (EC2)

1. Crear una instancia EC2 dentro de los parámetros de free tier.
2. Configurar la conexión remota, la misma podrá ser a través de SSM, utilizando la llave de SSH y conectarnos desde nuestra VM con Linux, etc. A elección de ustedes. Una vez configurado, verifiquen la conexión.

### Simple Storage Service (S3)

1. Crear bucket S3, tengan en cuenta que el nombre del bucket debe ser único.
2. Subir este PDF como prueba al bucket S3 y verificación de que funciona de forma correcta.

### Elastic Block Store (EBS)

1. Crear un volumen de EBS y linkearlo a la instancia que creamos previamente (recuerden verificar que ambos estén en la misma región y AZ), usar valores por defecto y un tamaño de 2GB.
2. Una vez que verificamos que el volumen se agregó de forma correcta a nuestro sistema, formatear el EBS como ext4, agregarlo al FSTAB y que el FS se monte en el directorio `/desafíos`. Montar el FS y verificar que se puede escribir en el mismo.
3. Una vez montado el FS, descargar el desafío que subimos al bucket de S3 y mover el archivo al directorio `/desafíos` (Para la descarga, se pueden utilizar diferentes formas como por ejemplo usar la AWS CLI, usar wget, etc. en base a la forma que utilicen tendrán que cambiar los permisos del bucket).
4. **IMPORTANTE**: Por último, una vez documentado todo en el instructivo, realizar una limpieza de recursos eliminando todo lo creado.
