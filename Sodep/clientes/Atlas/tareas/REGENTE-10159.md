[[Banco Atlas]]

Existes dos APIS uno favorito y otro contacto

No es optimo porque hace select en contacto y  para favoritos utiliza vista materializada



**Cambiar**
Se desea cambiar a una sola API que ya esta en desarrollo

**Nueva API**
La nueva api ya impacta directamente en la nueva tabla, alta baja listar se puede hacer todo eso en la nueva API. Esto para no llamar a los otros APIS y facilita tanto al front web y mobile.

Se quiere **deprecar** Agenda Contactos del frontend


**Tener en cuenta**
1. En transferencias antes de confirmar ya se esta llamando al **POST contacto** eso debe llamarse solo cuando se concrete la transferencia
2. Tambien guardar como contanto al finalizar 

**Lugares donde cambiar**
1. En Buscar Contacto 

**Tarea**
1. En Buscar Contacto  cambiar y llamar a la nueva API
2. Favoritos almacenar en el REDUX y luego no llamar mas, excepto cuando se haga otra transferencia, para eso tambien se debe verificar que el contacto no este en el REDUX[Esto evaluar]
3. El alias también guardar como contacto al terminar la transferencia
4. Guardar contacto al finalizar la transferencia




