https://nextjs.org/
[[Curos de programacion]]

Es un framework de React a diferencia de react que es solo una libreria que maneja el estado, next seria como angualr y vue

Tener en cuentra que React solo trabaja con el cliente ( a partir de la version 18 ya tiene tambien) a difernecia de Next . Renderiza tanto del lado del servidor como el lado del cliente

Tiene su next ui para componente de diseño es como el angular material


**Layout.tsx**
	Hace referncia al  **Page.tsx** , al crear la el page.tsx ya next te crea el layaout.tsx
	
**Page.tsx**	
	Archivo es sumamente importante porque es como el index.html , es un componente funcional
	
**Renderizado lado servidor**

Se ejecuta dentro del servidor, tareas o peticiones que solo se hacia con APis es decir ya se puede hacer consulta a archivos y a base de datos

**Use client**
	Esto sirve para que ese componente next haga que funcione como cliente 
**Rutas**	
	Todas las rutas que va a tener la aplicacion debe crearse dentro de la carpeta app.
	 La ruta principal siempre sera page.tsx .

**Anidacion de rutas** 
	Se debe solamente agregar dentro de la carpeta creada /app/articulo1 /app/articulo2

**Rutas dinamicas**	
	Al agregar [productId] se le esta pasando el parametro, tiene que ser el mismo nombre a la del parametro, la funcion luego le recibe como argumento
**404 Pagina**	
	Para configurar una pagina 404 es solo agregar en la raiz un  archivo **not-found.tsx**
**Ocultar carpetas**	
    Para ocultar una carpeta solo se necesita agregar _  guion bajo esto necesario cuando hay que utilizar carpetas auxiliares
  **Rutas agrupadas**  
	  Rutas que hacen referencia a una misma funcionalidad por ejemplo login se agregar entre paréntesis la carpeta que agrupa para no mostrar en la URL por ejemplo (cuenta
	  )