# 01 · Contexto del Proyecto y Análisis de Necesidades

> Última revisión: 22/11/2026[cite: 32]. Fuente de verdad para problema, necesidades y oportunidades[cite: 32]. El detalle de alcance está en `02-mvp-y-alcance.md`; las decisiones y pendientes, en `04-decisiones-hipotesis-pendientes.md`[cite: 29, 32].

## 1. Proyecto

GoRide es una aplicación web con servidor y base de datos para el alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales)[cite: 8, 32].

- **Cliente:** GoRide, empresa de *rent a car* ficticia, que usa la plataforma para mostrar su flota y gestionar reservas[cite: 8, 32].
- **Empresa desarrolladora:** El equipo (Drake y Toni), organizado como *software factory* (desarrollo a medida)[cite: 9, 22, 32]. No es el cliente[cite: 9, 32].

## 2. Problemas observados

1. El precio total no se conoce hasta el final de la reserva[cite: 8, 32].
2. El usuario puede elegir un vehículo que su permiso no le autoriza a conducir[cite: 8, 32].
3. Sin control de disponibilidad, un vehículo puede reservarse dos veces para las mismas fechas[cite: 8, 32].
4. El cliente repite sus datos y los del carnet en cada reserva[cite: 8, 32].
5. Se guardan datos personales y del carnet, y el usuario desconfía de cómo se tratan[cite: 8, 32].

## 3. Personas afectadas

- Viajeros, grupos de amigos y familias[cite: 8, 32].
- Empresas de catering y organización de eventos (furgonetas, vehículos especiales)[cite: 8, 32].
- Aficionados al motor que quieren probar vehículos de distintas gamas[cite: 8, 32].
- GoRide, que pierde reservas por desconfianza y atiende consultas evitables[cite: 8, 32].

## 4. Necesidades

| Nº | Necesidad | Afectados | Origen / evidencia | Estado | Importancia |
|---|---|---|---|---|---|
| **N1** | Conocer el coste total estimado antes de reservar[cite: 11, 32] | Viajeros, familias, empresas de eventos[cite: 11, 32] | Observación en 3 portales de *rent a car*: Sixt (`https://www.sixt.es`), Europcar (`https://www.europcar.com`) y Goldcar (`https://www.goldcar.es`). Los suplementos por kilometraje o coberturas alteran el precio final en los últimos pasos (Consulta: 20/11/2026)[cite: 11]. | Observado[cite: 32] | Alta[cite: 11, 32] |
| **N2** | Saber qué vehículos puede conducir con su permiso[cite: 11, 32] | Todos los usuarios[cite: 11, 32] | Clases de permiso del Reglamento General de Conductores (RD 818/2009, arts. 4 y 5.7, BOE: `https://www.boe.es`, consulta: 20/11/2026)[cite: 18, 32]. | Fuente normativa[cite: 32] | Alta[cite: 11, 32] |
| **N3** | Evitar que un vehículo se reserve dos veces en fechas solapadas[cite: 11, 32] | GoRide y usuarios[cite: 11, 32] | Riesgo de sobreventa en sistemas sin control de disponibilidad y datos del sector en FENEVAL (`https://www.feneval.com`, consulta: 20/11/2026)[cite: 11, 32]. | **Hipótesis** (a contrastar con prueba de solape)[cite: 11, 32] | Alta[cite: 11, 32] |
| **N4** | Reutilizar los datos del cliente sin repetirlos en cada reserva[cite: 11, 32] | Clientes recurrentes y empresas[cite: 11, 32] | Hipótesis interna de usabilidad del equipo (20/11/2026); pendiente validar con encuesta breve a 5-10 usuarios potenciales[cite: 18]. | **Hipótesis**[cite: 32] | Media[cite: 11, 32] |
| **N5** | Tratar los datos personales y del carnet con seguridad y legalidad[cite: 11, 32] | Usuarios y GoRide[cite: 11, 32] | RGPD (arts. 5 y 32) y LOPDGDD (LO 3/2018, BOE), consulta: 20/11/2026; desconfianza detectada en UT01[cite: 11, 18]. | Fuente normativa[cite: 32] | Alta[cite: 11, 32] |

**Problema, necesidad y solución.** Problema: «no sé el precio final»[cite: 32]. Necesidad: N1[cite: 32]. Solución: motor de presupuesto transparente antes de confirmar la reserva[cite: 19, 32].

## 5. Oportunidades

| Oportunidad | Necesidad | Valor | Prioridad | Decisión que origina |
|---|---|---|---|---|
| O1. Transparencia tarifaria[cite: 12, 32] | N1[cite: 12, 32] | Elimina sorpresas y genera confianza[cite: 12, 32] | Alta[cite: 12, 32] | Mostrar el total desglosado antes de confirmar (D2)[cite: 18, 32] |
| O2. Búsqueda guiada por requisitos legales[cite: 12, 32] | N2[cite: 12, 32] | Evita elegir vehículos no conducibles[cite: 12, 32] | Alta[cite: 12, 32] | Filtro por permiso en el catálogo (D3)[cite: 29, 32] |
| O3. Reserva fiable sin dobles reservas[cite: 12, 32] | N3[cite: 12, 32] | Reduce errores y reservas perdidas[cite: 12, 32] | Alta[cite: 12, 32] | Comprobar disponibilidad y solape inclusivo (D5)[cite: 26, 32] |
| O4. Perfil único y tratamiento seguro de datos[cite: 12, 32] | N4, N5[cite: 12, 32] | Agiliza reservas recurrentes y reduce riesgo legal[cite: 12, 32] | Media[cite: 12, 32] | Cuenta con datos mínimos y contraseñas BCrypt (D4)[cite: 18, 29, 32] |

## 6. Conclusión estratégica (resumen del DAFO)

No se compite en flota ni en funciones, sino en dos diferenciales: **filtrado por permiso** y **precio total transparente**[cite: 13, 32]. El equipo pequeño (2 integrantes), el plazo limitado y las obligaciones del RGPD justifican un MVP reducido, sin pagos ni app móvil, y con datos mínimos del carnet[cite: 13, 21, 32]. El DAFO completo está en `03-sector-y-dafo.md`[cite: 32].

## 7. Cambios respecto a UT01

- Los **pagos** dejan de ser una necesidad del MVP. La pasarela pasa al roadmap (el proyecto no admite integraciones externas obligatorias)[cite: 8, 32].
- Se añade el **solape de reservas** (N3) y los **datos seguros** (N5), antes sin cubrir[cite: 32].
- N3 y N4 se marcan como **hipótesis**[cite: 32].
- Se elimina el término «extras» del coste total (ver `04-decisiones-hipotesis-pendientes.md`, D2)[cite: 29, 32].
- El asistente de búsqueda pasa al roadmap (D7)[cite: 29, 32].
