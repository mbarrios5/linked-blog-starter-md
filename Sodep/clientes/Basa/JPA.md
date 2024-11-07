[[Banco Basa]]

- **`ddl-auto: none`**: Esto desactiva la generación automática de tablas y otras estructuras de base de datos al inicio de la aplicación. `ddl-auto` controla cómo Hibernate maneja la creación y actualización del esquema, y al estar en `none`, no hará ninguna modificación.
    
- **`generate-ddl: false`**: Esta opción también indica que JPA no generará automáticamente el DDL (lenguaje de definición de datos) para crear o actualizar tablas.
    
- **`hbm2ddl.auto: none`**: Es otra configuración redundante con `ddl-auto`, que indica a Hibernate que no debe realizar cambios en la base de datos.
    
- **`default_schema: be`**: Esta propiedad establece el esquema predeterminado (`be`) en la base de datos PostgreSQL. Sin embargo, como las tablas no se crearán automáticamente, solo se utilizará este esquema para ejecutar consultas en tablas que ya existan en la base de datos.