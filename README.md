# COLUMNA   TUPLA   RELACIÓN

### Comandos que tuve que hacer para configurar el mysql 

~~~

sudo pacman -Sy mysql

# Verifica el estado de los servicios mysql y mysqld
systemctl status mysql.service
systemctl status mysqld.service

# Inicia el servicio mysqld
sudo systemctl start mysqld

# Verifica el log del servicio mysqld para ver los errores
journalctl -xeu mysqld.service

# Instala la base de datos de mysql
sudo mysql_install_db --user=mysql --basedir=/usr --datadir=/var/lib/mysql

# Inicializa la base de datos de mysql
sudo mysqld --initialize --user=mysql

# Borra todos los archivos de la base de datos y vuelve a inicializar
sudo rm -rf /var/lib/mysql/*
sudo mysqld --initialize --user=mysql

# Borra todos los archivos de la base de datos (incluso los ocultos)
# y cambia el propietario de la carpeta /var/lib/mysql a mysql:mysql
sudo bash -c 'rm -rf /var/lib/mysql/* /var/lib/mysql/.*; chown -R mysql:mysql /var/lib/mysql'
~~~

~~~
sudo mysqld --initialize --user=mysql

sudo mysqld --initialize --user=mysql
2025-04-09T07:48:16.292467Z 0 [System] [MY-015017] [Server] MySQL Server Initialization - start.
2025-04-09T07:48:16.293598Z 0 [Warning] [MY-010915] [Server] 'NO_ZERO_DATE', 'NO_ZERO_IN_DATE' and 'ERROR_FOR_DIVISION_BY_ZERO' sql modes should be used with strict mode. They will be merged with strict mode in a future release.
2025-04-09T07:48:16.293668Z 0 [System] [MY-013169] [Server] /usr/bin/mysqld (mysqld 9.2.0) initializing of server in progress as process 283053
2025-04-09T07:48:16.304679Z 1 [System] [MY-013576] [InnoDB] InnoDB initialization has started.
2025-04-09T07:48:17.723763Z 1 [System] [MY-013577] [InnoDB] InnoDB initialization has ended.
2025-04-09T07:48:20.009089Z 6 [Note] [MY-010454] [Server] A temporary password is generated for root@localhost: xxxxxxxxxxxxx
2025-04-09T07:48:23.891964Z 0 [System] [MY-015018] [Server] MySQL Server Initialization - end
~~~

~~~
sudo systemctl start mysqld

#  Este comando inicia el servicio MySQL en un sistema Linux. `systemctl` es una herramienta de administración para controlar el sistema y los servicios de administración, y `mysqld` es el nombre del servicio de MySQL.


mysql -u root -p  xxxxxxxxxxxx

# Este comando se utiliza para iniciar sesión en el servidor MySQL con el usuario `root`. La opción `-u` especifica el nombre de usuario (`root`), y `-p` indica que se proporcionará una contraseña. `xxxxxxxxxxxx` es un marcador de posición para la contraseña real que debe ser ingresada.


ALTER USER 'root'@'localhost' IDENTIFIED BY 'xxxxxxxxxxxx';

# Este comando de SQL se usa para cambiar la contraseña del usuario `root` en el servidor MySQL. `'root'@'localhost'` especifica el usuario `root` que se conecta desde `localhost`, y `'xxxxxxxxxxxx'` es un marcador de posición para la nueva contraseña que se desea establecer.

~~~


## Pasos para arrancar a  crear la  base de datos

~~~
CREATE DATABASE clients_db;
~~~

~~~
USE clients_db;
~~~

~~~
CREATE TABLE clients (

    name varchar (100),
    email varchar (60),
    phone_nember varchar (15)

);


CREATE TABLE products (
    name VARCHAR (20),
    sku VARCHAR (15),
    slug VARCHAR (20),
    description TEXT,
    price float
);
~~~
