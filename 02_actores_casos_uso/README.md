# 02 · Actores y Casos de Uso

En esta sección se identifican los actores que interactúan con el sistema y las funcionalidades principales agrupadas a alto nivel.

## Actores del Sistema

| Actor | Tipo | Descripción |
| :--- | :--- | :--- |
| **Operario** | Principal | Introduce datos de producción y activa el proceso de envío a SAP. |
| **Responsable** | Principal | Supervisa los logs de ejecución y gestiona registros existentes. |
| **Administrador** | Principal | Gestiona los usuarios del sistema y la configuración global. |
| **Robot RPA** | Sistema | Ejecuta de forma autónoma las tareas en la interfaz de SAP. |
| **SAP / MES** | Externo | Sistemas con los que se integra la solución. |

### Relaciones entre Actores
![Relaciones Actores](./Actores_Relaciones.svg)

## Diagramas de Casos de Uso (Alto Nivel)

### Casos de Uso: Operario
![Casos de Uso Operario](./Actor_Operario.svg)

### Casos de Uso: Responsable
![Casos de Uso Responsable](./Actor_Responsable.svg)

### Casos de Uso: Administrador
![Casos de Uso Administrador](./Actor_Administrador.svg)

### Casos de Uso: Robot RPA
![Casos de Uso Robot RPA](./Actor_RobotRPA.svg)

---

<div align="center">

| ← Anterior | Inicio | Siguiente → |
|:---:|:---:|:---:|
| [01 · Presentación](../01_presentacion/README.md) | [🏠 Inicio](../README.md) | [03 · Requisitos RNF](../03_requisitos_rnf/README.md) |

</div>
