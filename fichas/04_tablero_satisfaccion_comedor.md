# Ficha de propuesta - Tablero de satisfacción del servicio de comedor

Prototipo con datos ficticios (1.137 encuestas de ejemplo), construido en un laboratorio personal. Se presenta como demostración de lo que se puede construir, para contrastar con la realidad del área.

**Nombre de la propuesta**
Tablero de satisfacción por sede y servicio, con alertas y tendencia semanal.

**Restricción actual**
La satisfacción se mide con encuestas sueltas y se revisa en Excel, si se revisa. Un promedio general puede verse bien y esconder una sede que empeora semana a semana.

**Usuarios**
- Gerente de operaciones: revisa el tablero cada semana.
- Administradores de sede: ven su sede y los comentarios de sus comensales.

**Solución (MVP)**
- Indicadores clave: encuestas, promedio general y porcentaje de satisfechos.
- Promedio por sede con alerta en rojo por debajo de 3,5.
- Tendencia semanal por sede y comentarios recientes.
- Filtros por servicio (desayuno, almuerzo) y por región.

**Herramientas**
Power BI (modelo en estrella con tabla de calendario y medidas DAX). En producción, la encuesta se capturaría con Power Apps o Forms y se guardaría en Dataverse o SharePoint.

**Beneficio esperado**
- Detectar a tiempo una sede en deterioro. En los datos de ejemplo, el tablero reveló una sede que caía semana a semana y otra que mejoraba tras un cambio, invisibles en el promedio general.
- Decisiones basadas en datos y comentarios reales.

**Indicadores para medirlo**
| Indicador | Cómo se calcula |
|---|---|
| Satisfacción promedio | Promedio de las 3 preguntas (sabor, variedad, atención), de 1 a 5 |
| % satisfechos | Encuestas con promedio de 4 o más / total de encuestas x 100 |
| Sedes en alerta | Sedes con promedio menor que 3,5 en la semana |

**Licencias**
Power BI Desktop es gratuito. Para compartir el tablero se necesita Power BI Pro (o capacidad Premium o Fabric) para quien publica y quien consulta.

**Gobernanza**
Área de trabajo del equipo, actualización programada, permisos por rol y, si aplica, seguridad a nivel de fila para que cada administrador vea su sede.

**Alcance y esfuerzo**
- **Prototipo funcional:** listo en menos de una jornada, con datos ficticios. Incluye carga y limpieza en Power Query, modelo en estrella con calendario, medidas DAX y tablero de una página con alertas y tendencia.
- **Camino a producción (estimado, 3 a 5 semanas):** diseño de la encuesta real con el área de servicio, captura en Power Apps o Forms, conexión a la fuente y actualización programada, seguridad por sede, publicación en el área de trabajo del equipo, capacitación a gerentes y administradores.

**Siguiente fase**
- Conectar a la fuente real y programar la actualización.
- Seguridad por sede y alertas automáticas por correo o Teams.
- Cruzar con el menú del día para entender qué platos funcionan.

**Riesgos y supuestos**
- La calidad del tablero depende del volumen y la honestidad de las respuestas: encuesta corta y anónima.
- Escala de 1 a 5 y 3 preguntas; ajustar con el área de servicio.
