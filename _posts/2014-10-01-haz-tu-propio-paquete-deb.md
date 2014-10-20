---
layout: post
title: Haz tu propio paquete deb
---
Alguna vez te preguntaste como se crean los paquetes **deb**?

Mmm... no? Entonces el post no es para vos.

Como ejemplo, vamos a crear un paquete básico para instalar [chromedriver](https://code.google.com/p/selenium/wiki/ChromeDriver)

Siendo **$DEST** una carpeta temporal y **$SOURCE** la que contiene los archivos de la aplicación

## Estructura de directorios de destino
  Hay que crear los directorios que necesitamos para instalar nuestro paquete

  ``` bash
  mkdir --parents $TEMP/opt/chromedriver $DEST/usr/local/bin
  ```

## Copiar los archivos de nuestra aplicación

 ``` bash
 cp -r $SOURCE/* $DEST/opt/chromedriver
 ```

## Enlaces simbólicos executables para los binarios

 ``` bash
 ln -sf $DEST/opt/chromedriver/chromedriver \
        $DEST/usr/local/bin/chromedriver
 chmod +x $DEST/usr/local/bin/chromedriver
 ```

## Metadatos del paquete

El directorio **DEBIAN** es el que contendrá archivos de metadatos y scripts necesarios para la instalación
 `mkdir $DEST/DEBIAN`

 Crear archivo **control** que contiene los metadatos del paquete

```
Package: chromedriver
Version: 2.10
Architecture: amd64
Maintainer: Gonzalo Matheu <gonzalommj@gmail.com>
Installed-Size: 5656
Pre-Depends: multiarch-support
Depends: google-chrome-stable (>= 33) | google-chrome-beta (>= 33) | google-chrome-unstable (>= 33)
Provides: chromedriver
Section:
Priority: optional
Multi-Arch: same
Homepage: https://code.google.com/p/selenium/wiki/ChromeDriver
Description: ChromeDriver is a standalone server which implements WebDriver's wire protocol.
```

Ademas existen otros archivos que se pueden incluir:

  * postinst
  * preinst
  * prerm
  * postrm
  * confiles
  * md5sums

## Crear paquete

``` bash
dpkg-deb -b $DEST chromedriver-2.10-amd64.deb
```

  Pimba! El paquete listo

## Probar que todo funciona

Preferentemente en una máquina virtual o contenedor...

``` bash
dpkg -i chromedriver-2.10-amd64.deb
```

  Luego de eso, si todo salió com esperado, deberíamos poder ejecutar `chromedriver` correctamente


### Extras

#### Descargar y extrar algún paquete existente

**hello** es un paquete que sólo tiene la intención de mostrar la estructura de los mismos.

`apt-get download hello` para bajar el paquete
`dpkg-deb -x hello.deb $DEST` para extraer los archivos
`dpkg-deb -e hello.deb $DEST/DEBIAN` para extraer metadatos y scripts de instalación.

### Subir paquete a algún repositorio (por ej (Bintray)[])

Habiendo creado el paquete y la versión en Bintray...


### Referencias


