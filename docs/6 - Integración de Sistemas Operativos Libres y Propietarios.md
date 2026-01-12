# 6️⃣ Integración de Sistemas Operativos Libres y Propietarios

En un entorno empresarial, la coexistencia de sistemas operativos libres (como Linux) y propietarios (como Windows) es una realidad común. La integración de estos sistemas permite aprovechar las ventajas de ambos mundos, optimizando recursos y mejorando la interoperabilidad en redes heterogéneas. Este tema se centra en las estrategias, herramientas y configuraciones necesarias para que estos sistemas trabajen de forma conjunta y eficiente.

## Conceptos básicos de integración

La integración de sistemas operativos libres y propietarios se basa en la capacidad de ambos para comunicarse mediante protocolos estándar.

Windows, con su interfaz gráfica intuitiva y amplio soporte de software, es ideal para estaciones de trabajo y entornos empresariales.

Linux, por su parte, destaca en servidores por su estabilidad, flexibilidad y coste reducido.

!!!note "La coexistencia de ambos sistemas permite...""
    - Reducción de costes mediante el uso de software libre.
    - Aprovechamiento de aplicaciones específicas de Windows.
    - Mayor flexibilidad en la gestión de recursos de red.

## Sistemas operativos libres y propietarios

**Sistemas operativos libres**

!!!tip "Software cuyo código fuente está disponible para su estudio, modificación y distribución"

- **Ejemplos:** Linux (Debian, Ubuntu, CentOS), FreeBSD.  
        
        Ventajas 👇

  - Coste reducido (la mayoría son gratuitos).  
  - Alta flexibilidad y personalización.  
  - Comunidad activa de soporte.  
  - Excelente estabilidad y rendimiento en servidores.  

        Desventajas 💢

  - Curva de aprendizaje más pronunciada.  
  - Menor soporte para aplicaciones específicas de empresas que usan sistemas propietarios.  

**Sistemas operativos propietarios**  

!!!danger "Software cuyo código fuente no está disponible al público y cuya modificación o distribución está restringida por licencias"

- **Ejemplos:** Windows (Server y Desktop), macOS.  

        Ventajas 👇

  - Interfaces gráficas intuitivas y fáciles de usar.  
  - Soporte técnico especializado.  
  - Amplia compatibilidad con software comercial.  

        Desventajas 💢

  - Coste elevado (licencias).  
  - Menor capacidad de personalización.  

### **Escenarios comunes de integración**  

En redes empresariales, la integración de sistemas libres y propietarios permite aprovechar las fortalezas de ambos tipos de sistemas. Algunos escenarios comunes incluyen:  

1. **Servidores Linux y estaciones de trabajo Windows:**  
   - Los servidores Linux pueden manejar servicios como web (Apache, Nginx), bases de datos (MySQL, PostgreSQL) y DNS, mientras que los usuarios trabajan en estaciones Windows.  

2. **Sistemas Linux en dominios Windows:**  
   - Integración de servidores Linux en un dominio de Active Directory para gestionar usuarios y políticas centralizadas.  

3. **Recursos compartidos entre Linux y Windows:**  
   - Uso de Samba para compartir carpetas desde Linux que sean accesibles desde Windows.  

4. **Autenticación unificada:**  
   - Uso de LDAP o Kerberos para gestionar usuarios y contraseñas de manera centralizada en una red mixta.  

### **Beneficios de la integración**  

La integración de sistemas operativos libres y propietarios ofrece numerosos beneficios.

- **Reducción de costes:** Utilizar Linux para servidores y Windows para estaciones de trabajo puede ser más económico que depender exclusivamente de sistemas propietarios.  
- **Flexibilidad:** Los sistemas libres permiten configuraciones avanzadas que pueden complementarse con la facilidad de uso de los sistemas propietarios.  
- **Interoperabilidad:** Los protocolos estándar como SMB, NFS y LDAP facilitan la comunicación entre sistemas.  
- **Escalabilidad:** Los sistemas Linux pueden manejar grandes cargas de trabajo, mientras que Windows puede gestionar estaciones de trabajo y aplicaciones empresariales.  

### **Retos de la integración**  

Aunque la integración tiene muchas ventajas, también presenta desafíos.

- **Compatibilidad:** Algunos formatos de archivo, aplicaciones o características no son totalmente compatibles entre sistemas.  
- **Configuración compleja:** La configuración inicial de servicios como Samba o LDAP puede ser complicada para usuarios sin experiencia.  
- **Soporte técnico:** Los sistemas libres suelen depender de la comunidad para soporte, lo que puede ser más lento que el soporte profesional de sistemas propietarios.  
- **Seguridad:** Es necesario garantizar que ambos sistemas estén configurados correctamente para evitar vulnerabilidades.  

### **Herramientas y tecnologías clave**  

Para lograr una integración efectiva, es importante conocer las herramientas y tecnologías disponibles

- **Samba:** Permite que los sistemas Linux actúen como servidores o clientes en redes Windows mediante el protocolo SMB/CIFS.  
- **LDAP:** Proporciona un directorio centralizado para la gestión de usuarios y grupos en redes heterogéneas.  
- **Kerberos:** Protocolo de autenticación que funciona tanto en Linux como en Windows, ideal para entornos mixtos.  
- **NFS:** Facilita la compartición de archivos entre sistemas Linux y Windows (con el cliente NFS en Windows).  
- **Virtualización:** Herramientas como VirtualBox, VMware y Proxmox permiten ejecutar sistemas operativos cruzados en un mismo hardware.  

---

### **Ejemplo práctico: Escenario básico de integración**  

**Objetivo:** Configurar un servidor Linux con Samba para compartir una carpeta accesible desde un equipo Windows.  

1. **Instalación de Samba en Linux:**  
   ```bash
   sudo apt update
   sudo apt install samba
   ```  

2. **Edición del archivo de configuración de Samba:**  
   - Ubicación: `/etc/samba/smb.conf`  
   - Añadir al final del archivo:  
     ```ini
     [RecursosCompartidos]
     path = /home/compartido
     read only = no
     browsable = yes
     ```  

3. **Crear la carpeta compartida y establecer permisos:**  
   ```bash
   mkdir /home/compartido
   chmod 777 /home/compartido
   ```  

4. **Reiniciar el servicio Samba:**  
   ```bash
   sudo systemctl restart smbd
   ```  

5. **Acceder al recurso desde Windows:**  
   - Abrir el explorador de archivos y escribir `\\IP_DEL_SERVIDOR\RecursosCompartidos`.  

---

## Servicios y servidores

A continuación veremos los distintos servicios que pueden configurarse como servidores para cualquier cliente que necesito de dicho servicio.

### 1. FTP (File Transfer Protocol)

FTP es un **protocolo de transferencia de archivos** que permite enviar y recibir ficheros entre un cliente y un servidor a través de la red.

Se utiliza tradicionalmente para:

* Subir archivos a un servidor web
* Compartir ficheros en redes internas
* Administración remota de archivos

❌ **FTP no cifra la información**: usuario, contraseña y datos viajan en texto plano.

#### Puertos

* **21/TCP** → canal de control
* **20/TCP** → canal de datos (modo activo)

#### Modos de funcionamiento

* **Activo**: el servidor inicia la conexión de datos (problemático con firewalls)
* **Pasivo**: el cliente inicia ambas conexiones (el más usado hoy en día)

#### Software habitual

* `vsftpd` (Very Secure FTP Daemon) → muy común en entornos educativos

#### Instalación (Debian/Ubuntu)

```bash
sudo apt update
sudo apt install vsftpd
```

#### Archivo de configuración

```bash
/etc/vsftpd.conf
```

#### Configuración básica comentada

```ini
listen=YES
anonymous_enable=NO
local_enable=YES
write_enable=YES
chroot_local_user=YES
pasv_enable=YES
pasv_min_port=40000
pasv_max_port=50000
```

🔹 **Explicación clave**:

* `anonymous_enable=NO` → desactiva acceso anónimo
* `local_enable=YES` → permite usuarios del sistema
* `write_enable=YES` → permite subir archivos
* `chroot_local_user=YES` → encierra al usuario en su carpeta

#### Reiniciar el servicio

```bash
sudo systemctl restart vsftpd
```

---

### 2. SFTP (SSH File Transfer Protocol)

SFTP es un **protocolo de transferencia de archivos seguro**, que **funciona sobre SSH**.

✔ Cifrado completo
✔ No necesita puertos adicionales
✔ Más seguro que FTP

⚠️ No es FTP cifrado, es un protocolo distinto.

#### Puerto

* **22/TCP** (el mismo que SSH)

#### Requisitos

* Tener SSH instalado y funcionando

#### Instalación de SSH

```bash
sudo apt install openssh-server
```

#### Uso de SFTP

Desde un cliente:

```bash
sftp usuario@ip_del_servidor
```

Comandos típicos dentro de SFTP:

* `ls` → listar archivos remotos
* `put archivo.txt` → subir archivo
* `get archivo.txt` → descargar archivo

#### Configuración avanzada (opcional)

Archivo:

```bash
/etc/ssh/sshd_config
```

Ejemplo para limitar usuarios a SFTP:

```ini
Subsystem sftp internal-sftp

Match User alumno
  ChrootDirectory /home/alumno
  ForceCommand internal-sftp
  AllowTcpForwarding no
```

---

### 3. SSH (Secure Shell)

SSH permite **acceder remotamente a la terminal de otro equipo**, de forma segura y cifrada.

Se utiliza para:

* Administración de servidores
* Ejecución remota de comandos
* Transferencia segura de archivos

#### Puerto

* **22/TCP**

#### Instalación

```bash
sudo apt install openssh-server
```

#### Comprobar estado

```bash
sudo systemctl status ssh
```

#### Conexión desde un cliente

```bash
ssh usuario@ip_del_servidor
```

#### Configuración básica

Archivo:

```bash
/etc/ssh/sshd_config
```

Opciones importantes:

```ini
Port 22
PermitRootLogin no
PasswordAuthentication yes
```

🔹 **Buenas prácticas**:

* No permitir login de root
* Cambiar el puerto en producción
* Usar claves en lugar de contraseña

#### Reiniciar servicio

```bash
sudo systemctl restart ssh
```

---

### 4. DNS (Domain Name System)

DNS es el servicio que **traduce nombres de dominio en direcciones IP**.

Ejemplo:

```
www.google.com → 142.250.184.36
```

Sin DNS, tendríamos que memorizar direcciones IP.

#### Puerto

* **53/UDP** (principal)
* **53/TCP** (transferencias de zona)

#### Software habitual

* `bind9`

#### Instalación

```bash
sudo apt install bind9
```

#### Archivos importantes

* `/etc/bind/named.conf`
* `/etc/bind/named.conf.local`
* `/etc/bind/db.ejemplo.local`

### Ejemplo de zona directa

```bash
zone "ejemplo.local" {
  type master;
  file "/etc/bind/db.ejemplo.local";
};
```

Archivo de zona:

```dns
$TTL 604800
@   IN  SOA servidor.ejemplo.local. admin.ejemplo.local. (
            2 604800 86400 2419200 604800 )
@       IN  NS  servidor.ejemplo.local.
servidor IN  A   192.168.1.10
www      IN  A   192.168.1.10
```

#### Comprobar sintaxis

```bash
sudo named-checkzone ejemplo.local /etc/bind/db.ejemplo.local
```

---

### 5. DHCP (Dynamic Host Configuration Protocol)

DHCP asigna automáticamente:

* Dirección IP
* Máscara de red
* Puerta de enlace
* DNS

A los equipos de una red.

#### Puerto

* **67/UDP** (servidor)
* **68/UDP** (cliente)

#### Software habitual

* `isc-dhcp-server`

#### Instalación

```bash
sudo apt install isc-dhcp-server
```

#### Interfaz de red

Archivo:

```bash
/etc/default/isc-dhcp-server
```

Ejemplo:

```ini
INTERFACESv4="eth0"
```

#### Configuración principal

Archivo:

```bash
/etc/dhcp/dhcpd.conf
```

Ejemplo de red:

```conf
subnet 192.168.1.0 netmask 255.255.255.0 {
  range 192.168.1.100 192.168.1.200;
  option routers 192.168.1.1;
  option domain-name-servers 192.168.1.10;
  default-lease-time 600;
  max-lease-time 7200;
}
```

#### Reiniciar servicio

```bash
sudo systemctl restart isc-dhcp-server
```

---

## Resumen final

| Servicio | Función principal         | Seguro | Puerto |
| -------- | ------------------------- | ------ | ------ |
| FTP      | Transferencia de archivos | ❌ No   | 21     |
| SFTP     | Transferencia segura      | ✔ Sí   | 22     |
| SSH      | Acceso remoto             | ✔ Sí   | 22     |
| DNS      | Resolución de nombres     | ✔      | 53     |
| DHCP     | Asignación IP automática  | ✔      | 67/68  |

---
