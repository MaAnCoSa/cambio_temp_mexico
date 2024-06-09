# Cambio de Temperatura en México (2016 - 2019)
### Manuel Andrés Cota Santeliz

## 1 - Instalación de MySQL
Para recrear el análisis hecho en este proyecto, es necesario almacenar los datos en una base de datos local en su computadora.
Para ello, es necesario descargar MySQL Community Server. La descarga se puede hacer desde [aquí](https://dev.mysql.com/downloads/mysql/). Durante la instalación se le pedira que cree una contraseña. Recomendamos que use ```1234``` o, si no, que más adelante modifique la contraseña en ```Cambio de Temperatura.ipynb``` para que se pueda establecer la conexión a su base de datos.

## 2 - Creación de la Base de Datos
Una vez instalado MySQL, hay que buscar "MySQL Command Line Client" en las aplicaciones. Al abrirlo, lo primero que se le pedirá es la contraseña para el
usuario root que generó. Al ingresarla, tendrá acceso a la línea de comando de MySQL. Para ver todas las bases de datos que se crean por defecto, use el siguiente comando:
```sql
SHOW DATABASES;
```
Asegurese de no modificar las bases de datos creadas por default.

Ahora, hay que crear la base de datos que se llamará desde el código del análisis. Para ello, usamos el siguiente comando:
```sql
CREATE DATABASE temp;
```
Cuando se cree, podemos entrar a ella desde la linea de comando con el comando:
```sql
USE temp;
```
Después podríamos analizar todas las tablas de la base de datos usando:
```sql
SHOW TABLES;
```

Pero lo mas fácil es utilizar una interfaz visual para correr los comandos y verificar que los datos se hayan almacenado correctamente.
MySQL ofrece su propia interfaz visual [MySQL Workbench](https://dev.mysql.com/downloads/workbench/). Sin embargo, existen otras interfaces útiles para
nuestro caso, como por ejemplo [SQLite](https://sqlite.org/download.html) o [DBeaver](https://dbeaver.io/download/).

## 3 - Creación de la Tabla
Usando la interfaz gráfica, hay que entrar a la base de datos y correr el archivo ```create_temp_change.sql``` que se encuentra en este repositorio. El script se encarga de crear la tabla que contendrá los datos de cambio de temperatura.

## 3 - Importación de los Datos
Finalmente, solo debemos importar los datos a esta tabla usando la interfaz gráfica. Los datos se encuentran en el archivo ```Environment_Temperature_change_E_All_Data_NOFLAG.csv``` que se encuentra en el repositorio. También se puede obtener de su fuente origianl en [Kaggle](https://www.kaggle.com/datasets/sevgisarac/temperature-change/data).

Con los datos importados, y la tabla llena, el notebook ```Cambio de Temperatura.ipynb``` podrá acceder a los datos y correr el análisis sin problema.
