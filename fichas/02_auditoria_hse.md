# Ficha de propuesta - Auditoría HSE de extintores desde el celular

Prototipo con datos ficticios, construido en un laboratorio personal. Se presenta como demostración de lo que se puede construir, para contrastar con la realidad del área.

**Nombre de la propuesta**
Auditoría HSE móvil con evidencia obligatoria cuando algo no cumple.

**Restricción actual**
Las revisiones de extintores se hacen con una lista de chequeo en papel. Las fallas quedan descritas a mano, sin foto, y se transcriben tarde a Excel. No hay forma rápida de saber qué sedes tienen hallazgos abiertos.

**Usuarios**
- Auditores HSE en terreno: registran desde el celular.
- Coordinador HSE: consulta y gestiona los hallazgos desde el escritorio.

**Solución (MVP)**
- App de celular: sede auditada, nombre del auditor e interruptor "Cumple extintores".
- Si no cumple, la app **muestra y exige** la descripción de la falla y una foto de evidencia antes de enviar.
- App de escritorio (basada en modelo) para el coordinador: lista de auditorías, filtros por sede y detalle con la foto.

**Herramientas**
Power Apps (lienzo para el celular y basada en modelo para el escritorio) y Dataverse, dentro de una solución propia.

**Beneficio esperado**
- Cero hallazgos sin evidencia: la regla la impone la app, no la memoria del auditor.
- Información disponible en el momento, sin transcribir papel.
- Base para medir cumplimiento por sede.

**Indicadores para medirlo**
| Indicador | Cómo se calcula |
|---|---|
| Cumplimiento por sede | Auditorías con "Cumple" / total de auditorías de la sede x 100 |
| Hallazgos con evidencia | Auditorías "No cumple" con foto / total de "No cumple" x 100 (meta: 100 %) |
| Tiempo de registro | Minutos desde que el auditor abre la app hasta enviar (muestra en piloto) |

**Licencias**
Premium de Power Apps (por usuario o por app) para auditores y coordinador, porque usa Dataverse. Alternativa estándar: SharePoint, con menos control de seguridad.

**Gobernanza**
Solución propia con editor y prefijo; despliegue administrado a pruebas y producción; roles de seguridad (el auditor ve lo suyo, el coordinador todo); retención para fotos; política de datos (DLP).

**Alcance y esfuerzo**
- **Prototipo funcional:** listo en menos de una jornada, con datos ficticios. Incluye modelo de datos, app de celular con reglas condicionales, app de escritorio para el coordinador y pruebas verificando cada resultado en el dato (así se detectó y corrigió un formato de foto no soportado). Construido con apoyo de IA.
- **Camino a producción (estimado, 3 a 4 semanas):** levantamiento con auditores y coordinador, ajuste de la lista de chequeo real, roles de seguridad, despliegue administrado a pruebas y producción, piloto en una sede, capacitación y medición de indicadores.

**Siguiente fase**
- Usar el usuario de Microsoft 365 como auditor en lugar de un texto.
- Plan de acción por hallazgo con responsable y fecha.
- Aviso al coordinador cuando una sede no cumple y tablero de cumplimiento en Power BI.
- Ampliar la lista de chequeo (botiquín, señalización, rutas de evacuación).

**Riesgos y supuestos**
- Cobertura móvil en algunas sedes al subir fotos: evaluar el modo sin conexión.
- Se asume una auditoría por sede y visita; la lista de chequeo real puede tener más ítems.
