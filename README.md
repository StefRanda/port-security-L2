# 🔐 Implementación de Port Security en Switch Cisco

## Descripción
Este proyecto forma parte de una práctica de laboratorio enfocada en la **seguridad de capa 2**, utilizando **Port Security** para proteger el acceso a la red desde los puertos del switch.

## Objetivos
- Limitar el número de dispositivos que pueden conectarse a cada puerto.
- Evitar accesos no autorizados mediante control de direcciones MAC.
- Aplicar buenas prácticas de seguridad deshabilitando puertos no utilizados.

## Configuración básica
```bash
enable
configure terminal
hostname Switch1
interface vlan 1
ip address 192.168.1.2 255.255.255.0
no shutdown
exit
interface range f0/1 – 2
switchport port-security
switchport port-security maximum 1
switchport port-security mac-address sticky
switchport port-security violation restrict
interface range f0/3 - 24 , g0/1 - 2
shutdown
copy running-config startup-config
