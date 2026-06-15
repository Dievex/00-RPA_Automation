# CU: Registrar Declaración

| Campo | Descripción |
| :--- | :--- |
| **Actor principal** | Operario |
| **Precondición** | El operario tiene acceso a la Interfaz Web y hay puestos activos en el MES. |
| **Postcondición** | Puesto, referencia, orden y cantidad listos para guardar. |

## Diagrama de Secuencia
![Registrar declaración](./CU_RegistrarDeclaracion.svg)

## Flujo Principal
1. El operario accede a la Interfaz Web.
2. El sistema consulta al MES y muestra los puestos disponibles.
3. El operario selecciona su puesto.
4. El sistema filtra y muestra las referencias con órdenes abiertas en ese puesto.
5. El operario selecciona la orden.
6. El sistema muestra las referencias para esa orden.
7. El operario selecciona la referencia.
8. El sistema muestra la cantidad producida anteriormente.
9. El operario introduce la cantidad a declarar.

---
[⬅️ Volver a Casos de Uso Detallados](./README.md)
