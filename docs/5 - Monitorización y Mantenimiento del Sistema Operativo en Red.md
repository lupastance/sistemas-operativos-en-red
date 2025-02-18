# 5️⃣ Monitorización y Mantenimiento del Sistema Operativo en Red

![Sistemas](assets/monitor.png){align="right"}

La administración de un sistema operativo en red requiere una monitorización constante para garantizar su correcto funcionamiento y prevenir problemas de rendimiento, seguridad o disponibilidad. Este tema abordará las herramientas y técnicas utilizadas para supervisar el sistema, detectar incidencias y optimizar el rendimiento de los recursos. Además, se estudiarán las operaciones de mantenimiento y automatización de tareas para mejorar la eficiencia en la gestión del sistema.  

---

### **1. Características de los Programas de Monitorización**  

Los programas de monitorización del sistema operativo en red permiten obtener información detallada sobre el estado y rendimiento de los equipos y servidores. Estas herramientas son esenciales para la administración de sistemas, ya que facilitan la detección de problemas y la optimización de los recursos disponibles.  

#### **Importancia de la Monitorización en Redes**  

La supervisión de un sistema operativo en red es fundamental para:  

- **Prevenir fallos y caídas del sistema**: Permite detectar anomalías antes de que causen problemas graves.  
- **Optimizar el rendimiento**: Ayuda a identificar procesos que consumen demasiados recursos.  
- **Garantizar la seguridad**: Alerta sobre accesos no autorizados o actividad sospechosa.  
- **Facilitar la administración remota**: Permite gestionar múltiples servidores desde una única consola.  
- **Cumplir con normativas**: Empresas e instituciones deben monitorizar la actividad para cumplir con regulaciones de seguridad.  

#### **Tipos de Monitorización**  

Existen diferentes formas de monitorización según los objetivos y necesidades del sistema:  

#### **Monitorización de Recursos del Sistema**  
Evalúa el uso de CPU, memoria, disco y red para detectar cuellos de botella.  

- **CPU Usage**: Detecta procesos que consumen demasiados recursos.  
- **Memory Usage**: Identifica fugas de memoria o consumo excesivo de RAM.  
- **Disk I/O**: Analiza velocidad de lectura/escritura en discos duros y SSD.  
- **Network Traffic**: Monitorea la actividad de red para prevenir saturaciones.  

#### **Monitorización de Eventos del Sistema**  
Permite detectar fallos en hardware o software mediante el análisis de logs.  

- **Registros de errores**: Problemas de controladores o fallos del sistema.  
- **Intentos de acceso fallidos**: Detección de posibles intentos de ataque.  
- **Estado de servicios y procesos**: Supervisión de procesos críticos del sistema.  

#### **Monitorización de Seguridad**  
Ayuda a prevenir intrusiones y ataques mediante auditorías y control de accesos.  

- **Análisis de tráfico de red**: Identificación de conexiones sospechosas.  
- **Control de cambios en archivos**: Protección contra malware y ransomware.  
- **Registro de actividad de usuarios**: Auditoría de accesos a servidores.  

#### **Supervisión en Tiempo Real**  
Las herramientas modernas permiten ver el estado del sistema en tiempo real, con dashboards interactivos que muestran gráficos y estadísticas de uso.  

Ejemplo:  
- **Windows Task Manager** muestra el uso de CPU y memoria en vivo.  
- **htop (Linux)** permite ver procesos en ejecución con actualización constante.  

#### **Alertas y Notificaciones**  
Muchos programas de monitorización envían alertas cuando se detectan problemas, como:  
- Consumo excesivo de recursos.  
- Intentos de acceso sospechosos.  
- Fallos en hardware o servicios críticos.  

Ejemplo:  
- **Nagios/Zabbix** permiten configurar notificaciones por correo o SMS.  
- **Windows Event Viewer** muestra alertas de errores en el sistema.  

#### **Análisis de Tendencias y Registros Históricos**  
Las herramientas avanzadas registran datos históricos para evaluar tendencias en el rendimiento del sistema.  

Ejemplo:  
- **Performance Monitor (Windows)** almacena métricas de uso de CPU y memoria.  
- **Elasticsearch + Kibana** permiten visualizar logs del sistema en tiempo real.  

#### **Interfaces Gráficas vs. Línea de Comandos**  
Algunas herramientas proporcionan una interfaz gráfica para facilitar la supervisión, mientras que otras funcionan desde la terminal.  

Ejemplo:  
- **Windows Task Manager** tiene interfaz gráfica amigable.  
- **top/htop (Linux)** funcionan en línea de comandos.  

#### **Compatibilidad con Protocolos de Red**  
Muchas herramientas utilizan protocolos estándar para la recopilación de datos.  

Ejemplo:  
- **SNMP (Simple Network Management Protocol)** para supervisión de redes.  
- **WMI (Windows Management Instrumentation)** para gestión de sistemas Windows.  

#### **Herramientas Incluidas en Windows**  

- **Task Manager (Administrador de Tareas)**  
  - Permite ver el uso de CPU, RAM y disco.  
  - Se accede con *Ctrl + Shift + Esc*.  

- **Performance Monitor (Monitor de Rendimiento)**  
  - Analiza el rendimiento del sistema con gráficos detallados.  
  - Se ejecuta con `perfmon.msc`.  

- **Event Viewer (Visor de Eventos)**  
  - Registra errores, advertencias y eventos críticos del sistema.  
  - Se accede con `eventvwr.msc`.  

- **Resource Monitor (Monitor de Recursos)**  
  - Proporciona información detallada sobre los procesos activos.  
  - Se ejecuta con `resmon`.  

### **Herramientas Incluidas en Linux**  

- **top/htop**  
  - Monitoriza procesos en ejecución y consumo de recursos.  

- **iostat/vmstat**  
  - Evalúa el rendimiento del disco y la memoria.  

- **journalctl**  
  - Analiza logs del sistema en distribuciones con systemd.  

- **netstat/ss**  
  - Muestra conexiones de red activas.  

---

#### **Herramientas de Monitorización en Red**  

- **Nagios**  
  - Supervisión avanzada de servidores y redes.  
  - Envía alertas en caso de fallos.  

- **Zabbix**  
  - Alternativa a Nagios con interfaz web moderna.  

- **Wireshark**  
  - Captura y analiza paquetes de red.  

- **SolarWinds**  
  - Solución de monitorización profesional para grandes empresas.  

#### **Ejercicios Prácticos**  

1. **Supervisión del sistema con Task Manager y htop**  
   - Abre el Administrador de Tareas en Windows y observa qué procesos consumen más CPU y memoria.  
   - En Linux, ejecuta `htop` y filtra por procesos más pesados.  

2. **Análisis de eventos del sistema**  
   - En Windows, abre el Visor de Eventos (`eventvwr.msc`) y revisa errores recientes en la categoría "Sistema".  
   - En Linux, usa `journalctl -xe` para ver logs en tiempo real.  

3. **Monitorización de tráfico de red con netstat y Wireshark**  
   - Ejecuta `netstat -ano` en Windows o `ss -tulnp` en Linux para ver conexiones activas.  
   - Usa Wireshark para capturar tráfico de red y analizar paquetes sospechosos.  

4. **Configuración de alertas en Nagios o Zabbix**  
   - Instala Nagios en un servidor y configura alertas para consumo excesivo de CPU.  
   - Usa Zabbix para monitorear el uso de memoria RAM y recibir notificaciones.  

---

### **2. Identificación de Problemas de Rendimiento en los Dispositivos de Almacenamiento**  

El rendimiento del almacenamiento es un factor crítico en la estabilidad y velocidad de un sistema operativo en red. Un disco lento o defectuoso puede afectar drásticamente el tiempo de respuesta de aplicaciones, bases de datos y sistemas de archivos, lo que impacta directamente en la productividad y experiencia del usuario.  

#### **Importancia del Rendimiento en el Almacenamiento**  

Los dispositivos de almacenamiento, como discos duros (HDD), unidades de estado sólido (SSD) y soluciones en red (NAS, SAN), desempeñan un papel crucial en el acceso y almacenamiento de datos. Un mal rendimiento en el almacenamiento puede causar:  

- **Tiempos de carga elevados** en aplicaciones y sistemas operativos.  
- **Retrasos en la ejecución de comandos y procesos** en servidores.  
- **Problemas en bases de datos** debido a tiempos de respuesta lentos.  
- **Pérdida de datos** si los discos presentan sectores defectuosos o fallos críticos.  

Para evitar estos problemas, es fundamental identificar y solucionar cualquier deficiencia en el rendimiento del almacenamiento.  

### **Parámetros Claves en el Rendimiento del Almacenamiento**  

Para evaluar el rendimiento de un dispositivo de almacenamiento, se analizan los siguientes factores:  

#### **Latencia**  
Tiempo que tarda el dispositivo en responder a una solicitud de lectura o escritura.  

- **Valores normales**:  
  - HDD: 5-10 ms  
  - SSD SATA: 0.1-0.3 ms  
  - SSD NVMe: 0.01 ms  

Una alta latencia indica problemas con el disco o el sistema de archivos.  

##### **Velocidad de Lectura y Escritura (Throughput)**  
Cantidad de datos que pueden ser leídos o escritos por segundo, medida en MB/s o GB/s.  

- **Valores aproximados:**  
  - HDD (5400 RPM): ~100 MB/s  
  - HDD (7200 RPM): ~150 MB/s  
  - SSD SATA: ~500 MB/s  
  - SSD NVMe: ~3000 MB/s  

Bajas velocidades pueden indicar problemas de hardware o configuración inadecuada.  

---

#### **Operaciones de Entrada/Salida por Segundo (IOPS)**  
Mide cuántas operaciones de lectura/escritura puede manejar el almacenamiento en un segundo.  

- HDD: ~100 IOPS  
- SSD SATA: ~100K IOPS  
- SSD NVMe: ~500K-1M IOPS  

Bajos valores de IOPS pueden afectar el rendimiento de servidores y bases de datos.  

#### **Estado del Disco (SMART)**  
El sistema SMART (Self-Monitoring, Analysis, and Reporting Technology) permite evaluar la salud del disco y detectar sectores defectuosos.  

Ejemplo de atributos SMART importantes:  
- **Reallocated Sectors Count**: Sectores defectuosos reasignados.  
- **Current Pending Sector Count**: Sectores pendientes de reparación.  
- **Power-On Hours**: Tiempo total de uso del disco.  

Un alto número de sectores defectuosos puede indicar que el disco está fallando.  

#### **Herramientas de Diagnóstico y Monitorización**  

Para analizar el rendimiento de los dispositivos de almacenamiento, se utilizan diversas herramientas:  

#### **En Windows**  

- **Task Manager (Administrador de Tareas)**  
  - Pestaña "Rendimiento" → Disco  
  - Muestra uso del disco y velocidad de lectura/escritura.  

- **Resource Monitor (Monitor de Recursos)**  
  - `resmon` en la consola.  
  - Proporciona información detallada de procesos que acceden al disco.  

- **CrystalDiskInfo**  
  - Muestra el estado SMART del disco.  

- **Winsat**  
  - `winsat disk` evalúa la velocidad del disco.  

#### **En Linux**  

- **iostat** (`sudo apt install sysstat`)  
  - `iostat -x 1` muestra estadísticas de uso del disco.  

- **hdparm**  
  - `sudo hdparm -tT /dev/sda` mide la velocidad del disco.  

- **smartctl** (`sudo apt install smartmontools`)  
  - `sudo smartctl -a /dev/sda` muestra el estado SMART.  

- **iotop** (`sudo apt install iotop`)  
  - Muestra los procesos que consumen más I/O de disco.  

- **df -h**  
  - Verifica el espacio en disco disponible.  

### **Identificación de Problemas Comunes y Soluciones**

#### **Disco Saturado al 100%**  
💡 **Síntomas**:  
- Sistema lento.  
- Aplicaciones tardan en abrirse.  
- Uso del disco al 100% en el Administrador de Tareas (Windows) o `iotop` (Linux).  

✅ **Soluciones**:  
1. Cerrar programas en segundo plano que usen el disco.  
2. Desactivar la indexación de Windows (`services.msc → Windows Search → Deshabilitar`).  
3. Revisar logs con `journalctl` (Linux) o `eventvwr.msc` (Windows).  
4. Verificar que no haya malware con **Malwarebytes** o **ClamAV**.  

#### **Baja Velocidad de Lectura/Escritura**  
💡 **Síntomas**:  
- Transferencias de archivos muy lentas.  
- Tiempos de carga largos en programas.  

✅ **Soluciones**:  
1. Comprobar el estado SMART del disco.  
2. En HDDs, desfragmentar (`defrag` en Windows, `e4defrag` en Linux).  
3. En SSDs, verificar si **TRIM** está activado:  
   - Windows: `fsutil behavior query DisableDeleteNotify` (debe ser 0).  
   - Linux: `sudo fstrim -v /`.  
4. Revisar la conexión SATA/NVMe.  

#### **Sectores Defectuosos**  
💡 **Síntomas**:  
- Archivos dañados o ilegibles.  
- Errores SMART.  

✅ **Soluciones**:  
1. Ejecutar diagnóstico SMART (`smartctl -a /dev/sda`).  
2. En Windows, ejecutar `chkdsk /f /r`.  
3. En Linux, usar `fsck` (`sudo fsck -y /dev/sda1`).  
4. Hacer copia de seguridad y considerar reemplazo del disco.  

#### **Ejercicios Prácticos**  

1️⃣ **Analizar el rendimiento del disco en Windows**  
- Abre el Administrador de Tareas y ve a la pestaña "Rendimiento".  
- Observa el uso del disco y la velocidad de lectura/escritura.  
- Explica qué procesos están consumiendo más recursos.  

2️⃣ **Medir el rendimiento del disco en Linux**  
- Usa `iostat -x 1` y analiza las métricas.  
- Ejecuta `hdparm -tT /dev/sda` para comprobar la velocidad.  
- Explica qué valores indican un posible problema.  

3️⃣ **Comprobar el estado SMART de un disco**  
- En Windows, usa **CrystalDiskInfo**.  
- En Linux, usa `smartctl -a /dev/sda`.  
- Identifica si hay sectores defectuosos.  

4️⃣ **Optimización de almacenamiento**  
- Desfragmenta un HDD en Windows (`defrag`).  
- Activa TRIM en un SSD (`fsutil behavior set DisableDeleteNotify 0`).  
- Compara antes y después de la optimización.  

---

## **3. Observación de la Actividad del Sistema Operativo en Red**  

### **3.1. Logs y Registros del Sistema**  

Los sistemas operativos en red generan archivos de registro (logs) que permiten analizar su funcionamiento y detectar fallos.  

- **Windows Event Viewer (Visor de Eventos)**:  
  - Application Logs: Registros de programas y servicios.  
  - Security Logs: Intentos de acceso y fallos de autenticación.  
  - System Logs: Errores de hardware y controladores.  

### **3.2. Monitorización del Tráfico de Red**  

- **Wireshark**: Captura paquetes para analizar comunicación entre dispositivos.  
- **Netstat**: Muestra conexiones activas y puertos en uso.  
- **Ping y Tracert**: Diagnostican problemas de conectividad.  

---

## **4. Mantenimiento del Software Instalado en el Sistema**  

El mantenimiento del software es fundamental para la seguridad y estabilidad del sistema operativo en red.  

### **4.1. Actualización y Gestión de Software**  

- **Windows Update**: Instala actualizaciones de seguridad y parches del sistema.  
- **Chocolatey / Winget**: Herramientas para instalar y gestionar paquetes de software en Windows.  
- **Group Policy (GPOs)**: Permiten aplicar configuraciones automáticas a varios equipos en una red.  

### **4.2. Eliminación de Software Innecesario**  

- **Programas innecesarios o en desuso** pueden consumir recursos y generar vulnerabilidades.  
- **MSConfig / Task Manager**: Administran programas en el inicio del sistema.  
- **PowerShell (Get-AppxPackage / Remove-AppxPackage)**: Desinstalan aplicaciones mediante línea de comandos.  

---

## **5. Automatización de Tareas del Sistema**  

Automatizar tareas permite optimizar la gestión del sistema y reducir errores humanos.  

### **5.1. Programación de Tareas en Windows**  

Windows incluye herramientas para programar tareas de mantenimiento:  

- **Task Scheduler (Programador de Tareas)**: Ejecuta tareas en momentos programados.  
- **PowerShell Scripting**: Permite crear scripts avanzados para automatizar configuraciones.  
- **Batch Scripts (.bat)**: Utilizados para tareas básicas como copias de seguridad o limpieza de archivos temporales.  

### **5.2. Ejemplos de Automatización**  

- Programar un reinicio automático semanal de servidores.  
- Configurar la eliminación automática de logs antiguos.  
- Realizar copias de seguridad diarias con scripts de PowerShell.  

---

## **6. Interpretación de la Configuración del Sistema Operativo en Red**  

Es fundamental conocer la configuración del sistema operativo para diagnosticar problemas y optimizar su funcionamiento.  

### **6.1. Comprobación de la Configuración del Sistema**  

- **System Information (msinfo32)**: Proporciona detalles sobre hardware y software.  
- **IPConfig / Get-NetIPAddress**: Muestra configuración de red.  
- **Services.msc**: Gestiona los servicios del sistema.  
- **Control de Cuentas de Usuario (UAC)**: Configura niveles de seguridad y permisos de aplicaciones.  

---

## **Ejercicios Prácticos**  

1. **Monitorización del rendimiento**:  
   - Usar el **Monitor de Rendimiento** para detectar cuellos de botella en CPU y RAM.  
   - Analizar procesos en ejecución con **Process Explorer**.  

2. **Diagnóstico de almacenamiento**:  
   - Utilizar **CrystalDiskInfo** para verificar el estado del disco.  
   - Identificar procesos con alto uso de disco en el **Administrador de Tareas**.  

3. **Análisis de eventos del sistema**:  
   - Consultar logs en el **Visor de Eventos** y detectar intentos fallidos de inicio de sesión.  
   - Usar **Wireshark** para analizar tráfico de red y detectar paquetes sospechosos.  

4. **Gestión de software**:  
   - Instalar una aplicación con **Winget** y programar su actualización automática.  
   - Configurar una política de grupo para bloquear la instalación de software no autorizado.  

5. **Automatización de tareas**:  
   - Crear un script de PowerShell que elimine archivos temporales cada semana.  
   - Configurar el **Programador de Tareas** para realizar copias de seguridad de una carpeta compartida.  

6. **Interpretación de configuración del sistema**:  
   - Ejecutar **msinfo32** y guardar un informe con la configuración del equipo.  
   - Identificar la configuración de red mediante **IPConfig** y modificarla manualmente.  