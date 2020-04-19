# KillMaintenance
KillMaintenance are a set of CodeSmith (https://www.codesmithtools.com/) templates for fast development, 
generating the user interface from the table structures in the database.

## Some of the dependencies it has:
They are Wisej https://wisej.com/ (which is a Framework for the development of business Web Applications),Wisej.Ext.MaterialDesign, SmartXLS http://www.smartxls.com/ (Library to export data to excel), Entityframework 6.4 (ORM), NInject (Dependency Manager) http://www.ninject.org/ and SqlServer. The MVP design pattern is implemented (https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93presenter) and Dependency Injection.

## Features
Multitenance, MultiLanguage, Automatic Validations obtained from the definition of table structure in the database, CRUD and Automatic Search, scheme for tests (Unit Test of presenter)

## Restrictions
All tables must have a primary key Called Id(Identity) that can be Int or BigInt, all the tables must have the following fields: Creado (Varchar), FechaCreado (DateTime), Modificado (Varchar) and FechaModificado (DateTime)

## Screen of CodeSmith running KillMaintenance
![Screen of CodeSmith running KillMaintenance](/assets/CodeSmith.PNG) (https://www.youtube.com/watch?v=Y8rvl_QEhXk)

## Screen in Visual Studio showing an example of  Maintenance generated
![Screen en Visual Studio showing an example of  Maintenance generated](/assets/Pantallagenerada.PNG)

## License
[MIT](https://choosealicense.com/licenses/mit/)

