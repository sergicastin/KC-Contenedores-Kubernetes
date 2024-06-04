# Práctica: Generación de Manifiestos de Kubernetes y Charts de Helm

## Descripción de Ejercicios de Kubernetes

Este repositorio contiene ejercicios prácticos que cubren la generación de manifiestos de Kubernetes y la creación de charts de Helm. A continuación se resumen los pasos principales:

### Generación de Manifiestos de Kubernetes (directorio `k8s/`)

1. **Utilización de Imágenes Existentes**: Se utilizan imágenes previamente creadas y almacenadas en Docker Hub.
   
2. **Deployment y Servicios**: Se implementa un Deployment para la aplicación y se crean Servicios para exponerla dentro y fuera del clúster.
   
3. **StatefulSet para la Base de Datos**: Se utiliza un StatefulSet para desplegar la base de datos, con PersistentVolumeClaim para almacenamiento persistente.
   
4. **Ingress para Acceso Externo**: Se añade un Ingress para exponer la aplicación al exterior mediante un Ingress Controller.
   
5. **ConfigMaps y Secrets**: Se utilizan ConfigMaps para datos de configuración no sensibles y Secrets para datos sensibles, con documentación sobre cómo generarlos.
   
6. **README de Kubernetes**: Se documentan todos los recursos creados y se detallan las configuraciones personalizables. Se incluyen instrucciones de despliegue y pruebas de la aplicación.

### Generación de Charts de Helm (directorio `charts/`)

1. **Componentes del Chart**: El chart de Helm incluye Deployment, Service, PersistentVolumeClaim (para la base de datos), Ingress, ConfigMap y Secret.
   
2. **README de Helm Chart**: Se proporciona flexibilidad y configurabilidad al chart de Helm, explicando las modificaciones posibles en el archivo `values.yaml`. Se detallan las opciones para habilitar/deshabilitar Ingress, exponer la aplicación con un servicio LoadBalancer, entre otros.

### Requisitos Adicionales de Kubernetes y Helm

9. **Agrupación de PODs**: Se asegura que los PODs de la base de datos y la aplicación permanezcan lo más juntos posible al desplegarse en Kubernetes.
   
10. **Separación de Réplicas de Aplicación**: Se garantiza que los PODs de las réplicas de la aplicación permanezcan lo más separados posible entre sí.
   
11. **Autoescalado de la Aplicación**: Se implementa autoescalado opcional cuando el uso de CPU excede el 70%, manteniendo una alta disponibilidad.
   
12. **Almacenamiento Persistente Dinámico**: Se utiliza almacenamiento persistente provisionado de forma dinámica para la base de datos en el StatefulSet.
   
13. **Configuración Externa mediante Secrets y ConfigMaps**: Se evita el uso de datos "hardcoded" utilizando Secrets y ConfigMaps para la configuración externa.

Este repositorio ofrece una práctica completa para aprender a trabajar con Kubernetes y Helm, abordando los principales aspectos del despliegue de aplicaciones en un entorno de contenedores.

## Enlaces a Documentación Detallada

- [Directorio charts](./charts/README.md): Documentación detallada del chart de Helm.
- [Directorio k8s](./K8S/README.md): Documentación detallada de los manifiestos de Kubernetes.
