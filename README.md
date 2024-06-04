# 2324_ASIR_EMANUEL_ROJAS_COLLAZOS_INFRAGUARD

Este proyecto tiene como objetivo desarrollar e implementar una herramienta de monitorización de seguridad utilizando Wazuh y Docker. La solución está diseñada para ser desplegada en pequeñas y medianas empresas (pymes) y proporciona una manera eficiente de supervisar y solucionar errores relacionados con el uso de los equipos de la empresa, así como gestionar actualizaciones e instalaciones de software.

## Tabla de Contenidos

- [Descripción](#descripción)
- [Arquitectura](#arquitectura)
- [Requisitos](#requisitos)
- [Deploys o Scrips](#Deploys_o_Scrips)

## Descripción

Este proyecto implementa una solución de monitorización de seguridad utilizando Wazuh desplegado con Docker. La arquitectura incluye contenedores de Docker que ejecutan diferentes servicios de Wazuh (indexer, dashboard, management) y otros contenedores que actúan como hosts y router.

## Arquitectura

La arquitectura del proyecto se compone de seis contenedores Docker:
- Tres contenedores para Wazuh desplegados con Docker-Compose (indexer, dashboard, management).
- Tres contenedores ejecutando imágenes de Ubuntu mediante Docker RUN:
  - Dos contenedores actuando como hosts en diferentes redes (interna y DMZ).
  - Un contenedor actuando como router con tres interfaces de red (WAN, interna, DMZ).

La siguiente figura ilustra la arquitectura de la red:
Wazuh Indexer] -- Docker-Compose
[Wazuh Dashboard] -- Docker-Compose
[Wazuh Management] -- Docker-Compose

[Host Interna] -- Docker RUN
[Host DMZ] -- Docker RUN
[Router] -- Docker RUN (con 3 interfaces de red)


## Requisitos

- Docker y Docker-Compose instalados.
- Sistema operativo Linux (preferiblemente Ubuntu).
- Conexión a Internet para descargar las imágenes de Docker y actualizaciones.

## Deploys o Scrips

-El script de iptables esta en la carpeta single-node se llama rc.local
-EL deploy del SIEM Wazuh esta en la ruta single-nodde se llama docker-compose

