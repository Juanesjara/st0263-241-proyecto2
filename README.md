# 1. breve descripción de la actividad
El Proyecto 2 en el curso ST0263 de la Universidad EAFIT se desarrolla en desplegar una aplicación WordPress en un clúster de Kubernetes configurado en máquinas virtuales en la nube IaaS, utilizando microk8s. Este proyecto se enfoca en la alta disponibilidad a través de múltiples capas: aplicación, base de datos y almacenamiento, utilizando un servidor NFS para los servicios con estado. Debes implementar un balanceador de cargas, asegurar la disponibilidad de la base de datos y permitir el aumento dinámico de nodos en el clúster. 

## 1.1. Que aspectos cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
En cuanto al proyecto se logro configurar una infraestructura esencial para el mismo:
   - **Despliegue de WordPress y MySQL:** Usando los archivos de Deployment para WordPress y MySQL, configuraste cómo se deben crear y manejar las instancias de estas aplicaciones en el clúster.
   - **Almacenamiento persistente:** Con los archivos de PersistentVolume (PV) y PersistentVolumeClaim (PVC), preparaste el almacenamiento persistente necesario para WordPress y MySQL, lo que es crucial para la alta disponibilidad.
   - **Servicios y acceso al clúster:** Los archivos de Service e Ingress ayudan a exponer WordPress al tráfico externo y gestionar la comunicación dentro del clúster, respectivamente.

## 1.2. Que aspectos NO cumplió o desarrolló de la actividad propuesta por el profesor (requerimientos funcionales y no funcionales)
No se implementó un certificado SSL para la configuración de WordPress en Kubernetes. Los archivos de configuración actuales se centran en el despliegue, servicios, y almacenamiento de la aplicación y la base de datos, pero no incluyen detalles sobre la configuración de seguridad SSL/TLS para las comunicaciones encriptadas. Esto es esencial para asegurar que la información transmitida entre los usuarios y el sitio web 

# 2. información general de diseño de alto nivel, arquitectura, patrones, mejores prácticas utilizadas.
En cuanto a estos aspectos implementamos:
   - **Automatización de DevOps:** Se utilizaron archivos YAML para automatizar el despliegue de aplicaciones y servicios en Kubernetes, lo cual es una práctica clave en DevOps.
   - **Alta disponibilidad y escalabilidad:** Se configuraron réplicas para los deployments de WordPress y MySQL, además de utilizar persistent volumes y services que ayudan a mantener la disponibilidad y escalabilidad del proyecto.
----------------------------
# 3. Descripción del ambiente de desarrollo y técnico:

## detalles del desarrollo.
   - **Lenguaje de Programación:** PHP, típicamente la última versión estable o la que sea compatible con la versión de WordPress utilizada.
   - **WordPress:** Una versión específica de WordPress como WordPress 5.7.
   - **Base de Datos:** MySQL, con detalles sobre la versión exacta utilizada, que debe ser compatible con las exigencias de WordPress.
   - **Kubernetes:** Usando MicroK8s para la gestión del clúster, que simplifica el despliegue y manejo de cargas de trabajo en Kubernetes.
   - **Herramientas de DevOps:** Como Helm para la gestión de aplicaciones Kubernetes, y posiblemente Git para control de versiones.
     
## detalles técnicos:
   - **PHP:** Versión compatible con tu versión de WordPress, usualmente PHP 7.4 o superior.
   - **WordPress:** Versión específica como la 5.7, configurada para ejecutarse en contenedores Docker.
   - **MySQL:** Empleando una imagen de contenedor, por ejemplo, mysql:5.7, configurada para alta disponibilidad.
   - **Kubernetes:** Utilizando MicroK8s como la plataforma de orquestación de contenedores, configurada para soportar escalabilidad y alta disponibilidad.
   - **Almacenamiento:** PV y PVC en Kubernetes, utilizando NFS para almacenamiento compartido y persistente.
     
# 4. Descripción del ambiente de EJECUCIÓN

# IP o nombres de dominio en nube o en la máquina servidor.
Dominio del proyecto:
   - http://juanesjarar.tech/

## como se lanza el servidor.
El servidor se lanza corriendo todos los manifiestos con el comando 
   - microk8s kubectl apply -f "nombre del archivo"
      
# Referencias:
## https://microk8s.io/tutorials



