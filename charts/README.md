# Chart de Helm

Este chart de Helm simplifica la gestión y despliegue de una aplicación en Kubernetes. Aquí se resume el archivo `Values.yaml`, dividiendo la información confidencial en `secrets.yaml` y la no confidencial en `configmap.yaml`. Además, se han configurado aspectos como la afinidad para mantener los pods lo más cerca posible y el autoescalado de la aplicación web con un máximo del 70% de uso de la CPU, mientras que se asegura que los pods permanezcan lo más separados posible con un anti-affinity definido en el deployment. Se ha utilizado también un almacenamiento persistente definido en el archivo `persistentvolumeclaim.yaml`.

## Instrucciones

1. Si aún no has comprometido los archivos, ejecuta `helm package sergichart` en el mismo directorio.
2. Una vez que tengas un archivo comprimido `.tgz`, ejecuta `helm install my-release sergichart-0.1.0.tgz`, donde `my-release` es el nombre que deseas asignar a la aplicación, y `sergichart-0.1.0.tgz` es el nombre del archivo comprimido.
3. Verifica que todo se haya desplegado correctamente ejecutando `helm list`, donde podrás ver si tu aplicación se ha creado adecuadamente.
4. Luego, ejecuta `minikube service my-nginx-service` para lanzar tu aplicación en un navegador web y comenzar a usarla.

El funcionamiento es exactamente igual que en el caso anterior.

Para eliminar tu aplicación, ejecuta `helm uninstall my-release`, donde `my-release` es el nombre que le hayas dado a la aplicación.

## Parámetros de Configuración

Puedes personalizar la instalación modificando el archivo `values.yaml`. Aquí hay algunos parámetros que puedes ajustar:

- `replicaCount`: Número de réplicas de la aplicación.
- `image.repository`: Repositorio de la imagen de la aplicación.
- `image.tag`: Etiqueta de la imagen de la aplicación.
- `service.type`: Tipo de servicio para exponer la aplicación.
- `ingress.enabled`: Habilitar o deshabilitar el Ingress.
- `autoscaling.enabled`: Habilitar o deshabilitar el autoescalado de la aplicación.
- Otros parámetros para recursos, sonda de disponibilidad, etc.