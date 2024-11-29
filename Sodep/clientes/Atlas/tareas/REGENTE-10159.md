[[Banco Atlas]]

Existes dos APIS uno favorito y otro contacto

No es optimo porque hace select en contacto y  para favoritos utiliza vista materializada



**Cambiar**
Se desea cambiar a una sola API que ya esta en desarrollo

**Nueva API**
La nueva api ya impacta directamente en la nueva tabla, alta baja listar se puede hacer todo eso en la nueva API. Esto para no llamar a los otros APIS y facilita tanto al front web y mobile.

Se quiere **deprecar** Agenda Contactos del frontend

**TABLAS**
1. La vieja es esta BCAMOVIL.AGENDA_CONTACTO
2. La nueva es BW_AGE_CONTACTOS
**Tener en cuenta**
1. En transferencias antes de confirmar ya se esta llamando al **POST contacto** eso debe llamarse solo cuando se concrete la transferencia
2. Tambien guardar como contanto al finalizar 

**Lugares donde cambiar**
1. En Buscar Contacto 

**Tarea**
1. Quitar frecuentes de transferencias y solo dejar contacto con la nueva API [media].Corrobe que no cambia al cambiar la cuenta
2. En Buscar Contacto  cambiar y llamar a la nueva API
3. Favoritos almacenar en el REDUX y luego no llamar mas, excepto cuando se haga otra transferencia, para eso tambien se debe verificar que el contacto no este en el REDUX[Esto evaluar]
4. El alias también guardar como contacto al terminar la transferencia
5. Guardar contacto al finalizar la transferencia ahora mismo se esta guardando en AccountContactForm que es un paso ANTES a la confirmacion [MEDIA]
6. En transafernecia el BOTON agenda mirar
7. Chimi button


**ALIAS**
1. TIeene su propio form , verifiacar como funciona
**Respuesta API Vieja**

```
{
    "totalRegistros": 3,
    "paginaActual": 1,
    "totalPaginas": 1,
    "contactos": [
        {
            "contactoID": 1341345,
            "estado": "ACTIVO",
            "contacto": "BLAS EDUARDO VILLALBA MARTINEZ",
            "tipoDocContacto": "1",
            "tipoDocDescContacto": null,
            "nroDocContacto": "888123574",
            "bancoDesc": "Atlas",
            "bancoCod": "ATLAS",
            "monedaCod": "6900",
            "nroCuenta": "678144",
            "email": null,
            "celular": null,
            "atajo": "N",
            "notifEmail": null,
            "notifSMS": null,
            "destino": "others",
            "alias": null,
            "bancoDescripcionCorta": null
        },
        {
            "contactoID": 1341346,
            "estado": "ACTIVO",
            "contacto": "JULIO DARIO ARGUELLO RIVEROS",
            "tipoDocContacto": "1",
            "tipoDocDescContacto": null,
            "nroDocContacto": "888454643",
            "bancoDesc": "Atlas",
            "bancoCod": "ATLAS",
            "monedaCod": "1",
            "nroCuenta": "1233533",
            "email": null,
            "celular": null,
            "atajo": "N",
            "notifEmail": null,
            "notifSMS": null,
            "destino": "others",
            "alias": null,
            "bancoDescripcionCorta": null
        },
        {
            "contactoID": 1341344,
            "estado": "ACTIVO",
            "contacto": "ROBERTO ARIEL GONZALEZ FLEITAS",
            "tipoDocContacto": "1",
            "tipoDocDescContacto": null,
            "nroDocContacto": "888351807",
            "bancoDesc": "Atlas",
            "bancoCod": "ATLAS",
            "monedaCod": "6900",
            "nroCuenta": "676422",
            "email": null,
            "celular": null,
            "atajo": "N",
            "notifEmail": null,
            "notifSMS": null,
            "destino": "others",
            "alias": null,
            "bancoDescripcionCorta": null
        }
    ]
}
```

API VIEJA FAVOTIRO
```
{
    "totalRegistros": 1,
    "paginaActual": 1,
    "totalPaginas": 1,
    "favoritos": [
        {
            "favoritoID": 0,
            "estado": "ACTIVO",
            "count": 0,
            "alias": "Joaquin Ariel Valdivieso Lugo",
            "fechaInsercion": "2024-11-15T09:50:15-03:00",
            "fechaActualizacion": "2024-11-15T09:50:15-03:00",
            "fechaUltimaTransaccion": null,
            "shortcut": false,
            "frequency": true,
            "tipo": "FRECUENTE",
            "banco": "Atlas",
            "operaciones": null,
            "tokenFavorito": null,
            "operacionesFavoritas": {
                "transactionID": 34306673,
                "externalId": "0034306673",
                "tipo": "TRANSFERENCIA_PROPIA",
                "estado": "CONCRETADA",
                "monto": 0,
                "montoLista": 100,
                "moneda": {
                    "nombre": "Guaraníes",
                    "codigo": 6900,
                    "iso": "PYG",
                    "simbolo": "Gs",
                    "abreviatura": "GS"
                },
                "debito": "874683",
                "credito": "1460861",
                "infoAdicional": {
                    "frecuencia": null,
                    "fecha_inicio": null,
                    "cantidad_transferencias": 0,
                    "es_programada": "N",
                    "favorito": 0,
                    "concepto_transferencia": "Transf.Bca.Web a: 1460861",
                    "monto_cotizacion": 7780,
                    "canal_origen": 4,
                    "origen": {
                        "nroCuenta": "874683",
                        "denominacion": "PERSONA NRO. 478367",
                        "modulo": 3,
                        "modalidad": {
                            "codigo": 31,
                            "descripcion": "AHORROS A LA VISTA",
                            "descripcionCorta": "AH"
                        },
                        "sistema": "x",
                        "fecApertura": null,
                        "fecActivacion": null,
                        "saldo": 1537229,
                        "moneda": {
                            "nombre": "Guaraníes",
                            "codigo": 6900,
                            "iso": "PYG",
                            "simbolo": "Gs",
                            "abreviatura": "GS"
                        },
                        "estado": "N",
                        "tipoFacultad": "P",
                        "depositoConfirmar": 0,
                        "saldoDisponible": 1537229,
                        "saldoPromedio": null,
                        "saldoAtlasAdelanto": null,
                        "saldoBloqueado": null,
                        "tipoBloqueo": null,
                        "saldoProtegido": null,
                        "lineaAtlasAdelanto": null,
                        "tipTarDebito": 6,
                        "nroTarDebito": null,
                        "tipoEmision": null,
                        "valorTasa": null,
                        "saldoMinimo": null,
                        "nroCuentaCombinada": null,
                        "denomCuentaCombinada": null,
                        "extractoEmail": {
                            "email": null,
                            "habilitar": null,
                            "frecuencia": null
                        },
                        "enteAsociado": null,
                        "beneficio": null,
                        "estadoTarjeta": {
                            "codigo": 0,
                            "descripcion": null
                        },
                        "esEmpresarial": false,
                        "causaBloqueo": null,
                        "tipoGarantias": [],
                        "nroCtaAliasBancard": 0,
                        "tipoAlias": null,
                        "alias": null,
                        "infoAdicional": {
                            "total_credito": null,
                            "monto_disponible_cuenta": null,
                            "limite_mensual": null,
                            "limite_transferencias": null
                        }
                    },
                    "codMichiProgram": null,
                    "aprobaciones_pendientes": 1,
                    "monto_credito": 0.01,
                    "fecha_fin": null,
                    "nro_contrato_cambio": null,
                    "motivo_transferencia": {
                        "codigo": "0",
                        "descripcion": "",
                        "descripcionCorta": ""
                    },
                    "destino": {
                        "nroCuenta": "1460861",
                        "denominacion": "PERSONA NRO. 478367",
                        "modulo": 3,
                        "modalidad": {
                            "codigo": 31,
                            "descripcion": "AHORROS A LA VISTA",
                            "descripcionCorta": "AH"
                        },
                        "sistema": "1",
                        "fecApertura": "2023-10-19T03:00:00.000+0000",
                        "fecActivacion": null,
                        "saldo": 9.15,
                        "moneda": {
                            "nombre": "Dólares",
                            "codigo": 1,
                            "iso": "USD",
                            "simbolo": "$",
                            "abreviatura": "USD"
                        },
                        "estado": "N",
                        "tipoFacultad": "P",
                        "depositoConfirmar": 0,
                        "saldoDisponible": 9.15,
                        "saldoPromedio": 8.24,
                        "saldoAtlasAdelanto": null,
                        "saldoBloqueado": 0,
                        "tipoBloqueo": null,
                        "saldoProtegido": 0,
                        "lineaAtlasAdelanto": null,
                        "tipTarDebito": 0,
                        "nroTarDebito": null,
                        "tipoEmision": null,
                        "valorTasa": 1,
                        "saldoMinimo": 0,
                        "nroCuentaCombinada": null,
                        "denomCuentaCombinada": null,
                        "extractoEmail": {
                            "email": null,
                            "habilitar": null,
                            "frecuencia": null
                        },
                        "enteAsociado": null,
                        "beneficio": null,
                        "estadoTarjeta": {
                            "codigo": 0,
                            "descripcion": null
                        },
                        "esEmpresarial": false,
                        "causaBloqueo": null,
                        "tipoGarantias": [],
                        "nroCtaAliasBancard": 0,
                        "tipoAlias": null,
                        "alias": null,
                        "infoAdicional": {
                            "total_credito": 1,
                            "monto_disponible_cuenta": 0,
                            "limite_mensual": 0,
                            "limite_transferencias": 15000
                        }
                    },
                    "suspender": null
                }
            }
        }
    ],
    "operaciones": {
        "TRANSFERENCIA_PROPIA": "TRANSFERENCIA PROPIA"
    }
}
```


API NUEVA
```
{
	"totalRegistros": null,
	"paginaActual": null,
	"totalPaginas": null,
	"contactos": [
		{
			"codAgenda": 4,
			"tipDocumento": 1,
			"nroDocumento": "5032037",
			"nomContacto": "Brian N. Duré Aquino",
			"nomAlias": "Karpi",
			"codSwift": "FAMIPYPA",
			"codMoneda": "GS",
			"nroCuenta": "23233232",
			"dirCorreo": "durebrian01@gmail.com",
			"nroCelular": null,
			"tipTransferencia": "SIPAP",
			"bcpTipAlias": null,
			"bcpAlias": null,
			"activo": "S",
			"destacado": "N"
		},
		{
			"codAgenda": 5,
			"tipDocumento": 1,
			"nroDocumento": "888295645",
			"nomContacto": "IGNACIO ALDERETE MARTINEZ",
			"nomAlias": "Karpi",
			"codSwift": "FAMIPYPA",
			"codMoneda": "GS",
			"nroCuenta": "650078",
			"dirCorreo": "durebrian01@gmail.com",
			"nroCelular": null,
			"tipTransferencia": "SIPAP",
			"bcpTipAlias": null,
			"bcpAlias": null,
			"activo": "S",
			"destacado": "N"
		}
	]
}
```

POST API VIEJA 
```
{
    "estado": "ACTIVO",
    "bancoCod": "FAMIPYPA",
    "contacto": "juan",
    "destino": "sipap",
    "monedaCod": "6900",
    "nroCuenta": "1234567",
    "nroDocContacto": "1231233",
    "tipoDocContacto": "1",
    "bancoDesc": "BANCO FAMILIAR SAECA"
}
```


POST Contacto viejo desde pefil
```
{
  estado: "ACTIVO",
  bancoCod: "AMAMPYPA",
  celular: undefined,
  email: "marce@gmail.com",
  contacto: "Barrios",
  destino: "sipap",
  monedaCod: "6900",
  nroCuenta: "987654",
  nroDocContacto: "5436554",
  tipoDocContacto: "1",
  bancoDesc: "BANCO BASA SA",
  
}

```



Ver porque recibir Null cuando cargue 


Probar con empresas

Todas las APIS DE FAVORITO se debe eliminar?

verificar el componente CARD CLIENT
VERIFICAR -> POST en EVA que esta almacenando igual auqnue ya exista el contacto

**Componentes**
NewTransfer -> primera pantalla de transferencia donde muestra los contactos
NewTransferForm -> ultimo formulario de envio
SaveAccountEva -> guarda el nuevo contacto desde chimi con los datos 
AliasFormEva -> guarda contacto desde el ALIs


**Cambios realizados:**
- MainAddContact: ELIMINAR FRECUETNES, NUEVO DELETE, NUEVO GET
- AddContactForm: NUEVO POST,NUEVO GET,ElIMINAR FRECUENTES
- NewTransfer: ElIMINAR FRECUENTES,NUEVO GET,MAPPER, NUEVO FAVORITO, NUEVO BUSCADO, NUEVA VISTA   . Obs:quietar comentarios
- AliasFormEva: Nuevo POST -> se activa despues de clickear alias
- SaveAccountEva: NUEVO POST 
- AliasForm -> desde perfil



```
{
    "favoritoID": 0,
    "estado": "ACTIVO",
    "count": 0,
    "alias": "Joaquin Ariel Valdivieso Lugo",
    "fechaInsercion": "2024-11-21T08:00:50-03:00",
    "fechaActualizacion": "2024-11-21T08:00:50-03:00",
    "fechaUltimaTransaccion": null,
    "shortcut": false,
    "frequency": true,
    "tipo": "FRECUENTE",
    "banco": "Atlas",
    "operaciones": null,
    "tokenFavorito": null,
    "operacionesFavoritas": {
        "transactionID": 34306741,
        "externalId": "0034306741",
        "tipo": "TRANSFERENCIA_PROPIA",
        "estado": "CONCRETADA",
        "monto": 0,
        "montoLista": 1000,
        "moneda": {
            "nombre": "Guaraníes",
            "codigo": 6900,
            "iso": "PYG",
            "simbolo": "Gs",
            "abreviatura": "GS"
        },
        "debito": "874683",
        "credito": "1460861",
        "infoAdicional": {
            "frecuencia": null,
            "fecha_inicio": null,
            "cantidad_transferencias": 0,
            "es_programada": "N",
            "favorito": 0,
            "concepto_transferencia": "Transf.Bca.Web a: 1460861",
            "monto_cotizacion": 7780,
            "canal_origen": 4,
            "origen": {
                "nroCuenta": "874683",
                "denominacion": "PERSONA NRO. 478367",
                "modulo": 3,
                "modalidad": {
                    "codigo": 31,
                    "descripcion": "AHORROS A LA VISTA",
                    "descripcionCorta": "AH"
                },
                "sistema": "x",
                "fecApertura": null,
                "fecActivacion": null,
                "saldo": 1517081,
                "moneda": {
                    "nombre": "Guaraníes",
                    "codigo": 6900,
                    "iso": "PYG",
                    "simbolo": "Gs",
                    "abreviatura": "GS"
                },
                "estado": "N",
                "tipoFacultad": "P",
                "depositoConfirmar": 0,
                "saldoDisponible": 1517081,
                "saldoPromedio": null,
                "saldoAtlasAdelanto": null,
                "saldoBloqueado": null,
                "tipoBloqueo": null,
                "saldoProtegido": null,
                "lineaAtlasAdelanto": null,
                "tipTarDebito": 6,
                "nroTarDebito": null,
                "tipoEmision": null,
                "valorTasa": null,
                "saldoMinimo": null,
                "nroCuentaCombinada": null,
                "denomCuentaCombinada": null,
                "extractoEmail": {
                    "email": null,
                    "habilitar": null,
                    "frecuencia": null
                },
                "enteAsociado": null,
                "beneficio": null,
                "estadoTarjeta": {
                    "codigo": 0,
                    "descripcion": null
                },
                "esEmpresarial": false,
                "causaBloqueo": null,
                "tipoGarantias": [],
                "nroCtaAliasBancard": 0,
                "tipoAlias": null,
                "alias": null,
                "infoAdicional": {
                    "total_credito": null,
                    "monto_disponible_cuenta": null,
                    "limite_mensual": null,
                    "limite_transferencias": null
                }
            },
            "codMichiProgram": null,
            "aprobaciones_pendientes": 1,
            "monto_credito": 0.13,
            "fecha_fin": null,
            "nro_contrato_cambio": null,
            "motivo_transferencia": {
                "codigo": "0",
                "descripcion": "",
                "descripcionCorta": ""
            },
            "destino": {
                "nroCuenta": "1460861",
                "denominacion": "PERSONA NRO. 478367",
                "modulo": 3,
                "modalidad": {
                    "codigo": 31,
                    "descripcion": "AHORROS A LA VISTA",
                    "descripcionCorta": "AH"
                },
                "sistema": "1",
                "fecApertura": "2023-10-19T03:00:00.000+0000",
                "fecActivacion": null,
                "saldo": 10.45,
                "moneda": {
                    "nombre": "Dólares",
                    "codigo": 1,
                    "iso": "USD",
                    "simbolo": "$",
                    "abreviatura": "USD"
                },
                "estado": "N",
                "tipoFacultad": "P",
                "depositoConfirmar": 0,
                "saldoDisponible": 10.45,
                "saldoPromedio": 8.24,
                "saldoAtlasAdelanto": null,
                "saldoBloqueado": 0,
                "tipoBloqueo": null,
                "saldoProtegido": 0,
                "lineaAtlasAdelanto": null,
                "tipTarDebito": 0,
                "nroTarDebito": null,
                "tipoEmision": null,
                "valorTasa": 1,
                "saldoMinimo": 0,
                "nroCuentaCombinada": null,
                "denomCuentaCombinada": null,
                "extractoEmail": {
                    "email": null,
                    "habilitar": null,
                    "frecuencia": null
                },
                "enteAsociado": null,
                "beneficio": null,
                "estadoTarjeta": {
                    "codigo": 0,
                    "descripcion": null
                },
                "esEmpresarial": false,
                "causaBloqueo": null,
                "tipoGarantias": [],
                "nroCtaAliasBancard": 0,
                "tipoAlias": null,
                "alias": null,
                "infoAdicional": {
                    "total_credito": 2.3,
                    "monto_disponible_cuenta": 0,
                    "limite_mensual": 0,
                    "limite_transferencias": 15000
                }
            },
            "suspender": null
        }
    }
}
```