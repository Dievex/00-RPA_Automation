<!-- NAV: adapta los paths según la profundidad del archivo (../../) -->

<div align="center">

<table><tr>
<td><a href="../../README.md">🏠 Inicio</a></td>
<td><b>·</b></td>
<td><a href="../../01-inicio/README.md"
   style="background:#dbeafe;padding:4px 10px;border-radius:12px;color:#1d4ed8;font-weight:bold;text-decoration:none">
   📋 01 · Inicio</a></td>
<td><b>·</b></td>
<td><a href="../../02-elaboracion/README.md"
   style="padding:4px 10px;border-radius:12px;color:#57606a;text-decoration:none">
   🔬 02 · Elaboración</a></td>
<td><b>·</b></td>
<td><a href="../../03-construccion/README.md"
   style="padding:4px 10px;border-radius:12px;color:#57606a;text-decoration:none">
   🔨 03 · Construcción</a></td>
<td><b>·</b></td>
<td><a href="../../04-transicion/README.md"
   style="padding:4px 10px;border-radius:12px;color:#57606a;text-decoration:none">
   🚀 04 · Transición</a></td>
</tr></table>

<details>
<summary>📋 Ver todas las secciones del repositorio</summary>

<br />

<table>
<tr><th>📋 01 · Inicio</th><th>🔬 02 · Elaboración</th><th>🔨 03 · Construcción</th><th>🚀 04 · Transición</th></tr>
<tr>
<td valign="top">

[📌 Visión y Justificación](../../01-inicio/vision-justificacion/README.md)
[🧩 Modelo del Dominio](../../01-inicio/modelo-dominio/README.md)
[👥 Actores y CU alto nivel](../../01-inicio/casos-de-uso-alto-nivel/README.md)
[⚠️ Análisis de Riesgos](../../01-inicio/analisis-riesgos/README.md)
[📖 Glosario](../../01-inicio/glosario/README.md)

</td>
<td valign="top">

[🏗️ Arquitectura del Sistema](../../02-elaboracion/arquitectura/README.md)
[🔄 Diagramas de Estado](../../02-elaboracion/diagramas-estado/README.md)
[📝 Casos de Uso Detallados](../../02-elaboracion/casos-de-uso-detallados/README.md)
[⚖️ Priorización de CU](../../02-elaboracion/priorizacion-cu/README.md)
[📋 Requisitos RF/RNF](../../02-elaboracion/requisitos/README.md)

</td>
<td valign="top">

[🎨 Diseño por Caso de Uso](../../03-construccion/diseno-por-caso-de-uso/README.md)
[📦 Análisis de Paquetes](../../03-construccion/analisis-paquetes/README.md)
[🗄️ Base de Datos](../../03-construccion/base-de-datos/README.md)
[🤖 Robot UiPath](../../03-construccion/robot-uipath/README.md)
[💻 Descripción Solución](../../03-construccion/descripcion-solucion/README.md)
[⚙️ Instalación](../../03-construccion/instalacion/README.md)

</td>
<td valign="top">

[🧪 Plan de Pruebas](../../04-transicion/plan-pruebas/README.md)
[🖥️ CU en Interfaz](../../04-transicion/cu-en-interfaz/README.md)
[📊 Resultados y Métricas](../../04-transicion/resultados-metricas/README.md)
[🎓 Conclusiones](../../04-transicion/conclusiones/README.md)

</td>
</tr>
</table>

</details>

<sub>📍 Estás en: <b>Modelo del Dominio</b></sub>

</div>

***

# 🧩 Modelo del Dominio

El modelo del dominio identifica las entidades fundamentales que participan en el proceso de automatización y sus responsabilidades dentro del sistema.

## Escenario (Diagrama de Clases)

![Modelo de clases](./diagramas/clases.svg)

*Diagrama de clases del modelo del dominio.*

## Entidades Principales

| Entidad           | Atributos Clave                           | Descripción                                                        |
| ----------------- | ----------------------------------------- | ------------------------------------------------------------------ |
| **Operario**      | nombre, turno                             | Usuario final que introduce los datos en la interfaz web.          |
| **InterfazWeb**   | url                                       | Punto de entrada del sistema para los usuarios humanos.            |
| **PuestoTrabajo** | nombre, usuarioSAP                        | Determina las credenciales de acceso a SAP y la impresora destino. |
| **RobotRPA**      | estado, ultimoCambioPassword              | Proceso automatizado encargado de la interacción con SAP.          |
| **MES**           | sistema (Apriso)                          | Sistema externo de gestión de producción en planta.                |
| **SAP**           | módulo, transacción                       | ERP corporativo donde se declaran las Galias.                      |
| **Impresora**     | nombre, ubicación                         | Dispositivo físico vinculado a cada Puesto de Trabajo.             |
| **Galia**         | numeroOrden, referencia, cantidad, estado | Documento de trazabilidad objeto de la automatización.             |

## Escenario de Ejemplo (Diagrama de Objetos)

![Modelo de Objetos](./diagramas/objetos.svg)

*Escenario concreto de ejecución del sistema.*

### Descripción del Flujo:

1. El operario `jGarcia` accede desde el `puestoSoldadura`.
2. Al pulsar **Guardar**, la información se persiste en la BD y se guarda en el sistema **MES**.
3. Al pulsar **Enviar a SAP**, se activa el `robotRPA`.
4. El robot recupera las credenciales asociadas al `puestoSoldadura`, se loguea en **SAP** y procesa los registros.
5. Finalmente, SAP envía los documentos `galia1` y `galia2` a la `impresoraZebra` asignada a dicho puesto.

## Decisiones de Diseño

- La entidad **Puesto de Trabajo** es el nexo de unión crítico: vincula al operario con el usuario de SAP y la impresora física, permitiendo que el robot sea agnóstico a la ubicación hasta el momento de la ejecución.
- El **Estado de la Galia** (0=sin procesar, 1=completada, 2=error) permite la trazabilidad completa del proceso y la gestión de reintentos.

