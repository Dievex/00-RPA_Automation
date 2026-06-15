# CU: Procesar Declaración

| Campo | Descripción |
| :--- | :--- |
| **Actor principal** | RobotRPA |
| **Precondición** | Petición recibida por el servidor; registros con estado = 0 en BD. |
| **Postcondición** | Todos los registros procesados con estado = 1 o estado = 2; galias enviadas a imprimir. |

## Diagrama de Secuencia
![Procesar declaraciones](./CU5_ProcesarDeclaraciones.svg)

## Flujo Principal
1. El RobotRPA es activado por el servidor.
2. El robot verifica los días transcurridos desde el último cambio de contraseña.
3. El robot se loguea en SAP con el usuario correspondiente al puesto de trabajo.
4. El robot escribe la transacción en el buscador de SAP y la ejecuta.
5. El robot lee el primer registro con estado = 0 de la BD.
6. El robot completa los campos en SAP: referencia, orden y cantidad.
7. SAP procesa la declaración y envía la galia a imprimir.
8. El robot actualiza el registro en BD a estado = 1.
9. El robot repite hasta agotar todos los registros pendientes.

---
[⬅️ Volver a Casos de Uso Detallados](./README.md)
