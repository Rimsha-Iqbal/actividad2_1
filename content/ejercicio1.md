# Despliegue del tema "Minima" de Jekyll en GitHub Pages
# Ejercicio 1  

# Índice

- [Despliegue del tema "Minima" de Jekyll en GitHub Pages](#despliegue-del-tema-minima-de-jekyll-en-github-pages)
- [Ejercicio 1](#ejercicio-1)
- [Índice](#índice)
  - [Requisitos Previos](#requisitos-previos)
  - [Preparación Máquina virtual en Debian 12](#preparación-máquina-virtual-en-debian-12)
  - [Conexión remota desde Windows a Debian 12:](#conexión-remota-desde-windows-a-debian-12)
  - [Creación de Repositorio en GITHUB](#creación-de-repositorio-en-github)
  - [Creación de Repositorio local.](#creación-de-repositorio-local)
  - [Instalación de Ruby](#instalación-de-ruby)
    - [Requerimientos:](#requerimientos)
    - [Instalación:](#instalación)
  - [Instalación de Bundler y Jekyll](#instalación-de-bundler-y-jekyll)
  - [Creación de un sitio/proyecto de Jekyll](#creación-de-un-sitioproyecto-de-jekyll)
    - [Paso 1: Creación de un nuevo repositorio (Remoto) y configurar la fuente del sitio de Jekyll](#paso-1-creación-de-un-nuevo-repositorio-remoto-y-configurar-la-fuente-del-sitio-de-jekyll)
    - [Paso 2: Creación del repositorio local](#paso-2-creación-del-repositorio-local)
    - [Paso 3: Creación del sitio en Jekyll](#paso-3-creación-del-sitio-en-jekyll)
    - [Instalación del tema "Minima"](#instalación-del-tema-minima)
    - [Personalización de \_config.yml](#personalización-de-_configyml)
    - [Modificación en la página de inicio (index.md)](#modificación-en-la-página-de-inicio-indexmd)
    - [Creación de una Nueva Página: helloworld.md](#creación-de-una-nueva-página-helloworldmd)
    - [Personalización de la Página about.md](#personalización-de-la-página-aboutmd)
  - [Publicación de sitio en servidor local](#publicación-de-sitio-en-servidor-local)
  - [publicación de sitio en GitHub](#publicación-de-sitio-en-github)



## Requisitos Previos  

- Ruby (versión 2.5.0 o superior)  
- Bundler (para manejar las dependencias de Ruby)  
- Jekyll (generador de sitios estáticos)  
- Git (para gestionar el repositorio)  

## Preparación Máquina virtual en Debian 12 
Configuramos el fichero**/etc/network/interfaces** y ponemos una IP estática y párametros de TCP/IP.  
En Mi caso mi máquina virtual tiene IP como **"10.0.22.202"**

## Conexión remota desde Windows a Debian 12:
Para este paso usamos un editor de código **"Visual Studio Code"**. Usamos servicio de ssh para conectar a máquina virtual de debian usando nombre del usuario y contraseña.  

## Creación de Repositorio en GITHUB
- Accedemos a nuestra cuenta de GitHub y creamos un nuevo repositorio **mi_blog**.  
- No iniciamos el repositorio con un archivo README, ya que lo subiremos directamente desde la terminal.
- En **.gitignore** seleccionamos Jekyll
- El archivo **.gitignore**  es un archivo de configuración qque es muy útil para evitar que archivos generados automáticamente o archivos que no son necesarios para el repositorio GitHub.

- En el caso de Jekyll, hay ciertos archivos y directorios que no necesitas subir a repositorio porque se generan de manera automática. Por ejemplo **./jekyll-cache/**.

## Creación de Repositorio local.

- Iniciamos maquina de debian y conectamos con Visual Studio usando ssh.
- Creamos un irectorio "repositorio".
- Dentro de directorio repositorio creamos un directorio **myblog**.
- con git init covertimos este en un repositorio local.
- Con **git remote add origin https://Rimsha-Iqbal:token@github.com/Rimsha-Iqbal/blog.git** que vincula repositorio local a repositorio remoto en GITHUB.

## Instalación de Ruby
### Requerimientos:
- Ruby version 2.5.0 o superior -> ruby -v  
- RubyGems (gestor de paquetes) -> gem -v  
- GCC y Make-> gcc -v, g++ -v, make -v
### Instalación:
- Antes de Instalar ejcutamos comandos de "apt update" y "apt upgrade".
- Con siguiten comandos instalamos paquete de ruby y gems.   
**echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc  
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc  
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc  
source ~/.bashrc**
- Con el comando ruby -v confirmamos la instalación y versión.  
  
  ![alt text](img/img1.png)

- Con gem -v, g++ -v confirmamos instalación ye gems.  
- 
  ![alt text](img/img2.png)  

  ![alt text](img/img3.png)

## Instalación de Bundler y Jekyll

- Usamos el comandos **"gem install jekyll bundler"** para instalar bundler de jekyll en debian 12.  
  
  ![alt text](img/img4.png)

  ![alt text](img/img5.png)

## Creación de un sitio/proyecto de Jekyll

### Paso 1: Creación de un nuevo repositorio (Remoto) y configurar la fuente del sitio de Jekyll
- Creamos un nuevo repositorio VACÍO
### Paso 2: Creación del repositorio local
- Con el comando **cd myblog** cambiamos directorio.  
- Creamos rama gh-pages
- git checkout gh-pages cambios rama de main a gh-pages

### Paso 3: Creación del sitio en Jekyll

- Con **"jekyll new"** creamos un sitio en el directorio myblog.   
- Este comando generará una estructura básica de directorios y archivos para el sitio, incluyendo una página de inicio y el archivo de configuración **_config.yml**.

### Instalación del tema "Minima"
- Para instalar el tema "Minima",debemos modificar el archivo de configuración **_config.yml**
- Abri el archivo **_config.yml**.
- Cambiamos la línea de theme a minima.

###  Personalización de _config.yml
- En el archivo **_config.yml**, realizamos las siguientes modificaciones para personalizar el sitio:  

- En la linea de **title** pongo titulo **"Blog de Rimsha"** .
- En la linea de **email** pongo mi dirección de correo.
- En la linea de **baseurl** añadimos ruta de directorio myblog **/myblog**.
- En la linea de **url** pongo url de mi github pages.
- En la linea de **twitter_username** y **github_username** pongo nombre de usuario de Twitter y GitHub.

###  Modificación en la página de inicio (index.md)

- Abrimos el archivo index.md y agregamos el contenido  debajo del encabezado.
- He añadido una lista de numeración.

### Creación de una Nueva Página: helloworld.md

- En el directorio myblog, creamos una nueva página llamada helloworld.md..
- En el cabezado añadimos **layout** (page),**title** ("Hello world") y **primalink** (/hello-world/).
- Por ultimo luego añadimos contenido de la pagina.

### Personalización de la Página about.md
- Mismo que anterior el cabezados añadimo **layout** (page),**title** ("Acerca de mi") y **primalink** (/about/).
- Añadimos contenido.

## Publicación de sitio en servidor local

Con el comando "budle exec jekyll serve --host 10.0.22.X" desplegamos nuestro sitio en servidor local.

![alt text](img/imagenlocalservr.png)

## publicación de sitio en GitHub
- Con "git remote add origin" syncronamos nuestro repositorio con repositorio local.
- Con "git add ." subimos todos modificaciones a repositorio local.
- Con git commoit -m" añadimos mensaje a este.
- Con "git push origin gh-pages" subimos todos los cambios al repositorio remoto en github.  
  
  
  ![alt text](img/github.png)
