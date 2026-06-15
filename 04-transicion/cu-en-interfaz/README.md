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
[🖥️ CU Representativos en Código](../../04-transicion/cu-en-interfaz/README.md)<br>
[📊 Resultados y Métricas](../../04-transicion/resultados-metricas/README.md)<br>
[🎓 Conclusiones](../../04-transicion/conclusiones/README.md)

</td>
</tr>
</table>

</details>

<sub>📍 Estás en: <b>Casos de Uso Representativos en Código</b></sub>

</div>

***

# 💻 Casos de Uso Representativos en Código

En esta sección se muestra la implementación real de los casos de uso más críticos del sistema, tanto en la **aplicación web** (Node.js + React) como en el **robot RPA** (UiPath). El objetivo es evidenciar cómo los requisitos funcionales se traducen directamente en código fuente.

---

## CU Registrar Declaración — App (Node/Express)

La lógica de negocio del registro de declaraciones reside en el controlador Express. Se validan los datos recibidos, se persisten en la base de datos y se devuelve la respuesta al cliente React.


```javascript
exports.guardarDeclaracion = async (req, res) => {
  try {
    const { idPuesto, nombrePuesto, idOrden, numeroOrden, idReferencia, numeroReferencia, cantidad } = req.body;
    
    if (!idPuesto || !idOrden || !idReferencia || !cantidad || cantidad <= 0) {
      return res.status(400).json({ error: 'Faltan datos obligatorios o cantidad inválida' });
    }

    await Registro.guardar({
      idPuesto, nombrePuesto, idOrden, numeroOrden, idReferencia, numeroReferencia, cantidad
    });
      
    res.json({ message: 'Declaración guardada correctamente' });
  } catch (error) {
    console.error('Error guardarDeclaracion:', error);
    res.status(500).json({ error: 'Error al guardar declaración' });
  }
};
```
[declaracionController.js:L49-66](../../codigo/server/controllers/declaracionController.js#L49-L66)

```javascript
const handleGuardar = async (e) => {
  e.preventDefault();
  if (!idPuesto || !idOrden || !idReferencia || !cantidad || cantidad <= 0) {
    triggerNotification('Por favor completa todos los campos correctamente.', 'error');
    return;
  }

  setLoading(true);
  try {
    const puestoObj = puestos.find(p => p.id.toString() === idPuesto);
    const ordenObj = ordenes.find(o => o.id.toString() === idOrden);
    const refObj = referencias.find(r => r.id.toString() === idReferencia);

    await declaracionService.guardarDeclaracion({
      idPuesto: puestoObj.id,
      nombrePuesto: puestoObj.nombre,
      idOrden: ordenObj.id,
      numeroOrden: ordenObj.numero,
      idReferencia: refObj.id,
      numeroReferencia: refObj.numero,
      cantidad: parseInt(cantidad, 10)
    });

    triggerNotification('Declaración guardada exitosamente. ¡Paso 1 completado!', 'success');
    setIsSaved(true);
    cargarHistorial();
    
    const cantAnterior = await declaracionService.getCantidadAnterior(idOrden);
    setCantidadAnterior(cantAnterior);
    
  } catch {
    triggerNotification('Error al guardar la declaración.', 'error');
  } finally {
    setLoading(false);
  }
};
```
[DeclaracionForm.jsx:L109-144](../../codigo/client/src/views/declaracion/DeclaracionForm.jsx#L109-L144)

---

## CU Enviar a SAP
 
El sistema permite enviar una señal al robot RPA para que comience a procesar las declaraciones pendientes en SAP. Esto se realiza a través de un servicio en Node.js que ejecuta un script automatizado.

```javascript
static activarRobot() {
  const rpaPath = env.rpaBatPath;
  const dir = path.dirname(rpaPath);
  const file = path.basename(rpaPath);

  const cmd = `cd /d "${dir}" && "${file}"`;
  
  console.log(`--> Ejecutando archivo .bat del RPA con comando: ${cmd}`);

  exec(cmd, (error, stdout, stderr) => {
    if (error) {
      console.error(`Error al ejecutar el bat: ${error.message}`);
      return;
    }
    if (stderr) {
      console.error(`stderr: ${stderr}`);
    }
    console.log(`stdout: ${stdout}`);
  });
}
```
[rpaService.js:L6-25](../../codigo/server/services/rpaService.js#L6-L25)

```javascript
const handleEnviarSAP = async () => {
  setLoading(true);
  try {
    await declaracionService.enviarASap();
    triggerNotification('¡Señal enviada a SAP (Robot activado)!', 'success');
    
    // Reset de estados tras el envío
    setIdPuesto('');
    setIdOrden('');
    setIdReferencia('');
    setCantidad('');
    setCantidadAnterior(0);
    setOrdenes([]);
    setReferencias([]);
    setIsSaved(false);
    cargarHistorial();
  } catch {
    triggerNotification('Error al activar el robot.', 'error');
  } finally {
    setLoading(false);
  }
};
```

[DeclaracionForm.jsx:L146-166](../../codigo/client/src/views/declaracion/DeclaracionForm.jsx#L146-L166)

---

## CU Cambiar Contraseña — Robot RPA (UiPath)

El robot detecta la necesidad de renovar credenciales e inicia el flujo de cambio de contraseña en SAP de forma autónoma. Se muestran las actividades de lectura desde un almacén seguro y la escritura en la pantalla de SAP.

![Captura código CU7 — Lectura credenciales](./capturas/cu7-codigo-rpa-credenciales.png)
*Figura 18: Lectura segura de la nueva contraseña desde Windows Credential Manager o variable de entorno. 📌 Sube la captura como `cu7-codigo-rpa-credenciales.png`*

![Captura código CU7 — Actualización en SAP](./capturas/cu7-codigo-rpa-sap.png)
*Figura 19: Actividades UiPath para navegar y actualizar la contraseña en SAP. 📌 Sube la captura como `cu7-codigo-rpa-sap.png`*

---

## CU Procesar Declaraciones — Robot RPA (UiPath)

El robot lee el lote de Galias pendientes desde la base de datos y automatiza la entrada de datos en SAP GUI. A continuación se muestra el flujo principal del proceso y la actividad de escritura en SAP.

![Captura código CU5 — Flujo UiPath](./capturas/cu5-codigo-rpa-flujo.png)
*Figura 14: Diagrama de flujo principal del robot en UiPath Studio. 📌 Sube la captura del workflow como `cu5-codigo-rpa-flujo.png`*

![Captura código CU5 — Actividad SAP](./capturas/cu5-codigo-rpa-actividad.png)
*Figura 15: Detalle de la actividad de escritura en SAP GUI (Type Into / Send Keys). 📌 Sube la captura de la actividad como `cu5-codigo-rpa-actividad.png`*

---

## CU Consultar Log — App (Node/Express + React)

El endpoint de consulta de logs recupera todos los registros de ejecución y los expone al cliente. El componente React renderiza la tabla de resultados con su estado asociado y permite realizar filtrados dinámicos.

```javascript
exports.getLogs = async (req, res) => {
  try {
    const logs = await Registro.findAll();
    res.json(logs);
  } catch (error) {
    console.error('Error getLogs:', error);
    res.status(500).json({ error: 'Error al obtener logs' });
  }
};
```
[logController.js:L3-11](../../codigo/server/controllers/logController.js#L3-L11)

```javascript
<tbody className="divide-y divide-slate-100 dark:divide-slate-700/50 text-sm font-medium">
  {currentLogs.length > 0 ? (
    currentLogs.map((log, index) => (
      <tr key={index} className="hover:bg-slate-50/70 dark:hover:bg-slate-700/50 transition-all duration-150">
        <td className="py-3.5 px-6 whitespace-nowrap text-slate-500 dark:text-slate-400 text-xs">
          {new Date(log.DATE_TIME).toLocaleString('es-ES')}
        </td>
        <td className="py-3.5 px-6 whitespace-nowrap">
          <span className="text-slate-900 dark:text-slate-200 font-semibold">{log.PRODUCTION_LINE || '—'}</span>
        </td>
        <td className="py-3.5 px-6 whitespace-nowrap text-slate-600 dark:text-slate-300 font-mono text-xs">
          {log.ORDER_NUMBER}
        </td>
        <td className="py-3.5 px-6 whitespace-nowrap text-slate-600 dark:text-slate-300 font-mono text-xs">
          {log.REFERENCE}
        </td>
        <td className="py-3.5 px-6 whitespace-nowrap text-center text-slate-900 dark:text-slate-100 font-bold">
          {log.QUANTITY_MANUFACTURED}
        </td>
        <td className="py-3.5 px-6 whitespace-nowrap text-center">
          {getStatusBadge(log.SAP_STATUS)}
        </td>
      </tr>
    ))
  ) : (
    <tr>
      <td colSpan="7" className="text-center py-10 text-slate-400 font-medium">
        No se encontraron registros que coincidan con los filtros aplicados.
      </td>
    </tr>
  )}
</tbody>
```
[LogCompleto.jsx:L340-397](../../codigo/client/src/views/log/LogCompleto.jsx#L340-L397)

