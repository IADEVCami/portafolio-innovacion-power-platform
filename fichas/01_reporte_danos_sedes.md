# Ficha de propuesta - Reporte digital de daños en sedes

Prototipo con datos ficticios, construido en un laboratorio personal. Se presenta como demostración de lo que se puede construir, para contrastar con la realidad del área.

**Nombre de la propuesta**
Reporte de daños en sedes con aviso inmediato al técnico.

**Restricción actual**
Los supervisores reportan daños (baños, cocinas, aires acondicionados, luminarias) por WhatsApp. Los técnicos se enteran tarde, no hay trazabilidad por reporte y no se puede medir cuánto tarda cada reparación.

**Usuarios**
- Supervisores de sede: reportan desde el celular.
- Técnicos de mantenimiento: atienden sus reportes pendientes.
- Líder de facilities: consulta tiempos y volumen por sede.

**Solución (MVP)**
- App móvil para reportar: sede, ubicación, tipo de daño, prioridad, descripción y foto obligatoria.
- Cada reporte queda asignado a un técnico y recibe un número único (DAN-0001).
- El técnico ve solo sus pendientes, ordenados por urgencia, y cambia el estado: Reportado, En atención, Resuelto.
- Aviso inmediato por Teams al técnico cuando la prioridad es Alta.
- Cálculo automático de las horas que tomó resolver cada reporte.

**Herramientas**
Power Apps (app de lienzo), Dataverse, Power Automate y Microsoft Teams, dentro de una solución propia.

**Beneficio esperado**
- Avisos urgentes en segundos en lugar de depender del chat.
- Trazabilidad completa por reporte, con evidencia fotográfica.
- Datos para priorizar mantenimiento y medir el servicio por sede.

**Indicadores para medirlo**
| Indicador | Cómo se calcula |
|---|---|
| Tiempo promedio de resolución | Promedio de "Horas de resolución" de los reportes resueltos en el periodo |
| Cumplimiento en prioridad Alta | Reportes Alta resueltos dentro del tiempo objetivo / total de reportes Alta resueltos x 100 |
| Tiempo de aviso al técnico | Hora del mensaje de Teams menos hora de creación del reporte, desde el historial del flujo |
| Pendientes por sede | Reportes en estado Reportado o En atención, agrupados por sede |
| Adopción | Reportes registrados en la app / total de daños reportados por cualquier canal x 100 |

**Licencias**
Cada supervisor y técnico necesita licencia Premium de Power Apps (o por app), porque la app usa Dataverse. El flujo usa un conector premium; se recomienda una cuenta de servicio con Power Automate Premium. Teams está incluido en Microsoft 365. Validar el modelo final con el área de licenciamiento. Alternativa de menor costo: SharePoint con conectores estándar.

**Gobernanza**
- Entornos separados de desarrollo, pruebas y producción; despliegue con solución administrada.
- Editor y prefijo propios; nada en la solución predeterminada.
- Roles de seguridad por perfil (supervisor, técnico, líder).
- Conexiones con cuenta de servicio y políticas de datos (DLP).
- Dueño funcional en facilities y dueño técnico en TI; política de retención para fotos.

**Alcance y esfuerzo**
- **Prototipo funcional:** listo en menos de una jornada, con datos ficticios. Incluye modelo de datos con cálculo automático de tiempos, app de 4 pantallas, flujo de aviso por Teams y pruebas de punta a punta. Construido con apoyo de IA: definí el problema, el diseño y las reglas de calidad, y verifiqué cada resultado en el dato.
- **Camino a producción (estimado, 4 a 6 semanas):** levantamiento con supervisores y técnicos, catálogo real de sedes y tipos de daño, roles de seguridad, cuenta de servicio para el flujo, despliegue administrado a pruebas y producción, piloto en una sede, capacitación y medición de indicadores.

**Siguiente fase**
- Piloto de 4 semanas en una sede con 2 o 3 técnicos.
- Asignación automática por sede, reapertura de reportes y aviso al supervisor al resolver.
- Tablero en Power BI para el líder de facilities con los indicadores.
- Revisión de accesibilidad y roles de seguridad antes de escalar.

**Riesgos**
- Baja adopción si se mantiene WhatsApp en paralelo; definir la app como canal oficial.
- Costo de licencias Premium por usuario.
- Cobertura móvil limitada en algunas sedes al cargar fotos.
- Sin roles de seguridad, un usuario podría ver reportes que no le corresponden.

**Supuestos**
- Un técnico por reporte, asignado por el supervisor en el MVP.
- "Pendiente" significa Reportado o En atención; un reporte resuelto queda cerrado.
- El tiempo de resolución se mide en horas corridas, no hábiles.
- Todos los usuarios tienen Microsoft 365 con Teams.
