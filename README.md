Proyecto NodeJS

En esta práctica aprenderemos a trabajar de manera básica con proyectos de NodeJS, una plataforma de desarrollo de aplicaciones que utiliza el lenguaje Javascript.
Referencias

    Mocha
    Should
    Introducción a Node.js
    Introducción a npm
    Testing in JS
    Debugging in VS Code: User interface
    Debugging in VS Code: Start debugging
    Debugging in VS Code: Launch configurations
    Debugging in VS Code: Debug actions

Instalación de dependencias

Antes de poder testear el programa, es necesario instalar su dependencias: librerías de código que el programa necesita para poder funcionar o para poder ser testeado. En proyectos de NodeJS, el comando que hay que ejecutar para instalar dichas dependencias es:

npm install

npm es un gestor de paquetes: se encarga de conectarse con el repositorio de librerías de Node, https://www.npmjs.com/, descargar las librerías definidas en el archivo de configuración del proyecto, package.json, e instalarlas en una carpeta especial, en este caso la carpeta node_modules.

Observa que el fichero .gitignore incluye una línea para ignorar esa carpeta a la hora de añadir cambios al repositorio. Ello se debe a que las dependencias no se deben almacenar en el control de versiones, ya que pueden ser fácilmente descargadas e instaladas de nuevo por el gestor de paquetes leyendo el archivo de configuración del proyecto.

En nuestro caso, este proyecto solo incluye dependencias para poder realizar los tests. Comprueba el fichero package.json y observa que hay dos dependencias de desarrollo definidas en la sección devDependencies: mocha y should. Dichas dependencias son librerías utilizas para realizar tests.
Ejecución de tests desde la consola

El fichero de configuración de proyecto, package.json, define comandos para utilizar en el proyecto. Observa que hay comandos para realizar los tests: test, test1 y test2. Dichos comandos utilizarán el programa mocha para ejecutarse. Puedes ejecutar los tests de la siguiente manera:

npm run test # Se puede utilizar 'npm test' como atajo
npm run test1
npm run test2

Dichos comandos arrojarán un error si antes no instalas las dependencias con npm install. Si ejecutas npm install, npm descargará el programa necesario para el test y lo guardará en la carpeta node_modules del proyecto. Entonces sí que podrás lanzar dichos comandos.

El test definido en test1.js utiliza el módulo assert integrado en Node.

El test definido en test2.js utiliza la librería should.

Se pueden añadir más ficheros de test en la carpeta test. Los nuevos archivos que se añadan a dicha carpeta se ejecutarán al llamar a npm run test.
Ejecución de tests y depuración en el IDE

Una configuración de lanzamiento, o launch configuration, es un fichero de configuración en el que se especifica qué programa se debe lanzar para ejecutar y depurar el código. Este repositorio incluye una configuración de lanzamiento en el fichero .vscode/launch.json.

A partir de esa configuración de lanzamiento, el IDE puede saber qué tiene que ejecutar para lanzar el programa. Además, al lanzar el programa desde el propio IDE, es posible realizar una depuración del código mediante puntos de ruptura. De esta manera, se puede marcar una determinada línea en el código fuente del programa, lanzar el programa, e interrumpir su ejecución en dicho punto para inspeccionar el estado actual o buscar posibles errores. En el apartado de Referencias tienes varios enlaces a la documentación oficial de VSCode en los que se explica cómo realizar estas acciones.

Observa que el fichero de configuración de lanzamiento define como programa para ejecutar mocha, igual que la configuración de package.json. De esta manera podrás lanzar los mismos tests que lanzabas en la consola a través de npm run test desde el propio IDE. La diferencia está en que, si utilizas la configuración de lanzamiento y las utilidades de depuración del IDE, podrás utilizar entre otras cosas los puntos de ruptura.
Desarrollo guiado por test

La metodología de Desarrollo Guiado por Pruebas consiste en los siguientes pasos:

    Elegir una funcionalidad que se desea añadir
    Escribir un test que compruebe el funcionamiento del código que implementará esa funcionalidad. Dicho test deberá tener en cuenta todos los posibles casos de uso
    Comprobar que el test falla. Lógico, el código ni siquiera existe...
    Crear el código para pasar el test
    Comprobar que se pasan todos los tests
    Refactorizar el código (eliminar duplicidades, etc.)
    Volver a comprobar que se pasan todos los tests

Tarea

    Clona este proyecto en el entorno de CodeSpaces.
    Inspecciona el código. Presta especial atención a los ficheros package.json y .vscode/launch.json.
    Lanza los tests desde la consola. Comprueba que fallan por no haber instalado las dependencias. Haz una captura de pantalla.
    Instala las dependencias. Haz una captura de pantalla de la ejecución del comando.
    Ejecuta los tests en un terminal. Haz una captura de pantalla de la ejecución del comando. Comprueba que los tests se pasan.
    Crea un punto de ruptura en el fichero operations.js para interrumpir la ejecución de una de las funciones.
    Ejecuta los tests desde el IDE a través de las herramientas de depuración. Comprueba que la ejecución se detiene en el punto de ruptura. Haz una captura de pantalla.
    Añade dos nuevos tests en dos archivos. Dichos tests deben comprobar el correcto funcionamiento de las funciones multiplicacion y division. Adjunta dichos tests al repositorio.
    Modifica el fichero package.json para incluir los nuevos tests en dos nuevos comandos, test3 y test4.
    Ejecuta los tests nuevos y comprueba que fallan. Haz una captura de pantalla.
    Modifica el código del fichero operations.js. Añade y exporta dos nuevas funciones, multiplicacion y division. Crea la lógica necesaria para que dichas funciones realicen las correspondientes operaciones matemáticas y devuelvan el resultado.
    Ejecuta una vez más los tests nuevos y comprueba que esta vez funcionan. Haz una captura de pantalla.
