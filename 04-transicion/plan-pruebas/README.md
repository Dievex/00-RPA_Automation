<!-- NAV: adapta los paths según la profundidad del archivo (../../) -->

<div align="center">

<table><tr>
<td><a href="../../README.md">🏠 Inicio</a></td>
<td><b>·</b></td>
<td><a href="../../01-inicio/README.md"
   style="padding:4px 10px;border-radius:12px;color:#57606a;text-decoration:none">
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
   style="background:#dbeafe;padding:4px 10px;border-radius:12px;color:#1d4ed8;font-weight:bold;text-decoration:none">
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

<sub>📍 Estás en: <b>Plan de Pruebas</b></sub>

</div>

***

# 🧪 Plan de Pruebas

El sistema ha sido sometido a un riguroso proceso de validación para asegurar el cumplimiento de los requisitos y la robustez de la automatización.

## Tipos de Pruebas Realizadas

1. **Pruebas Unitarias:** Validación de los controladores de Node.js y las funciones de validación de datos en el frontend.
2. **Pruebas de Integración:** Verificación de la comunicación entre la API web, la base de datos SQL Server y el robot UiPath.
3. **Pruebas de Automatización (RPA):** Pruebas de estrés sobre la SAP GUI para asegurar que el robot gestiona correctamente tiempos de espera y errores de red.
4. **Pruebas de Usuario (UAT):** Sesiones con operarios reales de Maflow para validar la usabilidad de la interfaz web.

## Casos de Prueba Críticos

| ID        | Descripción                     | Resultado Esperado                             | Estado |
| --------- | ------------------------------- | ---------------------------------------------- | ------ |
| **TP-01** | Registro de Galia válida        | Datos en BD + Declaración en MES               | ✅      |
| **TP-02** | Procesamiento en lote (20 docs) | Robot completa los 20 sin intervención         | ✅      |
| **TP-03** | Error en SAP (Orden cerrada)    | Registro marcado como estado 2, robot continúa | ✅      |
| **TP-04** | Cambio de password autónomo     | Robot renueva credenciales antes de loguearse  | ✅      |

## Entorno de Pruebas

Las pruebas se realizaron en un entorno simulado que replica exactamente la configuración de red y las versiones de software (SAP GUI, Windows Server) de la planta de Maflow Spain Automotive.
