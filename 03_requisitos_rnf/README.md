# 03 · Requisitos No Funcionales (RNF)

Los requisitos no funcionales garantizan la calidad, seguridad y rendimiento del sistema, asegurando que la automatización sea fiable en el entorno crítico de la planta.

## Principales RNF del Sistema

### Rendimiento

- **RNF-01:** El robot debe procesar cada registro en SAP en un tiempo máximo de 15 segundos por Galia.
- **RNF-03:** El sistema debe soportar el procesamiento de al menos 20 Galias en una misma ejecución de lote.

### Disponibilidad

- **RNF-04:** El servidor de aplicaciones debe estar operativo 24/7 durante todos los turnos de producción.
- **RNF-06:** Ante un fallo en un registro concreto, el sistema NO debe interrumpir el procesamiento del resto del lote.

### Seguridad

- **RNF-07:** El cambio automático de contraseña debe ejecutarse cada 28 días para cumplir con la política de SAP.
- **RNF-08:** El robot no debe realizar más de 2 intentos de login fallidos para evitar el bloqueo de la cuenta.

### Mantenibilidad

- **RNF-10:** Los estados de los registros (0=pendiente, 1=éxito, 2=error) deben persistirse en la BD.
- **RNF-11:** El sistema debe registrar logs detallados de cada ejecución del robot.

### Plataforma

- **RNF-12:** Interfaz web desarrollada con React y Node.js/Express.
- **RNF-15:** Base de datos Microsoft SQL Server compartida con el MES Apriso.

***

<div align="center">

|                            ← Anterior                            |           Inicio          |                          Siguiente →                          |
| :--------------------------------------------------------------: | :-----------------------: | :-----------------------------------------------------------: |
| [02 · Actores y Casos de Uso](../02_actores_casos_uso/README.md) | [🏠 Inicio](../README.md) | [04 · Casos de Uso Detallados](../04_cu_detallados/README.md) |

</div>
