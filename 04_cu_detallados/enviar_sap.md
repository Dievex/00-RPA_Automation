# CU: Enviar a SAP

| Campo | Descripción |
| :--- | :--- |
| **Actor principal** | Operario |
| **Precondición** | Al menos un registro guardado en BD con estado = 0. |
| **Postcondición** | Petición enviada al servidor y RobotRPA activado. |

## Diagrama de Secuencia
![Enviar a SAP](./CU3_EnviarASAP.svg)

## Flujo Principal
1. El operario pulsa el botón Enviar a SAP.
2. El sistema verifica que existen registros pendientes con estado = 0 en la BD.
3. El sistema lanza una petición al servidor de ejecución del RPA.
4. El servidor recibe la petición y confirma la recepción.
5. El servidor activa la ejecución del RobotRPA.
6. El sistema notifica al operario que el proceso ha sido lanzado correctamente.

---
[⬅️ Volver a Casos de Uso Detallados](./README.md)
