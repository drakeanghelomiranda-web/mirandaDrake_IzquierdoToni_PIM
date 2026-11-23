# GoRide - Plataforma Web de Alquiler de Vehículos

> **Módulo:** Proyecto Intermodular (PIM) – UT02: Diseño y viabilidad del proyecto[cite: 1]  
> **Ciclo:** Desarrollo de Aplicaciones Web (DAW) | **Curso:** 2026-2027[cite: 6]  
> **Equipo:** Drake Anghelo Miranda Álvarez y Toni Izquierdo Carbonell[cite: 6, 7]  
> **Última revisión:** 22/11/2026[cite: 29, 31, 32]

---

## 1. Descripción y Contexto del Proyecto

**GoRide** es una aplicación web con arquitectura cliente-servidor y persistencia en base de datos destinada al alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales)[cite: 8, 13, 14].

* **Cliente final:** GoRide, empresa ficticia de *rent a car* que utiliza la plataforma para publicar su flota y gestionar reservas[cite: 8, 32].
* **Empresa desarrolladora:** El equipo (Drake y Toni), organizado como una **Software Factory** de desarrollo a medida[cite: 9, 22, 32]. No somos la empresa de alquiler, sino el equipo técnico que diseña y programa la solución ajustada a sus reglas de negocio[cite: 9, 30].

### Público objetivo y perfiles de usuario
* **Colectivos afectados:** Viajeros, grupos de amigos y familias; empresas de catering y organización de eventos (furgonetas y vehículos especiales); aficionados al motor; y la propia empresa GoRide (que evita pérdidas de reservas y consultas innecesarias)[cite: 8, 13, 32].
* **Perfiles del sistema (D8):** `CLIENTE` (consulta catálogo, calcula presupuestos y gestiona sus reservas/perfil) y `ADMIN` (gestiona altas, bajas y edición de la flota, y consulta las reservas)[cite: 13, 18, 29, 31].

### Problemas identificados (UT01) y necesidades (N1–N5)
1. **Opacidad de tarifas (N1):** El precio total no queda claro hasta el final del proceso de reserva[cite: 8, 11].
2. **Incompatibilidad legal de permisos (N2):** El usuario puede elegir un vehículo que su permiso de conducir no le autoriza a conducir[cite: 8, 11].
3. **Dobles reservas (N3):** Sin control de disponibilidad, un mismo vehículo puede reservarse dos veces en fechas solapadas[cite: 8, 11].
4. **Fricción en reservas recurrentes (N4):** El cliente repite sus datos personales y los de su carnet en cada reserva[cite: 8, 11].
5. **Desconfianza en protección de datos (N5):** Se almacenan datos sensibles del carnet sin claridad sobre su seguridad y cumplimiento del RGPD[cite: 8, 11, 12].

---

## 2. Propuesta de Valor y Alcance del MVP

Nuestra propuesta se diferencia de los portales generalistas mediante dos pilares: **filtrado guiado por requisitos legales del permiso de conducir** y **cálculo transparente del precio total antes de confirmar**[cite: 12, 13, 31].

### Tres funcionalidades principales de la primera versión
1. **C1 · Catálogo interactivo con filtros y gestión de flota (`N2`):**
   * Búsqueda combinada por tipo de vehículo, combustible, número de plazas y permiso de conducir requerido (usando una tabla de equivalencias en BD, D3)[cite: 13, 29, 31].
   * Panel de administración para dar de alta, editar y retirar vehículos de la flota de demostración[cite: 13, 19, 31].
2. **C2 · Motor de presupuesto dinámico, disponibilidad y reserva (`N1`, `N3`):**
   * Cálculo en tiempo real antes de confirmar: `Total = (Tarifa_día × Días) + (Km_estimados × Tasa_km)`, sin extras, fianza ni seguro (D2)[cite: 18, 29, 31].
   * Control de disponibilidad con bloqueo automático de solapes mediante regla de extremos inclusivos (`inicio_nuevo <= fin_existente` y `fin_nuevo >= inicio_existente`, D5)[cite: 26, 29, 31].
   * Gestión de estados (`pendiente`, `confirmada`, `cancelada`). El pago es presencial al recoger el vehículo (D1)[cite: 26, 29, 31].
3. **C3 · Cuenta de usuario, datos mínimos y validación de permiso (`N2`, `N4`, `N5`):**
   * Registro y login seguro con Spring Security (contraseñas cifradas con hash BCrypt)[cite: 18, 31].
   * Reutilización de datos de contacto en futuras reservas[cite: 19, 31].
   * **Minimización de datos (D4):** Del carnet solo se guarda la **categoría y la fecha de caducidad**, sin subir archivos de imagen[cite: 26, 29, 31]. El sistema bloquea la reserva si el permiso no es compatible y el administrador verifica el carnet físico en la entrega[cite: 29, 31].

| Incluido en el MVP | Roadmap (versiones futuras) | Fuera de alcance (ahora) |
|---|---|---|
| C1, C2 y C3 para roles `CLIENTE` y `ADMIN` en entorno local[cite: 19, 21, 29] | Pasarela de pago en pruebas, informes PDF para seguros, mejoras en móvil y asistente de búsqueda (D7)[cite: 14, 29, 31] | Pagos online reales, app móvil nativa, GPS en tiempo real, integraciones externas (DGT), fianzas y seguros[cite: 14, 22, 29, 31] |

---

## 3. Arquitectura, Stack Tecnológico y Viabilidad

* **Stack (D9):** Java 17/21 (OpenJDK), **Spring Boot 3.x**, Spring Data JPA, Spring Security, **MySQL 8** y Frontend en **HTML5, CSS3 y JavaScript**[cite: 14, 19, 21, 29, 31].
* **Despliegue (D6):** Entorno local en la primera versión (coste de infraestructura: 0 €)[cite: 21, 23, 29].
* **Modelo de datos (nivel diseño):** `Vehículo`, `Usuario`, `Perfil`, `Reserva` y `Tabla_Compatibilidad_Permisos`[cite: 24, 31].

### Estado de dependencias técnicas
* **Viables:** Cálculo aritmético de tarifas y minimización de datos del carnet (RGPD)[cite: 22].
* **Viables con condiciones:**
  * *Validación de permisos:* Se valida frente a tabla interna según RD 818/2009 (incluyendo equivalencia en España de permiso B > 3 años con A1, pendiente de revisar actualización DGT)[cite: 18, 22, 23].
  * *Entorno y versiones:* Unificación en Spring Boot 3.x y MySQL 8 en los equipos locales de ambos integrantes[cite: 19, 21, 22].
* **Pendientes de prueba técnica:**
  * Concurrencia en reservas simultáneas (test con dos hilos reservando el mismo vehículo a la vez)[cite: 22, 29].
  * Flujo completo de autenticación y bloqueo de rutas por rol (`CLIENTE` vs `ADMIN`) con Spring Security[cite: 22, 29].

---

## 4. Planificación, Roles y Presupuesto

El desarrollo se estructura en **6 fases** con una estimación de **220 horas base + 22 horas de margen de imprevistos (10 %) = 242 horas totales**, repartidas al 50 % entre los dos integrantes[cite: 20, 22, 23]:

| Fase | Contenido principal | Entregable revisable | Horas | Coste (20 €/h) |
|---|---|---|---|---|
| **F1. Diseño y validación** | Reglas de negocio (permiso, solape, tarifa), modelo de datos, wireframes y prueba de solape[cite: 20] | Modelo de datos, wireframes, tabla permisos y prueba[cite: 20] | 35 h[cite: 20, 23] | 700 €[cite: 23] |
| **F2. Base técnica** | Proyecto Spring Boot, MySQL, Spring Security y repositorio Git[cite: 20] | App arrancando y conectada a BD con entidad base[cite: 20] | 30 h[cite: 20, 23] | 600 €[cite: 23] |
| **F3. Catálogo y flota** | Entidades de vehículo, filtros combinados y gestión CRUD admin[cite: 20] | Catálogo filtrable con flota demo y panel admin[cite: 20] | 40 h[cite: 20, 23] | 800 €[cite: 23] |
| **F4. Cuenta y permiso** | Registro/login, perfil reutilizable y bloqueo por permiso[cite: 20] | Registro funcional y rechazo de vehículos incompatibles[cite: 20] | 45 h[cite: 20, 23] | 900 €[cite: 23] |
| **F5. Presupuesto y reserva** | Cálculo de tarifa, disponibilidad y bloqueo de solapes[cite: 20] | Reserva completa con total previo y control concurrencia[cite: 20] | 40 h[cite: 20, 23] | 800 €[cite: 23] |
| **F6. Pruebas y cierre** | Pruebas de calidad, corrección de errores y documentación[cite: 20] | Informe de pruebas y repositorio alineado con PDF[cite: 20] | 30 h[cite: 20, 23] | 600 €[cite: 23] |
| **Margen imprevistos (10%)** | Colchón de seguridad para desviaciones técnicas[cite: 23] | — | 22 h[cite: 23] | 440 €[cite: 23] |
| **TOTAL** | **Autofinanciado mediante aportación de horas propias**[cite: 23] | **121 h Drake · 121 h Toni**[cite: 22] | **242 h**[cite: 23] | **4.840 €**[cite: 23] |

* **Reparto de responsabilidades:**
  * **Drake Anghelo Miranda Álvarez (121 h):** Coordinador y Revisor (coherencia PDF/GitHub, enlace con docente, contraste de fuentes) + Desarrollo Backend, Spring Security y motor de solape/reservas[cite: 22].
  * **Toni Izquierdo Carbonell (121 h):** Redactor y Revisor (maquetación del dossier, tablas y actualización de Markdown) + Diseño UI/UX, Frontend y módulo de catálogo/tarifas[cite: 22].
* **Financiación:** Coste de software y equipamiento = **0 €** (herramientas open source/gratuitas y portátiles propios)[cite: 21, 23]. No se recurre a subvenciones externas (Kit Digital cerró el 31/10/2025 y ENISA exige sociedad constituida), por lo que el proyecto se autofinancia íntegramente[cite: 19, 23].

---

## 5. Criterios de Calidad del Diseño

Para validar la primera versión se comprobarán los siguientes aspectos (sin umbrales numéricos de rendimiento hasta la primera medición, D10)[cite: 24, 25, 29]:

* **Corrección de reserva:** Test automático con reservas solapadas y simultáneas (solo se confirma una)[cite: 24].
* **Corrección de permiso:** Pruebas por cada categoría de carnet (solo se listan y reservan vehículos compatibles)[cite: 24].
* **Precio anticipado:** Comparativa entre el total mostrado antes de confirmar y el cálculo manual[cite: 24].
* **Seguridad y acceso por rol:** Contraseñas almacenadas como hash BCrypt en BD; un usuario `CLIENTE` recibe acceso denegado al intentar abrir rutas `/admin`[cite: 18, 25].
* **Privacidad (RGPD):** Verificación de columnas en MySQL para asegurar que no se guardan datos ni imágenes extra fuera del diseño[cite: 25, 26].
* **Usabilidad y rendimiento:** Prueba de flujo de reserva completo sin ayuda con usuarios ajenos al equipo, y registro de tiempos de carga del catálogo con flota demo[cite: 25].

---

## 6. Decisiones Vigentes, Fuentes y Pendientes

### Decisiones clave (D1–D10)
* **D1:** Pago presencial al recoger el vehículo (sin pasarela online)[cite: 29].
* **D2:** Fórmula cerrada `Total = (Tarifa_día × Días) + (Km_estimados × Tasa_km)`[cite: 18, 29].
* **D3:** Validación de permisos mediante tabla interna en BD[cite: 29].
* **D4:** Solo se guarda categoría y caducidad del carnet (sin imagen)[cite: 26, 29].
* **D5:** Estados (`pendiente`, `confirmada`, `cancelada`) y solape inclusivo (`inicio_nuevo <= fin_existente` y `fin_nuevo >= inicio_existente`)[cite: 26, 29].
* **D6:** Despliegue local en el MVP[cite: 21, 29].
* **D7:** Asistente de búsqueda pospuesto al roadmap[cite: 29].
* **D8:** Roles `CLIENTE` y `ADMIN`[cite: 18, 29].
* **D9:** Stack Java 17/21 + Spring Boot 3.x + JPA + Security + MySQL 8 + HTML/CSS/JS[cite: 14, 19, 21, 29].
* **D10:** Sin umbrales numéricos de rendimiento sin medición previa[cite: 25, 29].

### Fuentes principales contrastadas
* **RD 818/2009 (Reglamento General de Conductores, arts. 4 y 5.7):** BOE (`https://www.boe.es`), consultado el 20/11/2026[cite: 18, 32].
* **RGPD (arts. 5 y 32) y LOPDGDD (LO 3/2018):** BOE, consultado el 20/11/2026[cite: 11, 18].
* **Comparativa de mercado (Sixt, Europcar, Goldcar):** Consultadas el 20/11/2026 para analizar transparencia de tarifas[cite: 11].
* **FENEVAL (`https://www.feneval.com`) y ESDiario Motor:** Consultadas el 20/11/2026 para datos de demanda del sector[cite: 11, 12].
* **Red.es (Kit Digital) y ENISA:** Consultadas el 16/11/2026 para verificar disponibilidad de ayudas[cite: 15, 16, 19].

### Pendientes abiertos
* **P2 (Toni):** Realizar encuesta breve a 5–10 usuarios potenciales para validar la reutilización de datos (N4)[cite: 18, 22, 29].
* **P4 (Drake):** Confirmar con la docente las tarifas y flota ficticia de GoRide en F1[cite: 21, 22, 29].
* **P5 (Equipo):** Definir la forma jurídica en caso de constitución real de la empresa[cite: 29].
* **P7 (Drake):** Ejecutar prueba de seguridad por roles con Spring Security[cite: 22, 29].
* **P8 (Drake):** Ejecutar prueba de concurrencia en reservas solapadas[cite: 22, 29].

---

## 7. Estructura del Repositorio

* `/README.md` — Visión general del proyecto, arquitectura, planificación, decisiones vigentes y pendientes[cite: 1, 33].
* `/docs/01-contexto-
