# Guía de Containerlab

Material de referencia para instalar, configurar y utilizar **Containerlab** en entornos Linux, con prácticas de redes basadas en contenedores y apoyo de TopoViewer.

## Objetivos

- Comprender qué es Containerlab y cómo funciona.
- Instalar y utilizar Containerlab en Debian 13.
- Desplegar topologías de red mediante archivos YAML.
- Ejecutar pruebas de conectividad entre nodos.
- Visualizar y gestionar laboratorios mediante TopoViewer.
- Incorporar prácticas de networking y telecomunicaciones.
- Versionar y compartir configuraciones y documentación con GitHub.

## Contenido del repositorio

| Directorio o archivo | Descripción |
|---|---|
| `docs/` | Guía HTML y documentación técnica. |
| `labs/` | Topologías reproducibles y sus instrucciones. |
| `images/` | Capturas de pantalla y diagramas. |
| `.gitignore` | Archivos locales excluidos del repositorio. |
| `LICENSE` | Licencia del material, una vez definida. |

## Requisitos

- Un equipo Linux; la guía toma como referencia Debian 13.
- Docker instalado y operativo.
- Containerlab instalado.
- Acceso a las imágenes de contenedor utilizadas por cada laboratorio.
- TopoViewer, cuando se quiera utilizar la interfaz web.

Los requisitos concretos pueden variar según la topología y las imágenes utilizadas.

## Guía principal

Abrí [`docs/guia-containerlab.html`](docs/guia-containerlab.html) para consultar la guía en formato HTML.

La documentación complementaria se encuentra en [`docs/`](docs/), y las prácticas están organizadas en [`labs/`](labs/).

## Primera práctica: dos PCs

La topología inicial conecta dos nodos Linux mediante un enlace virtual.

Archivo: [`labs/dos-pcs/dos-pcs.clab.yml`](labs/dos-pcs/dos-pcs.clab.yml)

Desde un equipo que tenga Containerlab y Docker instalados, ejecutá:

```bash
sudo containerlab deploy --topo labs/dos-pcs/dos-pcs.clab.yml
sudo containerlab inspect --topo labs/dos-pcs/dos-pcs.clab.yml
```

Para eliminar el laboratorio:

```bash
sudo containerlab destroy --topo labs/dos-pcs/dos-pcs.clab.yml
```

Consultá el README de la práctica para ver cómo verificar las interfaces y probar la conectividad.

## Versionado y contribuciones

Las topologías y la documentación se mantienen en GitHub para registrar los cambios, compartir las prácticas y facilitar su reutilización en actividades docentes.

Antes de publicar, verificá que el repositorio no incluya contraseñas, tokens, capturas de tráfico con información sensible ni datos personales.

## Referencias

- [Containerlab — documentación oficial](https://containerlab.dev/)
- [Containerlab — repositorio oficial](https://github.com/srl-labs/containerlab)
- [TopoViewer — documentación y código del proyecto utilizado](https://github.com/srl-labs/containerlab)

**Nota:** la instalación y configuración de TopoViewer deben documentarse según la implementación concreta utilizada en el laboratorio. No se deben asumir comandos de administración de usuarios de otras interfaces.
