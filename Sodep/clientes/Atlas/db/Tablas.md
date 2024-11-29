[[Banco Atlas]]

1. **IT.TA_TARJETAS**
	En esta tabla se encuentra los datos de la tarjeta de crédito su tabla asociada que contiene mas datos es **IT.TA_CTA_TARJETAS**, tambien econtramos Atlas Adelanto
2. **IT.GE_PARAMETROS**	
	Se encuentra los parametros generales, se utiliza mucho como comodín por ejemplo  para saber si esta activo o no un parametro.
3. **ah_tar_debitos**
	En esta tabla se encuentra los datos de la tarjeta de debito.
4. **ge_log_3ds**
	Registra los logs del 3dscure que es un servicio de Bancard para compras realizadas en el exterios con tarjetas de Atlas
5. **ba_vinculos**
	De aca se obtiene las personas vinculadas a una empresa
6.	**cp_men_enviados**
    Tabla que registra los SMS a enviar, un JOB obtiene los registros y luego los envia
7. **BA_MONEDAS**
    Se registra todas las monedas.
8. **GE_CUENTAS**	
    Tiene las los detalles de la cuentas del cliente por ejemplo la moneda, estado
9. **TA_CLI_ATLAS_SOS** 
    Tabla donde se guarda info del ATLAS SOS
10. **GE_MOVIMIENTOS**
	Todos los movimientos del cliente
11. **BCAMOVIL.MICHI_SESSIONS_N**
	Aca están todas las sessiones del usuarios
12. **GE_SNP_TRANSFERENCIAS**
    De acá se forman las info adicionales, de algunos transacciones
13. **BCAMOVIL.MICHI_TRANSACTIONS**
    Todas la transferencias se registran aca
14.  **BCAMOVIL.MICHI_SESSIONS_N**
15. **BCAMOVIL.BW_AGE_CONTACTOS**
    Almacena los contactos 
16. **IT.GE_CALENDARIOS**
    Guarda el calendario
17. **GE_CTA_CLIENTES**
	Trae todos los datos de una cuenta, personas asociadas a esta cuenta
18. **LC_CON_CAMBIOS**
	Trae los contratos de cambios