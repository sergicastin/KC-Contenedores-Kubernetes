# Proyecto Kubernetes

Este proyecto consta de 7 archivos en total: dos deployments para las imágenes, sus dos servicios correspondientes, un secret, un configmap y un ingress. Sin embargo, el ingress no está funcionando completamente, aunque está estructurado correctamente. La contraseña de la base de datos está codificada en base64 en el archivo secret.yaml, mientras que el nombre de la base de datos se encuentra en el archivo configmap.yaml.

## Instrucciones

Para ejecutar esta aplicación, sigue estos pasos:

1. Descarga el repositorio desde GitHub.
2. Desde una terminal y con Minikube iniciado, navega al directorio descargado.
3. Una vez dentro del directorio, ejecuta `kubectl apply -f .`.
4. Una vez completado, ejecuta `minikube service my-nginx-service`.
5. Esto abrirá automáticamente el navegador web y cargará la aplicación, que estará lista para su uso.

El funcionamiento de la aplicación implica un formulario que simula la entrega de prácticas. Cuando se completan los 3 campos de entrada y se selecciona una opción, al hacer clic en "Agregar Práctica", se añade una entrada a una tabla ubicada debajo con todos los registros de la base de datos, junto con un botón para eliminar cada entrada individualmente.

Para eliminar todos los recursos creados, ejecuta `kubectl delete -f .`.
