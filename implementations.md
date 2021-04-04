# Proyecto #2 - Creación de servicio VPN, Servidor web(VHost) y servidor SQL
Debido a la pandemia de Covid-19, la empresa “Los Patitos S.A” los ha contratado a usted ysu compañero,
para implementar una solución de VPN para habilitar a sus colaboradores la opción   de   teletrabajo.
Para   demostrar   su   solución   deberá   considerar   al   menos   los   seisdispositivos que se muestran
en el siguiente diagrama.La empresa “Noire S.A.” requiere desplegar toda su infraestructura en la nube de Azure,
para lo cual usted deberá aprovisionar y configurar una servidor de OpenVPN, que será elúnico que tendrá
un puerto expuesto a Internet (el puerto 1194, en TCP/UDP), en otras dossub-redes de Azure, 
usted deberá desplegar una servidor web con Apache2 y un servidor deMySQL.

Los trabajadores podrán acceder a dichos recursos desde clientes en Windows, GNU/Linux y Android,
el nivel de acceso dependerá del rol del trabajador.

El personal de tecnologías podráacceder tanto al servidor web, como al servidor de base de datos,
mientras que el resto elpersonal solo podrá acceder al servidor de Apache2, para consumir los sitios
que estánpublicados en dicho servido

## Parte #1: Instalación de paquetes y servicios.
Todas las siguientes librerias son necesarias para la utilizar satisfactoriamente el servicio de VPN
```bash
apt-get install openvpn openssl ca-certificates iptables
mkdir -p /etc/openvpn/server/easy-rsa/
wget  https://github.com/OpenVPN/easy-rsa/releases/download/v3.0.8/EasyRSA-3.0.8.tgz
tar xz EasyRSA-3.0.8.tgz /etc/openvpn/server/easy-rsa/

```

## Parte #2: Creación de pki y configuración de CA (Autoridad certificadora)
Primero nos drigimos a la carpeta del servidor e ingresamos a easy-rsa
```bash
cd /etc/openvpn/server/easy-rsa/
./easyrsa init-pki
./easyrsa --batch build-ca nopass
cp pki/ca.crt /etc/openvpn/server
cp pki/private/ca.key /etc/openvpn/server
```
Con estos comandos anteriores se creará el certificado y la llave de la CA, luego lo moveremos en la 
raiz del servidor.

## Parte #3 Creación de certificado y llave del servidor: 
Luego de crear la CA crearemos el certificado y la llave para el servidor
```bash
./easyrsa build-server-full server nopass
cp pki/issued/server.crt /etc/openvpn/server
cp pki/private/server.key /etc/openvpn/server
```

