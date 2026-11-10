# Ficha de propuesta - Control de acceso de contratistas en portería

Prototipo con datos ficticios, construido en un laboratorio personal. Se presenta como demostración de lo que se puede construir, para contrastar con la realidad del área.

**Nombre de la propuesta**
Registro digital de ingreso y salida de contratistas, con firma y aviso al supervisor.

**Restricción actual**
La portería registra a los contratistas en una planilla de papel. No se sabe en tiempo real quién está dentro de cada sede, el supervisor no se entera de los ingresos y la aceptación de políticas de seguridad no queda soportada.

**Usuarios**
- Personal de portería: registra ingresos y salidas en una tableta.
- Supervisores de sede: reciben el aviso de cada ingreso.

**Solución (MVP)**
- Registro de ingreso: nombre, cédula, empresa contratista, sede, aceptación de políticas y firma en pantalla. El botón solo se activa cuando todo está completo.
- Lista de "quién sigue dentro" y registro de salida con un toque.
- Aviso por Teams al supervisor en cada ingreso, sin incluir la cédula (dato mínimo necesario).

**Herramientas**
Power Apps (lienzo para tableta), Dataverse, Power Automate y Microsoft Teams, dentro de una solución propia.

**Beneficio esperado**
- Saber en todo momento quién está dentro de cada sede (clave en una emergencia o evacuación).
- Aceptación de políticas con firma, trazable por persona y fecha.
- Supervisores enterados al instante.

**Indicadores para medirlo**
| Indicador | Cómo se calcula |
|---|---|
| Ingresos registrados digitalmente | Ingresos en la app / total de ingresos (app + papel) x 100 |
| Salidas sin registrar | Registros sin hora de salida al cierre del día |
| Tiempo de registro en portería | Promedio de segundos por ingreso (muestra en piloto) |

**Licencias**
Premium para el personal de portería (Dataverse) y conector premium en el flujo, idealmente con cuenta de servicio. Teams incluido en Microsoft 365.

**Gobernanza y datos personales**
La cédula es un dato personal: se guarda con acceso restringido (roles de seguridad y, si aplica, seguridad de columna), no se envía en avisos y se define su tiempo de retención según la política de tratamiento de datos (Ley 1581 de 2012). Solución propia, despliegue administrado y cuenta de servicio para el flujo.

**Alcance y esfuerzo**
- **Prototipo funcional:** listo en menos de una jornada, con datos ficticios. Incluye modelo de datos, app de portería con firma, registro de salida, flujo de aviso por Teams, ajustes de experiencia de usuario y publicación. Construido con apoyo de IA; detecté y corregí que la sede llegaba vacía en el aviso, verificando el mensaje final y no solo el estado del flujo.
- **Camino a producción (estimado, 4 a 6 semanas):** validación del tratamiento de datos personales con el área jurídica, levantamiento con portería y supervisores, roles y seguridad de columna para la cédula, cuenta de servicio, despliegue administrado, piloto en una sede, capacitación y medición de indicadores.

**Siguiente fase**
- Validar contra la lista de contratistas autorizados y la vigencia de su seguridad social.
- Reporte diario de permanencias y alertas de salidas no registradas.
- Código QR por contratista para agilizar el ingreso.

**Riesgos y supuestos**
- Tratamiento de datos personales: validar con el área jurídica antes del piloto.
- Una tableta por portería con conexión estable.
