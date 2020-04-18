# KillMaintenance
KillMaintenance are a set of CodeSmith templates for rapid development, 
generating the user interface from the table structures in the database.

## Some of the dependencies it has::
They are Wisej https://wisej.com/ (which is a Framework for the development of business Web Applications), SmartXLS http://www.smartxls.com/ (Library to export data to excel), Entityframework 6.4 (ORM), NInject (Dependency Manager) http://www.ninject.org/ and SqlServer. The MVP design pattern is implemented (https://es.wikipedia.org/wiki/Modelo%E2%80%93vista%E2%80%93presentador) and Dependency Injection.

## Features
Multitenance, MultiLanguage, Automatic Validations obtained from the definition of data in the database, CRUD and Automatic Search, scheme for tests (Unit Test of presenter)

## Restrictions
All must have a primary key Called Id that can be Int or Long, all the tables must have the following fields: Creado (Varchar), FechaCreado (DateTime), Modificado (Varchar) and FechaModificado (DateTime)

![Screen of CodeSmith running KillMaintenance](/assets/CodeSmith.PNG)
![Screen en Visual Studio showing an example of  Maintenance generated](/assets/Pantallagenerada.PNG)

## License
[MIT](https://choosealicense.com/licenses/mit/)

