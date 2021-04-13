# Proyecto #2 - Manual de usuario
Este manual tiene como fin ayudar a todos aquellos usuarios finales que necesitan ingresar a la VPN de la empresa desde dispositivos con 
sistema operativo Windows, cualquier distribución de linux y desde dispositivos de tipo Android.

# Contenido:
1. [Solicitud de archivo para ingresar a la VPN](#item1)
2. [Configurar VPN en dispositivo Windows](#item2)
3. [Configurar VPN en dispositivo Linux](#item3)
4. [Configurar VPN en dispositivo Android](#item4)

<a name="item1"></a>
# Solicitud de archivo para ingresar a la VPN
Para solicitar el ingreso a la VPN empresarial deberá comunicarse con el administrador de sistema o con el equipo de Tecnologias de la informacón
para que suministre sus datos personales y el tipo de dispositivos que va a utilizar para ingresar.

<a name="item2"></a>
# Configurar VPN en dispositivo Windows
Luego de obtener el archivo por el equipo de TI o el administrador de sistemas deberá seguir los siguientes pasos.

## Paso #1: Descargue el archivo con extensión .ovpn
Este archivo deberá colocarlo en una carpeta segura que ningun otro usuario tenga acceso a la misma, recuerde que debe tener cuidado con 
este archivo ya que facilita la conexión hacia la red empresarial.

## Paso #2: Descargue la aplicación de OpenVPN
A continuación se suministra el link para descargar la aplicación oficial para conectarse a la red, es importante que utilice este link
y no descargue otra aplicación de terceros por cuestiones de seguridad.
```
https://openvpn.net/downloads/openvpn-connect-v3-windows.msi
```
Luego de descargar el archivo lo ejecuta.

Aceptar la instalación del archivo
![OVInstall](./imgs/OVWin1.PNG)

Lo anterior abrirá un wizard, presionamos el boton de next
![OVInstall](./imgs/OVWin2.PNG)

Aceptamos terminos y condiciones
![OVInstall](./imgs/OVWin3.PNG)

Finalmente presionamos el boton de Install
![OVInstall](./imgs/OVWin4.PNG)

## Paso #3: Ejecutar la aplicación 
Buscamos OpenVPN GUI y lo ejecutamos
![OVInstall](./imgs/OVWin5.PNG)

## Paso #4: Importar el archivo OVPN
Se abrirá está aplicación en la barra de tareas, el icono es el de la computadora con el candado.
![OVInstall](./imgs/OVWin6.PNG)

Le damos click derecho al icono y seleccionamos la opcion de import file...
![OVInstall](./imgs/OVWin7.PNG)

Esto abrirá un exporador de archivos, acá buscamos el archivo que anteriormente descargamos
![OVInstall](./imgs/OVWin8.PNG)

Luego de cargar nuestro archivo, presionamos de nuevo con click derecho la aplicación en la barra de tareas y le damos en Connect

<a name="item3"></a>
# Configurar VPN en dispositivo Linux

## Paso #1: Descargue el archivo con extensión .ovpn
Este archivo deberá colocarlo en una carpeta segura que ningun otro usuario tenga acceso a la misma, recuerde que debe tener cuidado con 
este archivo ya que facilita la conexión hacia la red empresarial.

## Paso #2: Descargue el OpenVPN desde la consola
Abrimos la terminal y ejecutamos los siguientes comandos
```bash
apt-get update
apt-get install openvpn
```

## Paso #3: Importar el archivo de configuración
Ejecute el proximo comando para configurar su dispositivo para ingresar a la red empresarial
```bash
cd "Ruta del archivo (/home/usuario/documentos)"
openvpn --config "nombre del archivo"
```

## Paso #4: Comprobación de conectividad
Ejecutamos el siguiente comando para saber si la conexión está establecida
```bash
ping -c 4 10.0.4.7
```

<a name="item4"></a>
# Configurar VPN en dispositivo Android

## Paso #1: Descargue el archivo con extensión .ovpn
 ## Paso #1: Descargue el archivo con extensión .ovpn
Este archivo deberá colocarlo en una carpeta segura que ningun otro usuario tenga acceso a la misma, recuerde que debe tener cuidado con 
este archivo ya que facilita la conexión hacia la red empresarial.

## Paso #2: Descargar la aplicación desde la PlayStore
Instalar la siguiente aplicación de Open VPN
![OVWhats1](./imgs/OVWhats1.PNG)

## Paso #3: Importar el archivo descargado
Primero aceptamos los terminos y condiciones
![OVWhats1](./imgs/OVWhats2.PNG)

Segundo presionamos la casilla superior de file, buscamos el archiv OVPN y presionamos IMPORT
![OVWhats1](./imgs/OVWhats3.PNG)

Luego presionamos el boton ADD en la parte superior derecha
![OVWhats1](./imgs/OVWhats4.PNG)

Por ultimo nuestra configuración quedará guardada de la siguiente manera, acá puede activar la conexión o desconectarse de la red 
![OVWhats1](./imgs/OVWhats5.PNG)