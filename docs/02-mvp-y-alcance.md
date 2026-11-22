# 02 · Propuesta, MVP y alcance

> Última revisión: 22/11/2026. Este fichero recoge el alcance vigente. Las decisiones están en `decisiones-y-pendientes.md` (se citan como D1…D10) y las necesidades en `01-contexto-y-necesidades.md` (N1…N5).

## 1. Propuesta

- **Tipo de producto:** aplicación web con servidor y base de datos para el alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales).
- **Público:** viajeros, grupos de amigos y familias; empresas de catering y eventos; aficionados al motor.
- **Perfiles de usuario (D8):** cliente y administrador.
- **Necesidad principal:** alquilar un vehículo adecuado, legal para el conductor y con coste claro, sin dobles reservas.
- **Propuesta de valor:** muestra solo los vehículos que el usuario puede conducir e informa del precio total antes de reservar.
- **Elemento diferencial:** filtrado por permiso de conducir y cálculo de precio total transparente.
- **Cliente final:** GoRide (rent a car). El equipo es la empresa desarrolladora.

## 2. Tres funcionalidades principales del MVP

### C1 · Catálogo con filtros y gestión de flota → N2

- El cliente filtra por tipo, combustible, plazas y permiso necesario.
- El administrador da de alta, edita y retira vehículos.
- El filtro por permiso usa la tabla permiso ↔ tipo de vehículo (D3).

**Criterios de aceptación:**
- Con un permiso seleccionado, el catálogo no muestra vehículos que ese permiso no autoriza.
- Los filtros se pueden combinar.
- Un vehículo retirado no aparece en el catálogo.

### C2 · Presupuesto, disponibilidad y reserva → N1, N3

- Calcula el total antes de confirmar: **días × tarifa diaria + km estimados × tarifa por km**, sin extras, fianza ni seguro (D2).
- Comprueba disponibilidad y rechaza solapes con otra reserva confirmada del mismo vehículo (D5).
- Permite confirmar, consultar y cancelar la reserva. No hay cobro online: el pago es al recoger el vehículo (D1).
- El administrador consulta las reservas.

**Criterios de aceptación:**
- El total aparece antes del botón de confirmar y coincide con un cálculo manual.
- Dos reservas del mismo vehículo en fechas solapadas no pueden confirmarse a la vez, ni siquiera con peticiones simultáneas.
- Una reserva cancelada deja libres las fechas.

### C3 · Cuenta, documentación y comprobación de permiso → N2, N4, N5

- Registro y acceso seguro con Spring Security; contraseñas con hash.
- El cliente guarda sus datos para reutilizarlos. **Del carnet solo se guarda la categoría y la caducidad, sin imagen** (D4).
- El sistema comprueba que la categoría declarada es compatible con el vehículo; si no lo es, bloquea la reserva y muestra el motivo (D3).
- El administrador revisa el permiso al entregar el vehículo (D4).

**Criterios de aceptación:**
- Un usuario registrado hace una segunda reserva sin reintroducir sus datos.
- Un cliente no puede abrir una página de administrador.
- La base de datos solo contiene los campos del apartado 5.

## 3. Roadmap y fuera de alcance

| Roadmap (versiones futuras) | Fuera de alcance (ahora) |
|---|---|
| Pasarela de pago en modo de pruebas, informes PDF para seguros, mejoras de uso en móvil, asistente de búsqueda (D7) | Pagos reales, app móvil nativa, GPS en tiempo real, integraciones con terceros, fianza y seguros |

## 4. Características iniciales

**Funcionales:** filtros combinados; cálculo de tarifa; comprobación de disponibilidad; cancelación; registro, login y roles; comprobación de permiso.

**Condicionantes técnicos (D6, D9):** arquitectura cliente-servidor; Spring Boot, Spring Data JPA, Spring Security, MySQL; HTML5, CSS3 y JavaScript; despliegue local en la primera versión. Son un punto de partida, no un cierre.

**Calidad (D10):** sin umbrales numéricos de rendimiento hasta una primera medición. Controles comprobables en el dossier, apartado 9.8: solapes, permiso, precio, seguridad de acceso, privacidad, usabilidad y accesibilidad.

## 5. Datos necesarios (nivel de diseño, no ERD completo)

- **Vehículo:** tipo, combustible, plazas, permiso requerido, tarifa por día, tarifa por km.
- **Usuario:** credenciales (con hash), rol.
- **Perfil:** datos de contacto, categoría y caducidad del permiso.
- **Reserva:** usuario, vehículo, fechas, total, estado (pendiente, confirmada, cancelada; D5).
- **Tabla de compatibilidad:** categoría de permiso ↔ tipo de vehículo.

## 6. Reglas por confirmar

Estas reglas no están decididas. Hasta que el equipo las acuerde, no se tratan como hechos:

- **Solape de fechas:** si el día de devolución cuenta como ocupado o libre. *Propuesta:* se reserva por días completos y ambos extremos son inclusivos (`inicio_nuevo <= fin_existente` y `fin_nuevo >= inicio_existente`).
- **Quién confirma:** *propuesta:* la reserva se crea como pendiente y pasa a confirmada de forma automática si supera la comprobación de permiso y de disponibilidad.
- **Límite de km o tarifa mínima:** sin decidir.
- **Tabla completa permiso ↔ vehículo:** por redactar, con una fuente (RD 818/2009).
