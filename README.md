# Laboratorio 7: Gestión del Conocimiento (Knowledge Management) bajo el Marco ITIL

Este laboratorio práctico simula un escenario real de gobernanza TI y gestión del conocimiento alineado con las buenas prácticas de **ITIL**. El objetivo es transformar el conocimiento técnico adquirido en el despliegue de software (Laboratorio 6) en activos de información de valor tanto para el equipo de soporte como para los usuarios finales de la organización.

El repositorio está dividido en dos secciones estratégicas:
1. **Procedimiento Operativo Estándar (SOP):** Documentación técnica y estricta para el equipo de Soporte L1/L2.
2. **Artículo de Base de Conocimiento (KB):** Guía de autoayuda en lenguaje no técnico para los empleados de la empresa.

---

## 🛠️ Parte 1: Procedimiento Operativo Estándar (SOP)
**Código:** SOP-IT-006  
**Audiencia:** Técnicos de Soporte L1 / L2 / Administradores de Sistemas  
**Estado:** Aprobado  

### 1. Objetivo
Establecer el procedimiento estándar para la instalación de software corporativo en estaciones de trabajo de forma masiva y silenciosa, garantizando la nula interrupción de las actividades de los usuarios finales.

### 2. Alcance y Prerrequisitos
* **Alcance:** Aplicable a todas las estaciones de trabajo Windows (10/11) y entornos Windows Server gestionados por el equipo de Soporte Técnico.
* **Permisos:** Se requieren credenciales de **Administrador Local** o de **Dominio** en la máquina de destino.
* **Formato:** El instalador debe estar empaquetado exclusivamente en formato **`.msi`** (Windows Installer).

### 3. Procedimiento de Ejecución (Consola)
1. Iniciar la consola de **PowerShell** con privilegios elevados (Ejecutar como Administrador).
2. Ejecutar la sintaxis del motor `msiexec` inyectando los modificadores de fondo obligatorios:

```powershell
msiexec /i "C:\Users\Administrator\Downloads\7z2601-x64.msi" /qn /norestart
```

/i : Declaración explícita de Instalación (Install).

/qn : Modificador Quiet con No UI (Sin Interfaz de Usuario). Fuerza la ejecución invisible en segundo plano, suprimiendo pop-ups o barras de carga.

/norestart : Bloquea cualquier solicitud de reinicio automático del sistema operativo, protegiendo el trabajo del usuario.

### 4. Fase de Verificación y Auditoría
Al operar de forma silenciosa, el técnico debe auditar el éxito de la tarea listando el directorio nativo del programa mediante CLI:
```powershell
Get-ChildItem "C:\Program Files\7-Zip"
```
---

📦 Parte 2: Artículo de Base de Conocimiento (KB)
Código: KB-USER-042

Audiencia: Personal Administrativo / Usuarios Finales de la Empresa

Aplicación: 7-Zip (Compresor de Archivos Oficial)

📢 ¡Ya tienes disponible 7-Zip en tu equipo!
Desde el departamento de Soporte TI hemos instalado de forma automática en tu ordenador la herramienta 7-Zip. Este programa te permitirá reducir el tamaño de tus archivos para enviarlos por correo más fácilmente y abrir carpetas comprimidas que te envíen nuestros clientes.

Aquí tienes una guía rápida de uso en menos de 1 minuto:

1. Cómo comprimir una carpeta para enviarla por correo
Si tienes archivos que pesan mucho y la plataforma de correo no te deja adjuntarlos:

Haz clic derecho sobre la carpeta o archivo que quieras achicar.

En el menú flotante, busca la opción 7-Zip y luego haz clic en "Añadir a 'Nombre_de_tu_carpeta.zip'".

¡Listo! Se creará un nuevo archivo con el icono de una carpeta con cremallera en ese mismo lugar. Ese es el archivo ligero que debes adjuntar en tu correo.

🔒 Tip de Seguridad: Si necesitas enviar datos sensibles (DNI, contratos, nóminas), haz clic en "Añadir al archivo..." y escribe una contraseña en la sección derecha antes de aceptar.

2. Cómo abrir (descomprimir) un archivo que te ha enviado un cliente
Si recibes un correo con un archivo que termina en .zip o .rar:

Haz clic derecho sobre el archivo comprimido que has descargado.

Selecciona la opción 7-Zip en el menú.

Haz clic en "Extraer aquí" (Extract here).

El contenido se guardará automáticamente en una carpeta normal en ese mismo sitio para que puedas abrir los documentos sin problemas.

🎯 Habilidades Consolidadas en este Laboratorio
Gobernanza TI bajo ITIL: Aplicación práctica del proceso de Gestión del Conocimiento (Knowledge Management), asegurando que el conocimiento técnico no se pierda y sea accesible.

Redacción Técnica de TI (Technical Writing): Capacidad para estructurar un Procedimiento Operativo Estándar (SOP) riguroso, indexado y con control de excepciones para equipos de ingeniería.

Comunicación Orientada al Cliente (User-Centricity): Habilidad para traducir conceptos técnicos complejos (líneas de comandos, hilos de fondo, switches lógicos) en instrucciones amigables, sencillas y útiles para usuarios de negocio, reduciendo el volumen de tickets repetitivos en el Service Desk.
