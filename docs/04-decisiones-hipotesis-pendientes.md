# Decisiones, hipótesis y pendientes

> Última revisión: 22/11/2026. Una decisión solo está «vigente» si el equipo la ha acordado. Una hipótesis o un permiso pendiente **no** se trata como hecho. Si cambia algo aquí, actualizad también el dossier (apartados 9.1, 9.5 y 9.7).

## 1. Decisiones vigentes

| ID | Decisión | Motivo | Dónde se refleja |
|---|---|---|---|
| D1 | **Reserva sin cobro online.** El pago se hace al recoger el vehículo. | La pasarela de pago está fuera del MVP. | `02-mvp-y-alcance.md` |
| D2 | **Total = días × tarifa diaria + km estimados × tarifa por km.** Sin extras, fianza ni seguro en el MVP. | El MVP solo calcula con días y km. | `02-mvp-y-alcance.md` |
| D3 | **Tabla permiso ↔ tipo de vehículo en la base de datos** (AM, A1, A2, A, B, C1…). Si el permiso no sirve, se bloquea la reserva y se muestra el motivo. | Resuelve N2 sin integración externa. | `02-mvp-y-alcance.md` |
| D4 | **Del carnet solo se guarda la categoría y la caducidad**, sin imagen. El administrador revisa el permiso al entregar el vehículo. | Minimización de datos (RGPD arts. 5 y 32). | `02-mvp-y-alcance.md` |
| D5 | **Estados de reserva:** pendiente, confirmada, cancelada. Se rechaza una reserva que solape con otra confirmada del mismo vehículo. | Resuelve N3. | `02-mvp-y-alcance.md` |
| D6 | **Despliegue local** en la primera versión. | Sin hosting confirmado ni coste asociado. | Dossier 9.4 |
| D7 | **Asistente de búsqueda: roadmap**, no MVP. | Prioridad baja; fuera del equipo y el plazo actuales. | `02-mvp-y-alcance.md` |
| D8 | **Roles:** cliente y administrador. El administrador gestiona la flota y consulta reservas. | Alcance del MVP. | `02-mvp-y-alcance.md` |
| D9 | **Stack inicial:** Spring Boot, Spring Data JPA, Spring Security, MySQL, HTML/CSS/JS. Punto de partida, no cierre definitivo. | Conocimientos del equipo. | Dossier 5 |
| D10 | **Sin umbrales numéricos de rendimiento** hasta tener una primera medición (se elimina «< 2 s»). | No hay base que lo sostenga. | Dossier 9.2 y 9.8 |

## 2. Hipótesis (sin contrastar)

| ID | Hipótesis | Cómo se contrasta |
|---|---|---|
| H1 | Las dobles reservas son un riesgo real (N3). | Prueba de solape (dossier 9.9) |
| H2 | Los clientes quieren reutilizar sus datos (N4). | Encuesta breve |
| H3 | Filtrar por permiso reduce reservas inválidas. | Pruebas del filtro y comparativa de webs |
| H4 | La transparencia tarifaria genera confianza. | Prueba de usabilidad con 3 personas ajenas |
| H5 | La demanda de alquiler para viajes y eventos es suficiente. | Fuente sectorial con enlace y fecha |
| H6 | 240 h entre tres personas bastan para el MVP. | Contrastar con la docente y con el avance real |

## 3. Pendientes

| ID | Pendiente | Responsable | Estado |
|---|---|---|---|
| P1 | Identificar las 3 webs de la comparativa (nombre, URL, fecha, observación) | [asignar] | Abierto |
| P2 | Resultado de la encuesta de N4 | [asignar] | Abierto |
| P3 | Fuente con enlace para H5 y para el DAFO | [asignar] | Abierto |
| P4 | Confirmar con la docente si hace falta despliegue público y qué datos del carnet bastan | Equipo | Abierto |
| P5 | Forma jurídica de la empresa desarrolladora (afecta a las obligaciones laborales y fiscales) | Equipo | Abierto |
| P6 | Vigencia de Kit Digital y ENISA (se revisa si se abre convocatoria) | [asignar] | Abierto |
| P7 | Prueba de Spring Security con dos roles | [asignar] | Pendiente de prueba |
| P8 | Prueba de solape de reservas, incluso concurrentes | [asignar] | Pendiente de prueba |

## 4. Fuera de alcance (ahora)

Pagos reales, app móvil nativa, GPS en tiempo real, integraciones con terceros, fianza y seguros.

## 5. Roadmap

Pasarela de pago en modo de pruebas, informes PDF para seguros, mejoras de uso en móvil y asistente de búsqueda.
