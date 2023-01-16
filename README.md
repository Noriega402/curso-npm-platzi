# curso-npm-platzi
Aprendiendo npm y dependencias de js

### Glosario:
- __npm:__ Node Package Manager
- __CLI:__ Command Line Client

Cuando se instala Node se tiene acceso a _npm_ entonces no hay de que preocuparse

### Diferencias entre paquetes y modulos
- Un modulo es un archivo que puede ser importado desde otro archivo.
- Un paquete es una carpeta que puede tener varios módulos y son los que se agregan al archivo _package.json_

### Instalación de Node
[Descargar](https://nodejs.org/es/) la última versión para tener todas las funcionalidades que nos brinda.
### Verificar la version de node y npm por medio de la consola

- #### Para node
    ```bash
    node -v
    ```
- En caso no te funcione puedes ejecutar el siguiente comando:
    ```bash
    node --version
    ```
- #### Para npm
    ```bash
    npm -v
    ```
- En caso no te funcione puedes utilzar el siguiente comando:
    ```bash
    npm --version
    ```
## ¿Podemos tener mas de una version de Node en nuestra computadora?
La respuesta es si, podemos tener varias versiones de node, en caso requieras de esta opción, tendras que desinstalar node de tu computadora:
1. Seleccionas la opcion de buscar programas en tu computadora (la lupa), escribes __"_Panel de control_"__.
1. Te diriges a la opcion de programas y caracteristicas.
1. Buscar el programa que diga Node.
1. Click derecho encima de ella.
1. Click izquierdo en desinstalar.
1. Sigues los pasos que te indica el programa.
<br><br>

Luego de realizar esos pasos, puedes dar click [aquí](https://github.com/coreybutler/nvm-windows/releases) para descargar _nvm_ buscas el siguiente link:
<br>
<br>
<div align="center">
    <img src="./imgs/nvm.PNG" height="50px">
</div>
Al terminar tu descarga instalas el programa como una aplcacion normal.
Terminas de instalar y te diriges a tu terminal.

__Nota:__ te recomiendo que sea la terminal de git o instalas desde microsft store una terminal WSL.
<br><br>
<div align="center">
    <img src="https://gramfile.com/wp-content/uploads/2019/06/Git-BASH-Icon-45x45.png" height="80px">
</div>
Nos aseguramos de que nvm se instalo conrrectamente con el siguiente comando en la terminal:

```bash
nvm
```
Nos mostrara una lista de comandos para poder utilizar similar a la siguiente imagen:
<div align="center">
    <img src="./imgs/console-nvm.PNG">
</div>

Ahora viene la parte interesante en donde tendremos que instalar alguna version de Node, para eso primero veremos las versiones disponibles mediante la consola con el isguiente comando:
```bash
nvm list available
```

Nos deplegara una tabla con la informacion de las versiones disponibles para trabajar con Node JS
<div align="center">
    <img src="./imgs/list-available.PNG">
</div>

#### Instalacion de ultima version con nvm
Ya que vimos las versiones disponibles mediante la consola podemos ejecutar la siguiente instruccion por medio de la consola:
```bash
nvm install 18.10.0
```
El comando anterior indica que nvm realizara la instalacion de la version 18.10.0, nos dimos cuenta que elegimos una versión en específico, pero...

¿Qué pasa cuando queremos instalar la ultima versión?, sencillo... Utilizamos el siguiente comando:
```bash
nvm install latest
```
¿Y si queremos la version LTS? es similar al anterior:
```bash
nvm install lts
```
### Listar las versiones de Node
Si tenemos instalado _nvm_ podemos ver las diferenctes versiones de Node que tenemos instaladas:
```bash
nvm ls
```
```bash
nvm list
```
### Cambiar de versiones con nvm
Supongamos que instalamos 4 versiones de Node y la que esta en uso es la ultima version, pero por cuestiones de compatibilidad u otras cosas tenemos que cambiar a unas versiones anteriores, de que manera la hacemos?
<pre>nvm use numeroDeVersion</pre>
- Ejemplo
    ```bash
    nvm use 18.6.0
    ```
¿Como saber que cambiamos de versión?
```bash
nvm list
```
nos mostrar un asterisco en la version que el sistema esta utilizando como en la imagen que se muestra a continuación:
<div align="center">
    <img src="./imgs/use-version.PNG">
</div>