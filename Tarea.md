# Instalación de Maven en el SO

## 1.Instalar Apache Maven

 Actualizamos el sistema y Maven ingresando los siguientes comandos:

```
 sudo apt update
```
```
 sudo apt install maven
```

<img src="Imágenes/Imagen1.png" alt="Imagen 1">

 Para verificar la instalación, ejecutamos mvn -version:
```
 mvn -version
```

<img src="Imágenes/Imagen2.png" alt="Imagen 1">

 Eso es todo. Maven ahora está instalado en su sistema y puede comenzar a usarlo.

## 2.Instalar una versión concreta de Apache Maven


 Descargue Apache Maven en el directorio /tmp:

```
wget https://www.apache.org/dist/maven/maven-3/3.8.2/binaries/apache-maven-3.8.2-bin.tar.gz -P /tmp
```

<img src="Imágenes/Imagen3.png" alt="Imagen 1">

 Una vez que se complete la descarga, extraemos el archivo en el directorio /opt
```
sudo tar xf /tmp/apache-maven-*.tar.gz -C /opt
```
<img src="Imágenes/Imagen4.png" alt="Imagen 1">

 Para tener más control sobre las versiones y actualizaciones de Maven, ejecutamos lo siguiente al directorio de instalación de Maven:

```
sudo ln -s /opt/apache-maven-3.8.2 /opt/maven
```

<img src="Imágenes/Imagen5.png" alt="Imagen 1">

## 3.Establecer variables de entorno
 A continuación, necesitaremos establecer las variables de entorno. Para hacer esto, abrimos su editor de texto y creamos un nuevo archivo llamado mavenenv.sh en el directorio /etc/profile.d/
```
sudo nano /etc/profile.d/maven.sh
```
<img src="Imágenes/Imagen5.1.png" alt="Imagen 1">

Se nos abrirá el editor de texto Nano que tiene el siguiente aspecto:

<img src="Imágenes/Imagen6.png" alt="Imagen 1">

En el que pegamos el siguiente código:

```
 export M2_HOME=/opt/maven
 export MAVEN_HOME=/opt/maven
 export PATH=${M2_HOME}/bin:${PATH}
```

<img src="Imágenes/Imagen7.png" alt="Imagen 1">

 Guardamos el archivo presionando Ctrl+O y luego pulsando Enter, es decir, lo guardamos en el directorio que nos pone por defecto:
 
 <img src="Imágenes/Imagen8.png" alt="Imagen 1">
 
 Salimos del editor pulsando Ctrl+x 

 Hacemos que el script sea ejecutable con chmod:

```
 sudo chmod +x /etc/profile.d/maven.sh
```
<img src="Imágenes/Imagen9.png" alt="Imagen 1">

 Finalmente, cargamos las variables de entorno usando el comando de source
```
 source /etc/profile.d/maven.sh
```

<img src="Imágenes/Imagen10.png" alt="Imagen 1">

## 4.Verificar la instalación

Para verificar que Maven está instalado, usamos el mvn -version que imprimirá la versión de Maven:

```
mvn -version
```

<img src="Imágenes/Imagen11.png" alt="Imagen 1">
