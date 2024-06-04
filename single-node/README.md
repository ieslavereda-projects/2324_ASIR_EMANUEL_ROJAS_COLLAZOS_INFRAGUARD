# Implemente Wazuh Docker en una configuración de un solo nodo

Esta implementación se define en el archivo `docker-compose.yml` con un contenedor de administrador de Wazuh, un contenedor de indexador de Wazuh y un contenedor de panel de Wazuh. Se puede implementar siguiendo estos pasos:

1) Aumente max_map_count en su host (Linux). Este comando debe ejecutarse con permisos de root:
```
$ sysctl -w vm.max_map_count=262144
```
2) Ejecute el script de creación del certificado:
```
$ docker-compose -f generate-indexer-certs.yml run --rm generator
```
3) Inicie el entorno con Docker-compose:

- En primer plano:
```
$ docker-compose up
```
- En segundo Plano:
```
$ docker-compose up -d
```
- Para parar la ejecucion:
```
$ docker-compose down
```

El entorno tarda aproximadamente 1 minuto en activarse (dependiendo de su host Docker) por primera vez, ya que se debe iniciar Wazuh Indexer por primera vez y se deben generar los índices y patrones de índice.
