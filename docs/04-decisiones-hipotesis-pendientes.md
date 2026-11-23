# 04 · Decisiones, hipótesis y pendientes

> Última revisión: 22/11/2026[cite: 29]. Una decisión solo está «vigente» si el equipo la ha acordado[cite: 29]. Una hipótesis o un permiso pendiente **no** se trata como hecho[cite: 29]. Si cambia algo aquí, actualizad también el dossier (apartados 8, 9, 12 y 15)[cite: 7].

## 1. Decisiones vigentes

| ID | Decisión | Motivo | Dónde se refleja |
|---|---|---|---|
| **D1** | **Reserva sin cobro online.** El pago se hace al recoger el vehículo[cite: 29]. | La pasarela de pago está fuera del MVP[cite: 29]. | `02-mvp-y-alcance.md` (apdo. 2)[cite: 31] |
| **D2** | **Total = (Días × Tarifa_día) + (Km_estimados × Tasa_km).** Sin extras, fianza ni seguro en el MVP[cite: 18, 29]. | El MVP solo calcula con días y km para garantizar transparencia (N1)[cite: 18, 29]. | `02-mvp-y-alcance.md` (apdo. 2)[cite: 31] |
| **D3** | **Tabla `permiso ↔ tipo de vehículo` en la base de datos** (AM, A1, A2, A, B, C1…)[cite: 29]. Si el permiso no sirve, se bloquea la reserva y se muestra el motivo[cite: 29]. | Resuelve N2 sin integración externa con la DGT[cite: 22, 29]. | `02-mvp-y-alcance.md` (apdo. 2)[cite: 31] |
| **D4** | **Del carnet solo se guarda la categoría y la caducidad**, sin archivo de imagen[cite: 26, 29]. El administrador revisa el permiso físico al entregar el vehículo[cite: 29]. | Minimización de datos (RGPD arts. 5 y 32)[cite: 29]. | `02-mvp-y-alcance.md` (apdo. 2)[cite: 31] |
| **D5** | **Estados de reserva:** `pendiente`, `confirmada`, `cancelada`[cite: 26, 29]. Se rechaza cualquier reserva que solape con otra confirmada usando regla de extremos inclusivos (`inicio_nuevo <= fin_existente` y `fin_nuevo >= inicio_existente`)[cite: 26, 29]. | Resuelve N3 evitando dobles reservas incluso el mismo día de entrega/devolución[cite: 26, 29]. | `02-mvp-y-alcance.md` (apdo. 2)[cite: 31] |
| **D6** | **Despliegue local** en la primera versión[cite: 29]. | Sin hosting confirmado ni coste asociado[cite: 29]. | Dossier (apdo. 11)[cite: 21] |
| **D7** | **Asistente de búsqueda: roadmap**, no MVP[cite: 29]. | Prioridad baja; fuera del alcance y plazo actuales[cite: 29]. | `02-mvp-y-alcance.md` (apdo. 3)[cite: 31] |
| **D8** | **Roles:** `CLIENTE` y `ADMIN`[cite: 18, 29]. El administrador gestiona la flota y consulta reservas[cite: 29]. | Alcance del MVP[cite: 29]. | `02-mvp-y-alcance.md` (apdo. 1 y 2)[cite: 31] |
| **D9** | **Stack inicial:** Java 17/21, Spring Boot 3.x, Spring Data JPA, Spring Security, MySQL 8, HTML5/CSS3/JS[cite: 14, 19, 21, 29]. | Conocimientos del equipo y licencias gratuitas[cite: 19, 29]. | Dossier (apdos. 5, 8 y 11)[cite: 14, 19, 21] |
| **D10** | **Sin umbrales numéricos de rendimiento** hasta tener una primera medición (se elimina «< 2 s»)[cite: 29]. | No hay base empírica que lo sostenga antes de medir[cite: 29]. | Dossier (apdo. 15)[cite: 25] |

## 2. Hipótesis (sin contrastar)

| ID | Hipótesis | Cómo se contrasta |
|---|---|---|
| **H1** | Las dobles reservas en peticiones simultáneas son un riesgo real si no se bloquea la concurrencia (N3)[cite: 22, 29]. | Prueba unitaria de solape concurrente (F1 / F5)[cite: 20, 29] |
| **H2** | Los clientes recurrentes abandonan reservas si repiten sus datos y prefieren reutilizarlos (N4)[cite: 18, 29]. | Encuesta breve a 5-10 usuarios potenciales[cite: 18] |
| **H3** | Filtrar por permiso reduce reservas inválidas[cite: 29]. | Pruebas del filtro con cada categoría de permiso[cite: 22, 29] |
| **H4** | La transparencia tarifaria antes de confirmar genera confianza[cite: 29]. | Prueba de usabilidad con grupo reducido ajeno al equipo[cite: 25, 29] |
| **H5** | La demanda de alquiler para viajes y eventos es suficiente[cite: 29]. | Contrastado parcialmente con FENEVAL y ESDiario (20/11/2026)[cite: 11, 12] |
| **H6** | **242 h (220 h base + 10 % margen de imprevistos) entre dos personas (121 h cada una)** bastan para el MVP[cite: 22, 23]. | Contrastar con la docente y medir avance real en UT03[cite: 22, 29] |

## 3. Pendientes

| ID | Pendiente | Responsable | Estado |
|---|---|---|---|
| **P1** | Identificar las 3 webs de la comparativa (Sixt, Europcar, Goldcar; 20/11/2026)[cite: 11, 29] | Toni[cite: 22] | **Cerrado** |
| **P2** | Realizar y recoger resultado de la encuesta breve de N4 (5-10 usuarios)[cite: 18, 29] | Toni[cite: 22] | Abierto[cite: 29] |
| **P3** | Añadir fuentes con enlace para demanda sectorial y DAFO (FENEVAL y ESDiario; 20/11/2026)[cite: 11, 12, 29] | Drake[cite: 22] | **Cerrado** |
| **P4** | Confirmar con la docente la validación de tarifas y flota demo de GoRide en F1[cite: 21, 29] | Drake[cite: 22] | Abierto[cite: 29] |
| **P5** | Definir forma jurídica definitiva de la empresa desarrolladora (obligaciones laborales/fiscales)[cite: 14, 29] | Equipo[cite: 29] | Abierto[cite: 29] |
| **P6** | Comprobar vigencia de Kit Digital (cerrada 31/10/2025) y ENISA (16/11/2026)[cite: 15, 16, 29] | Drake[cite: 22] | **Cerrado** |
| **P7** | Ejecutar prueba de Spring Security con dos roles (`CLIENTE` y `ADMIN`) y ruta protegida[cite: 22, 29] | Drake[cite: 22] | Pendiente de prueba[cite: 29] |
| **P8** | Ejecutar prueba de solape de reservas con dos hilos simultáneos[cite: 22, 29] | Drake[cite: 22] | Pendiente de prueba[cite: 29] |

## 4. Fuera de alcance (ahora)

Pagos reales, app móvil nativa, GPS en tiempo real, integraciones con terceros, fianza y seguros[cite: 14, 29].

## 5. Roadmap

Pasarela de pago en modo de pruebas, informes PDF para seguros, mejoras de uso en móvil y asistente de búsqueda[cite: 14, 29].
