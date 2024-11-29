Cliente de [[SODEP SA]]
Repositorio 
Tecnologias

**Backend** 
https://github.com/sodep/basa-be-next
1. Spring Boot

2. Java 17

**Properties**
Utilizar el example .yml , se debe cambiar el nombre del example pero si usar ese. 

**SSH**
user: SODEP
pass: Reingeneria2023*

**Caperta Docs**
Esta la documentacion de la arquitectura hexagonal


**Frontend**

1. Version del NODE 18
2. Gestor de paquete pnpm
Para base de datos 
Utiliza JPA con configuracion ddl-auto: none que hace que no cree las tablas automaticamente

Modulo administrador usuairo banca emperesa
 
**SONNAR**

```
mvn clean install verify sonar:sonar -Dsonar.projectKey=basa-be-next -Dsonar.projectName='basa-be-next' -Dsonar.host.url=http://10.1.0.4:9059 -Dsonar.token=sqp_3374758b6ad345849f34cd9c03297ae3a06e054b
```
 sonnar basa mbarrios y el pass Cambiar123




