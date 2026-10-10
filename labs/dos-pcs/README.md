# Laboratorio: dos PCs conectadas

## Objetivo

Desplegar dos nodos Linux conectados por un enlace virtual mediante Containerlab.

## Despliegue

Desde la raíz del repositorio:

```bash
sudo containerlab deploy --topo labs/dos-pcs/dos-pcs.clab.yml
```

Verificar el estado:

```bash
sudo containerlab inspect --topo labs/dos-pcs/dos-pcs.clab.yml
```

## Verificación de interfaces

Inspeccionar las interfaces de cada contenedor:

```bash
docker exec -it clab-dos-pcs-pcA ip -br addr
docker exec -it clab-dos-pcs-pcB ip -br addr
```

Asignar direcciones IP a `eth1` en ambos nodos:

```bash
docker exec clab-dos-pcs-pcA ip addr add 10.0.0.1/24 dev eth1
docker exec clab-dos-pcs-pcB ip addr add 10.0.0.2/24 dev eth1
docker exec clab-dos-pcs-pcA ip link set eth1 up
docker exec clab-dos-pcs-pcB ip link set eth1 up
```

Probar conectividad:

```bash
docker exec clab-dos-pcs-pcA ping -c 4 10.0.0.2
```

## Limpieza

```bash
sudo containerlab destroy --topo labs/dos-pcs/dos-pcs.clab.yml
```

Las direcciones configuradas manualmente son temporales y se pierden al eliminar y recrear los contenedores.
