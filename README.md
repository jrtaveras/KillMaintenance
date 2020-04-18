# KillMaintenance
KillMaintenance are a set of CodeSmith templates for rapid development, 
generating the user interface from the table structures in the database.

## Some of the dependencies it has::
They are Wisej https://wisej.com/ (which is a Framework for the development of business Web Applications), SmartXLS http://www.smartxls.com/ (Library to export data to excel), Entityframework 6.4 (ORM), NInject (Dependency Manager) http://www.ninject.org/ and SqlServer. The MVP design pattern is implemented (https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93presentador) and Dependency Injection.

## Features
Multitenance,MultiLenguaje,Validaciones Automaticas obtenidas de la definicion de datos en la base de datos, CRUD y Busquedas Automaticas,
esquema para pruebas (Unit Test del presenter)

## Restrictions
All must have a primary key Called Id that can be Int or Long, all the tables must have the following fields: Created (Varchar), CreatedDate (DateTime), Modified (Varchar) and ModifiedDate (DateTime)

![Screen of CodeSmith running KillMaintenance](/assets/CodeSmith.PNG)
![Screen en Visual Studio showing an example of  Maintenance generated](/assets/Pantallagenerada.PNG)

## License
[MIT](https://choosealicense.com/licenses/mit/)

