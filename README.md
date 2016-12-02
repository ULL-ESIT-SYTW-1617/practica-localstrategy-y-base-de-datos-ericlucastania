#Práctica: LocalStrategy y base de datos

## Descripción

El servidor proveído por el plugin (sea iaaso heroku) deberá autenticar al lector del libro usando LocalStrategy 
y una base de datos en la que se guarda la información acerca de los usuarios.
En este caso la base de datos utilizada es SQLITE,que es una biblioteca escrita en leguaje C que implementa 
un Sistema de gestión de bases de datos transaccionales SQL auto-contenido, sin servidor y sin configuración. El código de 
SQLite es de dominio público y libre para cualquier uso, ya sea comercial o privado.

  
### Pasos a seguir

* Comprobar que tienes cuenta en el iaas,en caso de no tener cuenta no podrás llevar a cabo la práctica
  * [Enlace al login del iaas](https://iaas.ull.es/ovirt-engine/sso/login.html)




## Pasos a ejecutar 

**1. Instala nuestro paquete de forma global**

```npm install -g gitbook-start-elt```


**2. Ejecuta el binario para el render del template**
	
Tienes la opción de crear el repositorio o la opción de no crearlo:
	
	
**Crear repositorio**
* Si quieres que te cree un repositorio en Github tienes que poner la opción --repo
	
   ```gitbook-start --dir Carpeta --repo```

Cuando ejecutes el paso anterior si no es la primera vez que lo haces te pedirá el usuario y 
		contraseña de github.Si introduces los datos correctamente te pedirá que introduzcas el nombre que quieres ponerle al repo,
		Ahora se desplegará el libro en github:
				
**Ejemplo de uso:**
				
				
![](https://4.bp.blogspot.com/-tZyZ4yGuI9A/WCxV2cB2ktI/AAAAAAAAAAg/I2tzZnB7FL4Nld6OQRs2NYG-SRwa9kIuwCLcB/s1600/repo.PNG)
				
Una vez que se te creado el repo ya puedes trabajar en él,ya no tendrás que poner más el 
			usuario y contraseña gracias a que se te generó un token para evitar que cada vez que quieras 
				crear un repo te pida tus credenciales.
				El token que se genera se guarda en el ./gitbook-start/config.json un lugar seguro para que no pueda acceder nadie
				que no seas tu.	
				
La siguiente función es la que se utiliza para guardar el token que se obtiene
```javascript
    auth().then(function (resolve, reject) {
					fs.mkdirSync(directorioHome + '/.gitbook-start');
					var pac = directorioHome + '/.gitbook-start/';
					fs.writeFile(pac + 'config.json', JSON.stringify(json), function (err) {
						if (err) throw err;
						else resolviendo(console.log("guardando el json correctamente.."));

					});
				});
```




**3. Entra en la carpeta**

 ```cd Carpeta```


## PLUGINS

**1. Instala el plugin forma global**

```npm install -g gitbook-start-plugin-iaas-ull-es-ericlucastania```


**2. Cambia los datos del package.json que tiene el directorio que has creado en nuestro caso de llama Carpeta**


### Instrucciones de uso

Tenga en cuenta que para que el plugin funcione correctamente debe cambiar algunas cosas en el package.json


![](https://4.bp.blogspot.com/-Jjhh_IM9FAw/WA9EbkzsEoI/AAAAAAAAAoc/84cO_lVXgCYD6ekx1YzSV6LEjsCitH0AACLcB/s1600/iass.png)
* Deberá poner la IP de su maquina del iaas.

![](https://4.bp.blogspot.com/-qb-f3r0EpJ0/WA9IiJ-XjjI/AAAAAAAAAoo/aDSCiupjFeIOQ3WumKTtT5FIKK9FtxU1wCLcB/s1600/ip.png)

* Tenga en cuenta que si el usuario de su máquina no es "usuario" deberá también cambiar esto en el fichero package.json

![](https://4.bp.blogspot.com/-Ls3DTGAHQ7E/WA9IjVnGOqI/AAAAAAAAAow/BANS15EoXqYuVwIChWcSqZvqlkcLxtMRQCLcB/s1600/usuario.png)



**3. Ejecuta el plugin que desees, asegúrate de estar dentro de la carpeta**


```gitbook-start -d iaas``` !! También puedes usar la opción --deploy


**4. Ejecuta el gulp creado**

```gulp deploy-iaas```

Si se realiza este paso correctamente se clonara el repo creado y se instalarán las dependencias
automaticamente en el IAAS

## Entrar en el IAAS

El siguiente paso que deberás realizar es acceder al tu cuenta del iaas y si has seguido los pasos 
hechos anteriormente,te deberá aparecer una carpeta llamada Gitbook,en ella tienes la clonación del repo
Por último ejecuta 
```bash 
	node app*
```
Ahora simplemente pon ti IP y el puerto en el navegador y podrás acceder al login del Gitbook

![](https://1.bp.blogspot.com/-lLq-_MEkYsM/WEBhC2Ar5AI/AAAAAAAAAqA/ImB9cNyxNycQU5ToUgsVst5d_2bPwI7-QCLcB/s1600/Captura%2Bde%2Bpantalla%2Bde%2B2016-12-01%2B17%253A41%253A41.png)

Si no te has registrado anteriormente hazlo clicando en la parte que aparece justo encima del botón 
login

![](https://3.bp.blogspot.com/-JmjU0UCdEBA/WEBjJCGzzyI/AAAAAAAAAqM/SScW0jFBE6I-sBMLBpignzKteeNwjtWGACLcB/s1600/Captura%2Bde%2Bpantalla%2Bde%2B2016-12-01%2B17%253A49%253A30.png)

Y en caso de estar registrado pon tus datos y si son correctos te llevará al Home donde tendrás la opción de ver tu profile o acceder al gitbook.

![](https://3.bp.blogspot.com/-4Iuks1R4bhM/WEBkIgVxYsI/AAAAAAAAAqU/ZIyHRgBYN88ErbjAAqQFYVPVBLIUhzpvQCLcB/s1600/Captura%2Bde%2Bpantalla%2Bde%2B2016-12-01%2B17%253A55%253A29.png)


Si quieres cambiar la contraseña accede desde el login a Cambiar contraseñadd

![](https://1.bp.blogspot.com/-ohMGl5Zljso/WEBjbDRTqKI/AAAAAAAAAqQ/6n57bpjVoCAdwH6PrKdfPE1dFTl6c7NqgCLcB/s1600/Captura%2Bde%2Bpantalla%2Bde%2B2016-12-01%2B17%253A52%253A32.png)


#### Explicación

Cunado se ejecuta el gitbook-start -d iaas se te lanzará el initialize del módulo,
el initialize crea una tarea en el gulp para realizar el deploy. Además de guardarte el paquete
elegido en el package.json.

## Opciones

    gitbook-start [OPTIONS]
        --dir nombre_del_directorio a crear gitbook-start --dir miDirectorio
        -a autor del libro a crear node gitbook-star -a AutorDelLibro
        -e email del autor del libro node gitbook-star -e eric.ramos.suarez@gmail.com
        -r repositorio github contra el que se va a trabajar -r nameRepo
        -v muestra la version del paquete gitbook-start -v
        -h muestra ayuda sobre las opciones disponibles
        --repo opción que te permite crear un repositorio en GitHub





## Enlaces interesantes

* [Repositorio Práctica](https://github.com/ULL-ESIT-SYTW-1617/gitbook-start-plugin-iaas-ull-es-ericlucastania) 
* [Descripción de la práctica]()
* [PLUGIN IAAS](https://github.com/ULL-ESIT-SYTW-1617/gitbook-start-iaas-ull-es-ericlucastania)
* [NPM PLUGIN IAAS](https://www.npmjs.com/package/gitbook-start-plugin-iaas-ull-es-ericlucastania)

## Componentes del grupo de trabajo
* [Eric Ramos](https://github.com/alu0100786330)
* [Lucas Ruiz](https://github.com/alu0100785265)
* [Tania González](https://github.com/tania77)


