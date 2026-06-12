# Centro de operaciones de seguridad con AWS

El repositorio contiene los elementos necesarios para la creación de centro de operaciones de seguridad con la plataforma de AWS.

##Integrantes del proyecto

Kevin Antonio Andrade López
Andrés Job Melchor Almaraz
Dulce Esmeralda Muñoz Sanchez

##Tecnologías y Herramientas Utilizadas

* **Proveedor de Nube:** Amazon Web Services (AWS)
* **Infraestructura como código (IaC):** Terraform
* **Automatización y CLI:** AWS CLI v2
* **Monitoreo:**  AWS CloudWatch
* **Seguridad:** AWS IAM 

## Actividades Implementadas

### 1. Gestión de Identidades y Accesos (IAM) y Seguridad Base
* **Activación de MFA:** Se aseguró la cuenta raíz y los usuarios administradores mediante autenticación multifactor para mitigar riesgos de acceso no autorizado.
* **Roles de IAM específicos:** Creación de roles de IAM para servicios (como instancias EC2), eliminando la necesidad de almacenar llaves de acceso en texto plano y otorgando permisos bajo el principio de menor privilegio (ej. `CloudWatchAgentServerPolicy`, `ADMIN-IAM`).
* **Usuario de Automatización:** Configuración de un usuario dedicado (`terraform-admin-cli`) con la política `AdministratorAccess` gestionada de forma segura para despliegues automatizados.

### 2. Preparación del Entorno Local y Herramientas CLI
* **AWS CLI:** Instalación y configuración de la interfaz de línea de comandos de AWS para la interacción directa con la API del proveedor de nube.
* **Terraform:** Inicialización y configuración del entorno local para el aprovisionamiento automatizado y versionado de los recursos de red y cómputo.

### 3. Telemetría y Monitoreo Avanzado
* **Agente de CloudWatch:** Implementación y configuración del agente oficial de AWS CloudWatch dentro de las instancias virtuales EC2 para recolectar métricas avanzadas a nivel de sistema operativo y centralizar logs de auditoría en tiempo real.
