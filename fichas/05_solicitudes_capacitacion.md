# Ficha de propuesta - Solicitudes de capacitación con aprobación

Prototipo con datos ficticios, construido en un laboratorio personal. Se presenta como demostración de lo que se puede construir, para contrastar con la realidad del área.

**Nombre de la propuesta**
Solicitudes de capacitación con aprobación del jefe por Teams.

**Restricción actual**
Las solicitudes de capacitación llegan por correo o en conversaciones. No hay un estado claro (pendiente, aprobada, rechazada), el área de formación no sabe qué está pendiente y las solicitudes urgentes se pierden.

**Usuarios**
- Colaboradores: crean y consultan sus solicitudes.
- Jefes: aprueban o rechazan desde Teams.
- Equipo de formación: gestiona las aprobadas.

**Solución (MVP)**
- App para tableta o escritorio: lista de solicitudes con buscador, filtro por estado y etiquetas de color; detalle y formulario de nueva solicitud con curso, prioridad, fecha requerida, costo y justificación.
- Flujo de aprobación: el jefe recibe la solicitud en Teams (con aviso inmediato si la prioridad es Alta), aprueba o rechaza, y el estado se actualiza solo.
- Cancelación de una solicitud por parte del colaborador.

**Herramientas**
Power Apps (lienzo), SharePoint (listas), Power Automate (aprobaciones) y Microsoft Teams. Todo con licencias estándar de Microsoft 365.

**Beneficio esperado**
- Estado visible para todos, sin perseguir correos.
- Aprobaciones en minutos desde Teams.
- Historial para planear el presupuesto de formación.

**Indicadores para medirlo**
| Indicador | Cómo se calcula |
|---|---|
| Tiempo de aprobación | Promedio de horas entre la creación y la decisión del jefe |
| Solicitudes pendientes | Solicitudes en estado "Pendiente jefe" o "Pendiente formación" |
| Tasa de aprobación | Aprobadas / total de decididas x 100 |

**Licencias**
Estándar: incluida en Microsoft 365 (SharePoint, Power Apps para Microsoft 365, Power Automate estándar y Teams). Es la opción de menor costo para escalar.

**Gobernanza**
Solución propia para la app y el flujo (las listas de SharePoint se despliegan aparte); permisos del sitio por rol; cuenta de servicio para el flujo.

**Alcance y esfuerzo**
- **Prototipo funcional:** listas con integridad referencial, app de tres pantallas con búsqueda delegable y etiquetas de estado, y flujo de aprobación probado de punta a punta (aprobada y rechazada).
- **Camino a producción (estimado, 3 a 4 semanas):** levantamiento con formación y jefes, catálogo real de cursos, segundo nivel de aprobación si aplica, permisos del sitio por rol, cuenta de servicio, despliegue de la solución, piloto con un área, capacitación y medición de indicadores.

**Siguiente fase**
- Segundo nivel de aprobación (formación) y control de presupuesto por área.
- Tablero en Power BI con horas de formación por área.
- Migrar a Dataverse si se requiere seguridad por registro.

**Riesgos y supuestos**
- Un solo aprobador (el jefe inmediato) en el MVP.
- El límite de delegación de SharePoint obliga a filtros delegables cuando crezcan las solicitudes.
