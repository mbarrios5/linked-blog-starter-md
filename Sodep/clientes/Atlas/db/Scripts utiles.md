[[Banco Atlas]]
1. **Para obtener el schema de una tabla**
```
Select owner

from dba_tables

where table_name = 'MICHI_USERS'
```
2. **Para ver si una función se utiliza en otros paquetes**
```
SELECT * FROM dba_source WHERE LOWER(TEXT) LIKE '%fu_envia_mensaje%' ;

SELECT * FROM DBA_JOBS WHERE LOWER(WHAT) LIKE '%fu_envia_mensaje%' ;

SELECT * FROM DBA_SCHEDULER_JOBS WHERE LOWER(job_action) LIKE '%fu_envia_mensaje%' ;
```
3. **Para ver en que paquete esta el procedimiento**
```
SELECT owner, object_name, object_type

FROM all_objects

WHERE object_name = 'PAW_TAR' AND object_type = 'PACKAGE'
```
4. **Para ejecutar una función es necesario declarar una funcion anonima**
```
DECLARE

v_pedido VARCHAR2(4000);

v_respuesta VARCHAR2(4000);

BEGIN

-- JSON de prueba con los datos requeridos

v_pedido := 'algun valor de parametro'

-- Invocar la función

v_respuesta := IT.PAT_3DS.fu_stepup(v_pedido); --aca ejecuta la funcioan

-- Mostrar el resultado

DBMS_OUTPUT.PUT_LINE('Respuesta: ' || v_respuesta);

END;
```
5. Mostrar el popup
```
select a.*, a.rowid from bm_alertas awhere a.tip_alerta = 'BAN'order by a.fec_insercion desc;select * from bm_promociones a;select * from bm_alerta_personas a;select * from bm_perfiles aorder by a.fec_insercion desc; select a.*, a.rowid from bm_promocion_perfiles a; 
```
6. Para habilitar envio de correo, esto sirve para enviar correo desde atlas.Tener en cuenta volver a desabilitar el 'N'
```
DECLAREBEGIN  
BEGINUPDATE ge_par_dinamicos a  
  SET    a.val_parametro = 'S'  
  WHERE  a.parametro = 'ENV_MAI_HOMEBANKING';COMMIT;EXCEPTION  
WHEN others THEN  
  NULL;END;IT_MAIL.mail(sender => 'informacion@atlas.com.py', recipients => 'joaquin.valdivieso@atlas.com.py', subject => 'Prueba', message => 'Prueba');BEGIN  
  UPDATE ge_par_dinamicos a  
  SET    a.val_parametro = 'N'  
  WHERE  a.parametro = 'ENV_MAI_HOMEBANKING';  
    
  COMMIT;  
  exception  
WHEN others THEN  
  NULL;  
END;EXCEPTION  
WHEN others THEN  
  BEGINUPDATE ge_par_dinamicos a  
    SET    a.val_parametro = 'N'  
    WHERE  a.parametro = 'ENV_MAI_HOMEBANKING';COMMIT;EXCEPTION  
  WHEN others THEN  
    NULL;END;END;
```

7. Para activa el modo edicion 
```
BEGIN  
  
Begin pre_ini_aplicacion; pae_cnf.G_COD_MODULO := 1; end ;  
-- Aqui va la sentencia  
COMMIT;  
  
END;
```
8. Para obtener saldo atlas adelanto
```
SELECT * FROM IT.TA_CTA_TARJETAS WHERE COD_MODALIDAD = 50 AND NRO_CTA_AHORRO IS NOT NULL
```
9. Para obtener el calendario 
```
   select * from GE_CALENDARIOS Aorder by TO_NUMBER(A.COD_MODULO) desc; Begin pre_ini_aplicacion; pae_cnf.G_COD_MODULO := 1; end ; /UPDATE GE_CALENDARIOS ASET A.FEC_ACTUAL = TRUNC(SYSDATE);COMMIT;select * from ge_snp_horarios a;Begin pre_ini_aplicacion; pae_cnf.G_COD_MODULO := 1; end ; /UPDATE ge_snp_horarios ASET A.Fecha = TRUNC(SYSDATE);COMMIT;
   
```
10. Para matar sesiones
```
-- kill update MICHI_SESSIONS   SET MICHI_SESSIONS.STATUS = 'EXPIRED'--select * from MICHI_SESSIONS aWHERE SESSION_IID = (select max(sessions.SESSION_IID)                        from michi_sessions sessions                       where sessions.COD_PERSONA = '&cod_persona')and MICHI_SESSIONS.STATUS != 'EXPIRED';update MICHI_SESSIONS_N   SET MICHI_SESSIONS_N.STATUS = 'EXPIRED'--select * from MICHI_SESSIONS_NWHERE SESSION_IID = (select max(sessions.SESSION_IID)                        from MICHI_SESSIONS_N sessions                       where sessions.COD_PERSONA = '&cod_persona')and MICHI_SESSIONS_n.STATUS != 'EXPIRED';commit;
```
11. 
```
    -- g1000 - Can't get AES configuration running-- Es porque estan los dos michi auth, el viejo y el nuevo, se debe de eliminar el viejo y dejar el nuevo select a.*, a.rowid from michi_api_register awhere a.instance_id like '%181%'and a.api_code like '%auth%'order by a.fec_in
    sercion desc;-- El viejo es puerto 8080 y el nuevo es 8090 debe de estar 
```