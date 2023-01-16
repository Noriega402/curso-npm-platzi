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

### Desinstalar versiones de node con nvm
Hay casos en donde ya no utilizaremos algunas versiones de Node, resulta que tambien podemos eliminar las versiones de Node que tenemos instaladas en nuestra máquina:
<pre>nvm uninstall numeroDeVersion</pre>
```bash
nvm uninstall 18.6.0
```

## Primeros pasos con _npm_
creamos una carpeta en nuestros archivos:
__NOTA:__ Para fines de practica puedes crearla en tu escritorio
- Creamos la carpeta
    ```bash
    mkdir aprendiendo-npm
    ```
- Nos movemos a la carpeta creada
    ```bash
    cd aprendiendo-npm
    ```
- Creamos sub carpeta de primeros pasos
    ```bash
    mkdir primeros-pasos
    ```
- Nos movemos a la carpeta creada
    ```bash
    cd primeros-pasos
    ```
- Inicializamos npm
    ```bash
    npm init
    ```
Nos mostrara un recuadro para llenar alguna informacion para dar a conocer de que trata el proyecto que estaremos creando, por defecto el nombre del paquete toma el nombre de la carpeta
<div align="center">
    <img src="./imgs/npm-init.PNG">
</div>
Tendremos que rellenar varias opciones pero para fines educativos solo veremos algunas:
<div>
    <img src="./imgs/npm-finish.PNG">
</div>

- __Description:__ podemos dar una breve descripcion de que tratara el proyecto que estaremos realizando
- __entry point:__ el punto de entrada que tomara (archivo principal)
- __git repository:__ para agregar un repositorio al que guardara los cambios
- __keywords:__ palabras clave por ejemplo: Javascript, Node, HTMl, CSS, etc.
- __author:__ una de las más importantes, para dar a conocer quien creo el proyecto.
- __license:__ que tipo de licencia se utliza en el proyecto (normalmente se utiliza MIT).

En caso no querramos estar haciendo eso de rellenar siempre todos esos campos, podemos utilizar otra instruccion para saltarnos esos pasos:
```bash
npm init -y
```

## Instalación de Dependencias
### Dependencias de desarrollo VS Dependencias de producción
- __Dependencias de Desarrollo:__ son aquellos paquetes que necesitamos en un proyecto mientras estamos desarrollándolo, pero una vez tenemos el código generado del proyecto, no vuelven a hacer falta. Los paquetes instalados con el flag _--save-dev_ o _-D_ se instalan en esta modalidad, guardándolos en la sección devDependences del fichero _package.json_.

- __Dependencias de Producción:__ son aquellos paquetes que necesitamos tener en la web final generada, como librerías Javascript necesarias para su funcionamiento o paquetes similares. Los paquetes instalados con el flag _--save-prod_, _-P_ o directamente sin ningún flag se instalan en esta modalidad, guardándolos en la sección dependences del fichero _package.json_.

Dentro de la terminal procedemos con la instalacion de algnas dependencias:
```bash
npm install moment
```
__NOTA:__ esta es la opcion por defecto, ya que se instala como dependencias de producción, que seria lo mismo que colocar:
<pre>npm install -P moment</pre>

La siguiente dependencia sera para __dependencias de desarrollo__:
```bash
npm install eslint -D
```

### 4 maneras de instalar dependencias de producción
1. ```bash
    npm install react
    ```
1. ```bash
    npm install react -S
    ```
1. ```bash
    npm install react --save
    ```
1. ```bash
    npm install react --save-prod
    ```
En nuestro _package.json_ podemos ver al final del documento las dependencias que se instalaron:
<div align="center">
    <img src="./imgs/dependencias.PNG">
</div>

Podemos ver que hay dependencias de producción __(dependencies)__ y tambien las dependencias de desarrollo __(devDependencies)__.
## Instalando dependencias globales
Habra casos en los que tenemos que instalar paquetees globales en nuestro ordenador y se puede hacer de la siguiente manera:
```bash
npm install -g cowsay
```

#### Cowsay
Podremos tener compañia en nuestra terminal cuando instalamos cowsay!!!
```bash
cowsay hola a todos
```
<div>
    <img src="./imgs/cowsay-hello.PNG">
</div>

- Otros comandos con cowsay:
    <pre>cowsay -t Estoy cansado...</pre>
    <pre>cowsay -b Estoy aburrido...</pre>
    <pre>cowsay -d Estoy muriendo</pre>
    <pre>cowsay -f dragon "AHORA SERAS TESTIGO DE MI PODER"</pre>
   <pre>cowsay -f dragon-and-cow "SOY EL REY DE LA TERMINAL VAQUITA"</pre>
    <pre>cowsay -f tux soy el pinguino de Linux</pre>
    <pre>cowsay -f stegosaurus "Estas en la era de los Dinos"</pre>
    <pre>cowsay -f ghostbusters "En tu computadora hay fantasmas..."</pre>
    <pre>cowsay -f elephant "Soy el animal mas grande sobre la tierra"</pre>
    <pre>cowsay -f vader YO SOY TU PADRE</pre>