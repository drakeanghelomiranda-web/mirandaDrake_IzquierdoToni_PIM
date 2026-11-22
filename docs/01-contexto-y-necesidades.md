# 1. Contexto del Proyecto y Análisis de Necesidades

> Última revisión: 22/11/2026. Fuente de verdad para problema, necesidades y oportunidades. El detalle de alcance está en `02-mvp-y-alcance.md`; las decisiones y pendientes, en `decisiones-y-pendientes.md`.

## 1. Proyecto

GoRide es una aplicación web con servidor y base de datos para el alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales).

- **Cliente:** GoRide, empresa de *rent a car* ficticia, que usa la plataforma para mostrar su flota y gestionar reservas.
- **Empresa desarrolladora:** el equipo, organizado como software factory (desarrollo a medida). No es el cliente.

## 2. Problemas observados

1. El precio total no se conoce hasta el final de la reserva.
2. El usuario puede elegir un vehículo que su permiso no le autoriza a conducir.
3. Sin control de disponibilidad, un vehículo puede reservarse dos veces para las mismas fechas.
4. El cliente repite sus datos y los del carnet en cada reserva.
5. Se guardan datos personales y del carnet, y el usuario desconfía de cómo se tratan.

## 3. Personas afectadas

- Viajeros, grupos de amigos y familias.
- Empresas de catering y organización de eventos (furgonetas, vehículos especiales).
- Aficionados al motor que quieren probar vehículos de distintas gamas.
- GoRide, que pierde reservas por desconfianza y atiende consultas evitables.

## 4. Necesidades

| Nº | Necesidad | Afectados | Origen / evidencia | Estado | Importancia |
|---|---|---|---|---|---|
| N1 | Conocer el coste total estimado antes de reservar | Viajeros, familias, empresas de eventos | Comparativa de 3 webs de alquiler: [web 1, URL, fecha, observación] · [web 2…] · [web 3…] | Observado | Alta |
| N2 | Saber qué vehículos puede conducir con su permiso | Todos los usuarios | Clases de permiso del Reglamento General de Conductores (RD 818/2009, art. 4 y ss.) [enlace BOE, fecha] | Fuente normativa | Alta |
| N3 | Evitar que un vehículo se reserve dos veces en fechas solapadas | GoRide y usuarios | Riesgo de sobreventa en sistemas sin control de disponibilidad | **Hipótesis** (se contrasta con la prueba de solape) | Alta |
| N4 | Reutilizar los datos del cliente sin repetirlos en cada reserva | Clientes recurrentes y empresas | Encuesta breve [nº de respuestas, fecha] | **Hipótesis** | Media |
| N5 | Tratar los datos personales y del carnet con seguridad y legalidad | Usuarios y GoRide | RGPD (arts. 5 y 32), LOPDGDD 3/2018 [enlaces]; desconfianza detectada en UT0 | Fuente normativa | Alta |

**Problema, necesidad y solución.** Problema: «no sé el precio final». Necesidad: N1. Solución: motor de presupuesto en la reserva.

## 5. Oportunidades

| Oportunidad | Necesidad | Valor | Prioridad | Decisión que origina |
|---|---|---|---|---|
| O1. Transparencia tarifaria | N1 | Elimina sorpresas y genera confianza | Alta | Mostrar el total antes de confirmar |
| O2. Búsqueda guiada por requisitos legales | N2 | Evita elegir vehículos no conducibles | Alta | Filtro por permiso en el catálogo |
| O3. Reserva fiable sin dobles reservas | N3 | Reduce errores y reservas perdidas | Alta | Comprobar disponibilidad antes de confirmar |
| O4. Perfil único y tratamiento seguro de datos | N4, N5 | Agiliza reservas recurrentes y reduce riesgo legal | Media | Cuenta con datos mínimos y contraseñas con hash |

## 6. Conclusión estratégica (resumen del DAFO)

No se compite en flota ni en funciones, sino en dos diferenciales: **filtrado por permiso** y **precio total transparente**. El equipo pequeño, el plazo limitado y las obligaciones del RGPD justifican un MVP reducido, sin pagos ni app móvil, y con datos mínimos del carnet. El DAFO completo está en `03-sector-y-dafo.md`.

## 7. Cambios respecto a UT0 y a la primera versión de este fichero

- Los **pagos** dejan de ser una necesidad del MVP. La pasarela pasa al roadmap (el proyecto no admite integraciones externas obligatorias).
- Se añade el **solape de reservas** (N3) y los **datos seguros** (N5), antes sin cubrir.
- N3 y N4 se marcan como **hipótesis**.
- Se elimina el término «extras» del coste total (ver `decisiones-y-pendientes.md`, D2).
- El asistente de búsqueda pasa al roadmap.
