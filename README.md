# KillMaintenance
KillMaintenance son un conjunto de plantillas de CodeSmith para hacer desarrollo rapido,
Generando la interfaz de usuario a partir de las estructuras de las tablas en la base de datos

## Algunas de las dependencias que tiene:
Son Wisej https://wisej.com/ (que es un Framework para desarrollo de Aplicaciones Web empresariales),
SmartXLS http://www.smartxls.com/ (Libreria para exportar datos A excel),
Entityframework 6.4 (ORM),
NInject(Manejador de Dependencias) http://www.ninject.org/ y
SqlServer. Se implementa el patron de diseno MVP(https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93presentador) e Inyeccion  de Dependencias.
## Features
Multitenance,MultiLenguaje,Validaciones Automaticas obtenidas de la definicion de datos en la base de datos, CRUD y Busquedas Automaticas,
esquema para pruebas (Unit Test del presenter)
## Restricciones
Todas deben tener un primary key Llamado Id que puede ser Int o Long,
todas las tablas deben tener los siguientes campos:
Creado(Varchar),FechaCreado(DateTime),Modificado(Varchar) y FechaModificado(DateTime)

https://github.com/jrtaveras/KillMaintenance/blob/master/assets/CodeSmith.PNG

## License
[MIT](https://choosealicense.com/licenses/mit/)

