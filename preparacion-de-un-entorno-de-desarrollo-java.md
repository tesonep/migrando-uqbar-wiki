| | \_\_TOC\_\_ |
|---------------|

A continuación explicaremos cómo instalar un entorno de desarrollo para Java, en su versión 8, el cual incluirá los siguientes elementos:

-   El JDK8: Las bibliotecas estándar y herramientras de construcción para la tecnología Java y derivadas
-   Eclipse: Un entorno integrado de desarrollo (IDE), que nos servirá para codificar, compilar, probar, refactorizar nuestro software.
-   Maven: Una herramienta de (entre otras cosas) manejo de dependencias

Nota: además de lo descripto acá, será necesario contar con una herramienta de control de versiones, como por ejemplo git o svn.

Instalación del JDK (Java Development Kit)
------------------------------------------

El JDK8 contiene un compilador y una máquina virtual (el runtime) que traduce a código de máquina el código intermedio que genera el compilador (.java → COMPILADOR (javac) → .class → VM (java) → ejecutable final).

Para instalarlo, debemos descargarlo de <http://www.oracle.com/technetwork/java/javase/downloads/index.html>. Luego, procederemos a descomprimirlo.

Los pasos siguientes dependen del sistema operativo.

**En Windows**, el proceso esta guiado mayormente por el instalador.

**En Mac** pueden utilizar homebrew.

Una opción para **Debian, Ubuntu, Mint o sistemas** con apt-get es hacer:

-   `sudo` `add-apt-repository` `ppa:webupd8team/java`
-   `sudo` `apt-get` `update`
-   `sudo` `apt-get` `install` `oracle-java8-installer`

Y definirlo como el default haciendo

-   `sudo` `update-java-alternatives` `-s` `java-8-oracle`

Sino en **otros sistemas Linux** debemos realizar lo siguiente:

-   Pararse en el directorio donde se lo descomprimió.
-   `sudo` `mv` `jdk1.8.0` `/usr/lib/jvm/jdk1.8.0/` (si descargaste la versión JDK 1.8.0\_40 el nombre del directorio será jdk1.8.0\_40, y así sucesivamente)
-   `sudo` `update-alternatives` `--install` `/usr/bin/java` `java` `/usr/lib/jvm/jdk1.8.0/jre/bin/java` `500`
-   `sudo` `update-alternatives` `--config` `java`. Elegir la opcion del jdk8

\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_\_

Con esto, el JDK ya deberia estar instalado. Probarlo desde una terminal tipeando lo siguiente:

`java` `-version`

(deberia mostrar 1.8.0)

Eclipse
-------

La instalación del eclipse es muy sencilla: hay que bajar la versión el Eclipse IDE for Java Developers que corresponda a su sistema operativo desde <http://www.eclipse.org/downloads/> y descomprimirlo en su disco rígido. Posiblemente deseen crear un acceso directo para apuntar al ejecutable.

Recuerden después configurarlo adecuadamente: [Configuraciones generales para cualquier Eclipse](configuraciones-generales-para-cualquier-eclipse.md)

Problema de Eclipse con Ubuntu 13.10
------------------------------------

Si instalaste Eclipse en Ubuntu 13.10 y utilizás el escritorio Unity, es posible que tengas problemas a la hora de visualizar los menús (file, edit, view, etc). Para arreglar este problema, hay que editar a mano unos archivos tal como se indica en esta [solución](http://askubuntu.com/questions/364310/eclipse-kepler-runs-weird).

Hay que buscar los archivos eclipse.desktop en las rutas /usr/share/applications y ~/.local/share/applications/ y luego editarlos con cualquier editor de texto (nano, gedit, etc). Para esto, debemos primero pararnos en cada ruta, utilizando el comando cd.

-   `cd` `/usr/share/applications`

Luego, debemos utilizar un editor de texto para cambiar la línea que queremos cambiar.

-   `sudo` `nano` `eclipse.desktop`

o bien

-   `sudo` `gedit` `eclipse.desktop`

o bien sudo "el\_editor\_de\_texto\_que\_me\_guste" eclipse.desktop y reemplazamos la línea que comienza con Exec por:

-   `Exec=env` `UBUNTU_MENUPROXY=` `/ruta/al/eclipse/eclipse`

Luego repetimos los pasos anteriores para el eclipse.desktop que se encuentra en la ruta `~/.local/share/applications/`.

Reiniciamos el eclipse y los menús deberían poder visualizarse correctamente.

Maven
-----

Instalen Maven según la [Guía de Instalación de Maven](guia-de-instalacion-de-maven.md)

Y cuando creemos un proyecto, recordá configurar el compilador para que emplee Java 8. Ver <http://maven.apache.org/plugins/maven-compiler-plugin/examples/set-compiler-source-and-target.html>

Por ejemplo, agregá la siguiente información dentro de tu pom:

<build>
`   `<plugins>
`     `<plugin>
`       `<groupId>`org.apache.maven.plugins`</groupId>
`       `<artifactId>`maven-compiler-plugin`</artifactId>
`       `<version>`3.1`</version>
`       `<configuration>
`         `

    1.8

`         `<target>`1.8`</target>
`       `</configuration>
`     `</plugin>
`   `</plugins>
` `</build>

Links útiles
------------

-   [Amigandonos con el entorno de desarrollo](amigandonos-con-el-entorno-de-desarrollo.md)

