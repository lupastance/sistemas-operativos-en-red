# 4️⃣ Gestión de Recursos Compartidos y Seguridad

En un entorno de red, la **gestión eficiente de los recursos compartidos** es esencial para garantizar la productividad y la seguridad de los usuarios. Este tema aborda cómo configurar, administrar y proteger los recursos compartidos, como archivos, carpetas e impresoras, dentro de un dominio. Además, se analizarán los mecanismos de seguridad necesarios para regular el acceso, asegurando que cada usuario o grupo tenga los permisos adecuados según sus necesidades y responsabilidades.

La correcta **configuración de permisos y políticas de seguridad** no solo evita accesos no autorizados, sino que también protege la integridad y confidencialidad de los datos. Asimismo, aprenderás a monitorizar el uso de estos recursos, detectando posibles problemas y resolviéndolos de forma proactiva.

A lo largo del tema, trabajarás con herramientas propias de Windows Server, como el Administrador del Servidor y el Explorador de Archivos, para configurar recursos compartidos y gestionar los niveles de acceso. También exploraremos la implementación de estrategias de seguridad avanzadas, como la auditoría y el control de acceso basado en roles (RBAC), para cumplir con las necesidades específicas de un entorno profesional.

### **1. Introducción a los recursos compartidos en red**

Los recursos compartidos en red son una pieza clave en la administración de sistemas operativos en red, ya que permiten a los usuarios y equipos acceder y colaborar con recursos comunes de manera eficiente. Este apartado introduce los conceptos fundamentales, tipos de recursos compartidos y las herramientas que proporciona Windows Server para gestionarlos.

---

#### **1.1. ¿Qué son los recursos compartidos?**

Un recurso compartido es cualquier elemento dentro de una red que se pone a disposición de varios usuarios o dispositivos para su uso. Estos recursos pueden incluir archivos, carpetas, impresoras, conexiones a Internet, bases de datos, etc. 

Compartir recursos en una red permite:  
- **Optimizar el uso de recursos**: En lugar de que cada usuario tenga su propia impresora o copia de un archivo, estos se comparten y centralizan.  
- **Fomentar la colaboración**: Los usuarios pueden trabajar simultáneamente en un entorno de red al acceder a los mismos archivos o aplicaciones.  
- **Centralizar la administración**: Los administradores pueden gestionar el acceso, permisos y mantenimiento de recursos desde un único punto.

---

#### **1.2. Tipos de recursos compartidos**

En un entorno de red, los recursos compartidos más comunes son:  

1. **Archivos y carpetas**:  
   - **Archivos compartidos**: Documentos o aplicaciones a los que los usuarios pueden acceder desde cualquier equipo en la red.  
   - **Carpetas compartidas**: Estructuras jerárquicas que contienen archivos organizados y permiten la gestión centralizada del contenido.  

2. **Impresoras**:  
   - Permiten que varios usuarios envíen trabajos de impresión a través de la red, reduciendo la necesidad de dispositivos individuales.  

3. **Unidades de red**:  
   - Son particiones o discos completos compartidos para proporcionar almacenamiento centralizado y accesible desde varios equipos.  

4. **Aplicaciones y servicios**:  
   - Software o servicios alojados en un servidor, como bases de datos o sistemas ERP, accesibles para los usuarios autorizados.  

---

#### **1.3. Importancia de compartir recursos**

Compartir recursos en un entorno de red tiene ventajas significativas tanto para los usuarios como para los administradores:  

- **Ahorro de costes**: Reducir la necesidad de hardware duplicado, como impresoras o discos duros externos.  
- **Eficiencia operativa**: Facilitar el acceso a la información y mejorar la colaboración.  
- **Seguridad**: Centralizar el control de acceso y permisos para garantizar que solo los usuarios autorizados accedan a los recursos.  
- **Escalabilidad**: Permitir la adición de más usuarios o equipos sin afectar el rendimiento o la accesibilidad.  

Ejemplo práctico:  
En una empresa, compartir una carpeta llamada "Proyectos" permite que varios equipos colaboren en tiempo real, mientras que un administrador controla quién puede modificar o solo visualizar los documentos.  

---

#### **1.4. Herramientas en Windows Server para gestionar recursos compartidos**

Windows Server incluye diversas herramientas para facilitar la gestión de recursos compartidos. Estas herramientas ofrecen interfaces gráficas y comandos para configurar, supervisar y controlar los recursos.  

1. **Administrador del Servidor**:  
   - Una consola centralizada para añadir roles y características, como el de compartir archivos e impresoras.  
   - Permite configurar rápidamente carpetas compartidas y establecer permisos.  

2. **Explorador de archivos**:  
   - Los recursos se pueden compartir directamente desde las propiedades de una carpeta o archivo.  

3. **PowerShell**:  
   - Herramienta avanzada para configurar recursos compartidos mediante comandos.  
   - Ejemplo:  
     ```powershell
     New-SmbShare -Name "Documentos" -Path "C:\Carpetas\Documentos" -FullAccess "GrupoUsuarios"
     ```

4. **Consolas administrativas específicas**:  
   - **Gestión de impresión** para administrar impresoras compartidas.  
   - **Gestión de almacenamiento** para compartir unidades de red.  

5. **Directivas de grupo (GPO)**:  
   - Permiten automatizar la configuración de recursos compartidos y asignar permisos específicos en entornos grandes.  

---

## 🔰 Ejercicios

Supongamos que debéis gestionar una red ficticia con tres departamentos: Finanzas, Marketing y Recursos Humanos.  

- **Actividad 1**: Crear tres carpetas en el servidor:  
  - Finanzas: Solo accesible para los miembros del departamento de Finanzas.  
  - Marketing: Accesible para Marketing, pero en modo solo lectura para el resto.  
  - Recursos Humanos: Permitir que todos los usuarios puedan leer, pero solo el departamento de RRHH pueda modificar.  

- **Resultado esperado**:  
  Debéis configurar las carpetas compartidas utilizando el Administrador del Servidor, asignar permisos adecuados y probar el acceso desde equipos cliente.

---

### **Ejercicios prácticos**  

1. **Crear una carpeta compartida básica**  
   - En el servidor con Windows Server, los alumnos deben crear una carpeta llamada `RecursosGenerales` en `C:\`.
   - Configurar esta carpeta para que sea accesible para todos los usuarios de la red en modo de solo lectura.

2. **Configurar permisos avanzados en carpetas compartidas**  
   - Crear una carpeta llamada `PrivadoFinanzas` y configurarla para que solo el grupo `Finanzas` tenga permisos de lectura y escritura.  
   - Comprobar que otros usuarios no puedan acceder.

3. **Mapear una unidad de red**  
   - Desde un equipo cliente, los alumnos deben mapear la carpeta compartida `RecursosGenerales` como una unidad de red (por ejemplo, Z:).  
   - Verificar que el contenido sea accesible.

4. **Crear un recurso compartido para impresoras**  
   - Instalar una impresora ficticia (impresora PDF) en el servidor.  
   - Compartir la impresora con la red y permitir que los equipos cliente la usen.  

5. **Configurar múltiples niveles de acceso**  
   - Crear tres carpetas (`Marketing`, `Ventas`, `Soporte`) y asignar los siguientes permisos:  
     - `Marketing`: Lectura para todos, escritura solo para el grupo Marketing.  
     - `Ventas`: Lectura y escritura para el grupo Ventas, acceso denegado a otros.  
     - `Soporte`: Acceso completo para todos los usuarios.

6. **Usar PowerShell para compartir recursos**  
   - Configurar una carpeta compartida mediante PowerShell utilizando el siguiente comando:  
     ```powershell
     New-SmbShare -Name "EjemploPowerShell" -Path "C:\Compartido" -FullAccess "Usuarios"
     ```
   - Verificar que el recurso esté compartido.

7. **Auditoría de acceso**  
   - Habilitar la auditoría en una carpeta compartida (`/Finanzas`) para registrar qué usuarios acceden y modifican archivos.  
   - Consultar los registros de eventos en el visor de sucesos.

8. **Configurar el acceso basado en la red**  
   - Crear una carpeta compartida y limitar el acceso únicamente a las direcciones IP dentro de un rango específico.  
   - Comprobar que fuera del rango no sea accesible.

9. **Gestión de permisos heredados**  
   - Crear una carpeta con subcarpetas y configurar permisos diferentes para las subcarpetas eliminando la herencia en cada una de ellas.  
   - Documentar los pasos y verificar los accesos desde un cliente.

10. **Configurar recursos compartidos utilizando GPO**  
    - Crear una política de grupo que configure automáticamente el acceso a la carpeta `DocumentosCorporativos` para todos los usuarios al iniciar sesión en los equipos cliente.  
    - Verificar que se aplique correctamente.

---

### **Ejercicios teóricos**  

1. Define qué es un recurso compartido en red y da dos ejemplos prácticos.  

2. Explica las diferencias entre los tipos de permisos: **Lectura**, **Cambios** y **Control total** en Windows Server.  

3. Enumera tres beneficios de compartir recursos en una red empresarial.  

4. ¿Qué herramienta de Windows Server se utiliza para compartir carpetas y administrar sus permisos?  

5. ¿Qué diferencia hay entre compartir una carpeta desde el **Explorador de archivos** y desde el **Administrador del Servidor**?  

6. Explica el concepto de unidad de red. ¿Por qué se utiliza?  

7. Describe cómo los permisos de carpeta compartida interactúan con los permisos del sistema de archivos NTFS.  

8. ¿Qué es una impresora compartida? ¿Qué ventajas ofrece en un entorno de oficina?  

9. ¿Qué riesgos de seguridad pueden existir al compartir recursos en una red?  

10. Explica el proceso de configuración de auditoría para un recurso compartido. ¿Qué utilidad tiene esta función?  

---