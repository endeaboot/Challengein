### Documentación

Este widget (la barra o challengein) funciona con firebase para el backend, y jquery.
Usa el login que provee firebase. 
Tiene una página de administrador para crear un nueva cuenta, configurar misiones, puntos, etc.

Las imágenes que se usan en el administrador (misiones, medallas, etc) se suben a firebase storage.
Las imágenes que se usan en la barra están en base64.

Al principio del archivo `challengein.js` está la carga de firebase, hay un script de vimeo, youtube, y moment, estos son para ver cuándo se cumplan ciertas misiones. 
*moment* no se está usando porque las misiones con sesiones quedaron standby.

Luego viene la carga de la barra que verifica si hay un usuario de la barra, y que no sea un usuario administrador.
Sino hay usuario muestra la UI por defecto con la pantalla de login (que tb crea usuario)

Después viene una función que carga los datos del usuario en la UI.
Hay muchas funciones que var cargando las misiones, logros, niveles, etc (con las condiciones de cada uno para que se vayan cumpliendo, es decir... que si una misión en el backend dice que tiene que hacer click en un botón con el id #btnmision1, entonces la misión es tipo 1 y se cumple al hacer click en ése elemento.. y así con lo demás, logros, niveles)

La comunidad muestra a los usuarios que están asociados al proyecto.
Las posiciones es lo mismo, pero están ordenados.

más abajo está la función con la configuración inicial. 
Hay 2 estilos: cuándo el usuario está con sesión y la otra cuándo no hay sesión.
cuando hay una sesión toma la configuración del tema creado en el administrador.

más abajo está la configuración de los popups que muestran mensajes de la app.

Al final están las funciones de los slider, los tabs, etc.

### administrador

Para ingresar con el proyecto de prueba, hay que entrar a: `http://localhost:8080/admin/`
con el user: `roberto@axionla.cl` y la pass `axionla`.

en la pestaña de inicio muestra el código que debe ser pegado antes de cerrar el `body` y debajo de jquery.

En la pestaña niveles, se puden crear y borrar niveles.

En misiones y logros se pueden crear/modificar/borrar elementos

En usuarios se pueden borrar.

En configuración general hay configuración del tema de la barra (colores)

En configuración del popup se puede elegir posición, tipo, tiempo del popup que mostrará el proyecto.


### crear proyectos
En la url de administrador `/admin` (estando loggeado o no) 
en la consola hay que llamar a la función `crearcuenta(email, clave, proyecto)` por ejemplo
>crearcuenta('juanito@axionla.cl','juanito123','clgjuanito2017')
Entonces para ingresar al admin se ingresa con ése correo y la clave. el proyecto es el id con el cual se llamará cuando se integre el script en el sitioweb.