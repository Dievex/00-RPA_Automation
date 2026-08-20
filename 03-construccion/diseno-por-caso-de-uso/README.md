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
   style="background:#dbeafe;padding:4px 10px;border-radius:12px;color:#1d4ed8;font-weight:bold;text-decoration:none">
   🔨 03 · Construcción</a></td>
<td><b>·</b></td>
<td><a href="../../04-transicion/README.md"
   style="padding:4px 10px;border-radius:12px;color:#57606a;text-decoration:none">
   🚀 04 · Transición</a></td>
</tr></table>

<details>
<summary>📋 Ver todas las secciones del repositorio</summary>

<br>

<table>
<tr><th>📋 01 · Inicio</th><th>🔬 02 · Elaboración</th><th>🔨 03 · Construcción</th><th>🚀 04 · Transición</th></tr>
<tr>
<td valign="top">

[📌 Visión y Justificación](../../01-inicio/vision-justificacion/README.md)<br>
[🧩 Modelo del Dominio](../../01-inicio/modelo-dominio/README.md)<br>
[👥 Actores y CU alto nivel](../../01-inicio/casos-de-uso-alto-nivel/README.md)<br>
[⚠️ Análisis de Riesgos](../../01-inicio/analisis-riesgos/README.md)<br>
[📖 Glosario](../../01-inicio/glosario/README.md)

</td>
<td valign="top">

[🏗️ Arquitectura del Sistema](../../02-elaboracion/arquitectura/README.md)<br>
[🔄 Diagramas de Estado](../../02-elaboracion/diagramas-estado/README.md)<br>
[📝 Casos de Uso Detallados](../../02-elaboracion/casos-de-uso-detallados/README.md)<br>
[⚖️ Priorización de CU](../../02-elaboracion/priorizacion-cu/README.md)<br>
[📋 Requisitos RF/RNF](../../02-elaboracion/requisitos/README.md)

</td>
<td valign="top">

[🎨 Diseño por Caso de Uso](../../03-construccion/diseno-por-caso-de-uso/README.md)<br>
[📦 Análisis de Paquetes](../../03-construccion/analisis-paquetes/README.md)<br>
[🗄️ Base de Datos](../../03-construccion/base-de-datos/README.md)<br>
[🤖 Robot UiPath](../../03-construccion/robot-uipath/README.md)<br>
[💻 Descripción Solución](../../03-construccion/descripcion-solucion/README.md)<br>
[⚙️ Instalación](../../03-construccion/instalacion/README.md)

</td>
<td valign="top">

[🧪 Plan de Pruebas](../../04-transicion/plan-pruebas/README.md)<br>
[🖥️ CU en Interfaz](../../04-transicion/cu-en-interfaz/README.md)<br>
[📊 Resultados y Métricas](../../04-transicion/resultados-metricas/README.md)<br>
[🎓 Conclusiones](../../04-transicion/conclusiones/README.md)

</td>
</tr>
</table>

</details>

<sub>📍 Estás en: <b>Diseño por Caso de Uso</b></sub>

</div>

***

# 🎨 Diseño por Caso de Uso

Para asegurar una implementación robusta, cada caso de uso prioritario (CU1-CU9) cuenta con un diseño detallado siguiendo el patrón MVC.

## Artefactos de Diseño
Para cada caso de uso se han generado:
1.  **Diagrama de Clases de Diseño:** Mapeo de las clases de la vista, el controlador y el modelo involucradas.
2.  **Diagrama de Secuencia:** Modelado de la interacción temporal entre los objetos del sistema.
3.  **Mockup / Pantalla Real:** Representación visual de la interfaz final.

## CU Iniciar Sesion
![Clase diseño CU Iniciar Sesion](./diagramas/CU-IniciarSesion.svg)

*Diagrama de clases para el inicio de sesión.*

![Secuencia CU Iniciar Sesion](./diagramas/IniciarSesion.svg)

*Diagrama de secuencia para el inicio de sesión.*

## CU Cambiar Contraseña Automáticamente
![Clase diseño CU Cambiar Contraseña Automáticamente](./diagramas/CU-CambiarContraseñaAutomaticamente.svg)

*Diagrama de clases para el cambio de contraseña automático.*

![Secuencia CU Cambiar Contraseña Automáticamente](./diagramas/CambiarContraseñaAutomaticamente.svg)

*Diagrama de secuencia para el cambio de contraseña automático.*

## CU Consultar Log
![Clase diseño CU Consultar Log](./diagramas/CU-ConsultarLog.svg)

*Diagrama de clases para la consulta de logs.*

![Secuencia CU Consultar Log](./diagramas/ConsultarLog.svg)

*Diagrama de secuencia para la consulta de logs.*

## CU Enviar ASAP
![Clase diseño CU Enviar ASAP](./diagramas/CU-EnviarASAP.svg)

*Diagrama de clases para el envío a ASAP.*

![Secuencia CU Enviar ASAP](./diagramas/EnviarASAP.svg)

*Diagrama de secuencia para el envío a ASAP.*

## CU Gestionar Usuarios
![Clase diseño CU Gestionar Usuarios](./diagramas/CU-GestionarUsuarios.svg)

*Diagrama de clases para la gestión de usuarios.*

![Secuencia CU Gestionar Usuarios](./diagramas/GestionarUsuarios.svg)

*Diagrama de secuencia para la gestión de usuarios.*

## CU Guardar Registro
![Clase diseño CU Guardar Registro](./diagramas/CU-GuardarRegistro.svg)

*Diagrama de clases para el guardado de registros.*

![Secuencia CU Guardar Registro](./diagramas/GuardarRegistro.svg)

*Diagrama de secuencia para el guardado de registros.*

## CU Imprimir Galia
![Clase diseño CU Imprimir Galia](./diagramas/CU-ImprimirGalia.svg)

*Diagrama de clases para la impresión en Galia.*

![Secuencia CU Imprimir Galia](./diagramas/ImprimirGalia.svg)

*Diagrama de secuencia para la impresión en Galia.*

## CU Procesar Declaraciones
![Clase diseño CU Procesar Declaraciones](./diagramas/CU-ProcesarDeclaraciones.svg)

*Diagrama de clases para el procesamiento de declaraciones.*

![Secuencia CU Procesar Declaraciones](./diagramas/ProcesarDeclaraciones.svg)

*Diagrama de secuencia para el procesamiento de declaraciones.*

## CU Registrar Declaracion
![Clase diseño CU Registrar Declaracion](./diagramas/CU-RegistrarDeclaracion.svg)

*Diagrama de clases para el registro de declaraciones.*

![Secuencia CU Registrar Declaracion](./diagramas/RegistrarDeclaracion.svg)

*Diagrama de secuencia para el registro de declaraciones.*



## Relaciones
- Estos diseños concretan la [Arquitectura](../../02-elaboracion/arquitectura/README.md) definida en la fase anterior.
- Los flujos de secuencia alimentan la lógica implementada en el [Robot UiPath](../robot-uipath/README.md).
