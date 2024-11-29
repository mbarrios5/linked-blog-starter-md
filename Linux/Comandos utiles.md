
1. Para hacer kill a un proceso
```
ps aux | grep dbeaver

```
kill 4355

2. Levantar en modo debug el tomcat
```
   export JPDA_ADDRESS=800  
   export JPDA_TRANSPORT=dt_socket  

Then run the tomcat server in debug mode using following command.  
%TOMCAT_HOME%/bin/catalina.sh jpda start  
o  
sudo catalina.sh jpda start

```

3. Cambiar el jdk
```
1- Camibar el .profile
2- Ejecutar para actualizar source ~/.profile

```/home/mbarrios/.jdks/corretto-17.0.12