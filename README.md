### Princess Prado
### Modulo 5, Practica 1

# Ejecución de contenedores Docker

## Imagenes utilizadas 
1. **PostgresSQL** (`latest`) 
2. **MariaDB** (`jammy`)
3. **Nginx** (`alpine`)

## Comandos Utilizados 

### 1. Descargar Imagenes (Pull)

```bash
# Descargar PostgreSQL oficial
docker pull postgres:latest

# Descargar MariaDB oficial (versión jammy)
docker pull mariadb:jammy

# Descargar Nginx oficial (versión alpine)
docker pull nginx:alpine

# Ver las imágenes locales
docker images
```
<img width="646" height="148" alt="image" src="https://github.com/user-attachments/assets/cc0edc4d-7345-4454-955a-003b1932a713" />

### 2. Ejecutar Contenedores (Run)

### Descripción de cada Contenedor 

1. PostgreSQL: Sistema de base de datos relacional y de objetos de código abierto. Se ejecuta en el puerto 5432. Es
ampliamente utilizado en aplicaiones empresariales por su robuztes y cumplimineto de estándares SQL.
2. MariaDB (jammy): Sistema de gestión de datos relacional compatible con MySQL. Utiliza la etiqueta jammy, construida sobre Ubuntu 22.04 LTS. Se ejecutaen el puerto 3306.
3. Nginx (alpine): Servidor web de alto rendimiento basado en Alpine Linux. Esta versión es extremadamente ligera (aproximadamente 25MB vs 180MB de la versión normal), ideal para contenedores docker. Se ejecuta en el puerto 80 y es perfecto para entornos de produción que requieren eficiencia y seguridad. 

```bash
# Ejecutar PostgreSQL
docker run --name mi-postgres \
  -e POSTGRES_PASSWORD=mipassword \
  -e POSTGRES_USER=miusuario \
  -e POSTGRES_DB=mibase \
  -p 5432:5432 \
  -d postgres:latest

# Ejecutar MariaDB (Usando etiqueta jammy)
docker run --name mi-mariadb \
  -e MYSQL_ROOT_PASSWORD=rootpassword \
  -e MYSQL_DATABASE=mibase \
  -e MYSQL_USER=miusuario \
  -e MYSQL_PASSWORD=mipassword \
  -p 3306:3306 \
  -d mariadb:jammy

# Ejecutar Nginx (Usando versión alpine)
docker run --name mi-nginx \
  -p 80:80 \
  -d nginx:alpine
````

#### ¿Que son los parámetros que se usan?
1. --name: Asigna un nombre único al contenedor
2. -e: Establece variables de entorno
3. -p: Mapea puertos del host con los del contenedor
4. -d: Ejecuta en modo detached (en segundo plano)

### Para ver los contenedores Activos
````bash
# Ver Contenedores activos
docker ps
````
<img width="1054" height="119" alt="image" src="https://github.com/user-attachments/assets/9f34738e-7e66-4b89-b3bf-319793420657" />

### Para detener un contenedor
```bash
# Detener Contenedores
docker container stop 59f
```

<img width="318" height="71" alt="image" src="https://github.com/user-attachments/assets/cdfd7c4c-7826-4d72-9293-28a016ac0e42" />
<img width="1159" height="143" alt="image" src="https://github.com/user-attachments/assets/1ede3e55-a109-4979-9c1b-86330ee73bf0" />

### Para Eliminar un contenedor 
```bash
# Eliminar Contenedor
docker container rm 59f
````
<img width="322" height="74" alt="image" src="https://github.com/user-attachments/assets/90aeacd4-4684-4174-b6d9-91417b8cd15e" />
<img width="1037" height="111" alt="image" src="https://github.com/user-attachments/assets/cb4d8e53-24b7-44f8-aabe-33a6660e8bfa" />

### Para eliminar una imagen
```bash
# Eliminar Imagen
docker rmi postgres:latest
````
<img width="587" height="91" alt="image" src="https://github.com/user-attachments/assets/d8f06e81-a268-46d4-9027-098b79e2d8a8" />
<img width="517" height="128" alt="image" src="https://github.com/user-attachments/assets/06a1e9d9-5a55-438b-a07e-66987dd5be68" />







