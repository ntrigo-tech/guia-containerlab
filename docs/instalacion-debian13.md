# Instalación de Containerlab en Debian 13

## 1. Preparación del sistema

Actualizar los paquetes:

```bash
sudo apt update
sudo apt upgrade
```

## 2. Instalar Docker

Containerlab utiliza contenedores para ejecutar los nodos de una topología. Docker debe estar instalado y funcionando antes de desplegar un laboratorio.

Verificar Docker:

```bash
docker --version
sudo docker ps
```

## 3. Instalar Containerlab

Seguir las instrucciones vigentes de la documentación oficial:

https://containerlab.dev/install/

Verificar la instalación:

```bash
containerlab version
containerlab --help
```

## 4. Comprobar el entorno

Verificar que Docker funciona y que el equipo tiene acceso a las imágenes necesarias:

```bash
sudo docker info
```

## 5. Desplegar una topología

Desde la raíz de este repositorio, ejecutar las instrucciones de `labs/dos-pcs/README.md`.

## Referencia

Documentación oficial: https://containerlab.dev/
