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
   style="background:#dbeafe;padding:4px 10px;border-radius:12px;color:#1d4ed8;font-weight:bold;text-decoration:none">
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

<sub>📍 Estás en: <b>Priorización de CU</b></sub>

</div>

***

# ⚖️ Priorización de Casos de Uso

La priorización de los casos de uso se ha realizado evaluando tres dimensiones críticas para el éxito del proyecto.

## Criterios de Evaluación (1-3)

1. **Riesgo Arquitectónico:** ¿Involucra partes críticas o desconocidas de la arquitectura (especialmente RPA)?
2. **Valor de Negocio:** ¿Cuál es el impacto en la reducción de tiempo y errores?
3. **Frecuencia de Uso:** ¿Cuántas veces al día se ejecuta este caso de uso?

## Resultado de la Priorización

| CU       | Nombre                       | Riesgo | Valor | Frecuencia | Total | Prioridad |
| -------- | ---------------------------- | ------ | ----- | ---------- | ----- | --------- |
| **CU1**  | Registrar declaración        | 3      | 3     | 3          | **9** | Alta      |
| **CU2**  | Guardar registro             | 3      | 3     | 3          | **9** | Alta      |
| **CU3**  | Enviar a SAP                 | 3      | 3     | 3          | **9** | Alta      |
| **CU4**  | Loguearse en SAP             | 3      | 3     | 3          | **9** | Alta      |
| **CU5**  | Procesar declaraciones       | 3      | 3     | 3          | **9** | Alta      |
| **CU6**  | Iniciar sesión               | 3      | 3     | 3          | **9** | Alta      |
| **CU7**  | Cambio automático contraseña | 3      | 2     | 1          | **6** | Media     |
| **CU8**  | Imprimir Galia               | 1      | 3     | 3          | **7** | Media     |
| **CU9**  | Consultar log propio         | 1      | 3     | 3          | **7** | Media     |
| **CU10** | Consultar log completo       | 1      | 3     | 2          | **6** | Media     |
| **CU11** | Actualizar registro          | 1      | 2     | 2          | **5** | Media     |
| **CU12** | Crear usuario                | 1      | 2     | 1          | **4** | Baja      |
| **CU13** | Consultar usuarios           | 1      | 2     | 1          | **4** | Baja      |
| **CU14** | Actualizar usuario           | 1      | 2     | 1          | **4** | Baja      |
| **CU15** | Eliminar usuario             | 1      | 1     | 1          | **3** | Baja      |
| **CU16** | Eliminar registro            | 1      | 1     | 1          | **3** | Baja      |
| **CU17** | Desbloquear cuenta SAP       | 1      | 1     | 1          | **3** | Baja      |

*Nota: El detalle completo de los CU principales se encuentra en la sección de* *[Casos de Uso Detallados](../casos-de-uso-detallados/README.md).*
