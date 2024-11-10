# Proyecto DNSA y DNSB en BIND9

Este proyecto tiene como objetivo la implementación de un servidor DNS utilizando BIND9 para gestionar tanto zonas directas como inversas, además de configurar subdominios relacionados con diferentes áreas de una institución educativa. El proyecto incluye los siguientes aspectos:

- Configuración de **zona directa** para el dominio principal y subdominios como **informática**, **aulas** y **departamentos**.
- Implementación de **zona inversa** para la resolución inversa de direcciones IP a nombres de dominio.
- Configuración de **servidores DNS primario (DNSA) y secundario (DNSB)** para garantizar la alta disponibilidad y redundancia del servicio DNS.

## Estructura del Proyecto

### 1. Definición de zonas
Aqui despues de instalar el servicio me he puesto a definir las zonas necesarias.

- **informática**: Subdominio relacionado con los sistemas de tecnología de la información.
- **aulas**: Subdominio destinado a las aulas y recursos tecnológicos asociados.
- **departamentos**: Subdominio que organiza los diferentes departamentos académicos o administrativos de la institución.
- **Inversa**: En la inversa he puesto los pointers PTR a todo lo demas.
### 2. Named.local.conf
Este ha sido el segundo paso que he hecho, definirlas en este archivo con el type. Tanto en el principal como en el secundario.

### 3. Provision
Por ultimo he provisionado el Vagrant file para que solo con un "Vagrant up" funciones todo.