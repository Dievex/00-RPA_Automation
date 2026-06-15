# CU: Cambio de Contraseña Automático

| Campo | Descripción |
| :--- | :--- |
| **Actor principal** | RobotRPA |
| **Precondición** | Han transcurrido ≥ 28 días desde el último cambio de contraseña. |
| **Postcondición** | Contraseña renovada en SAP y contador de días reiniciado a 0. |

## Diagrama de Secuencia
![Cambiar contraseña](./CU7_CambiarContrasena.svg)

## Flujo Principal
1. El robot detecta que han pasado ≥ 28 días desde el último cambio.
2. El robot accede a la pantalla de cambio de contraseña de SAP.
3. El robot introduce la contraseña actual.
4. El robot genera y escribe la nueva contraseña siguiendo la política de SAP.
5. El robot confirma la nueva contraseña.
6. SAP valida y acepta el cambio.
7. El robot actualiza el registro de fecha del último cambio.

---
[⬅️ Volver a Casos de Uso Detallados](./README.md)
