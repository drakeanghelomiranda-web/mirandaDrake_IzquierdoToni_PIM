# 02 · Propuesta, MVP y alcance

> Última revisión: 22/11/2026[cite: 31]. Este fichero recoge el alcance vigente[cite: 31]. Las decisiones están en `04-decisiones-hipotesis-pendientes.md` (se citan como D1…D10) y las necesidades en `01-contexto-y-necesidades.md` (N1…N5)[cite: 29, 31].

## 1. Propuesta

- **Tipo de producto:** aplicación web con servidor y base de datos para el alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales)[cite: 13, 31].
- **Público:** viajeros, grupos de amigos y familias; empresas de catering y eventos; aficionados al motor[cite: 13, 31].
- **Perfiles de usuario (D8):** cliente y administrador[cite: 13, 31].
- **Necesidad principal:** alquilar un vehículo adecuado, legal para el conductor y con coste claro, sin dobles reservas[cite: 13, 31].
- **Propuesta de valor:** muestra solo los vehículos que el usuario puede conducir e informa del precio total antes de reservar[cite: 13, 31].
- **Elemento diferencial:** filtrado por permiso de conducir y cálculo de precio total transparente[cite: 13, 31].
- **Cliente final:** GoRide (*rent a car*)[cite: 8, 31]. El equipo es la empresa desarrolladora (*software factory*)[cite: 9, 31].

## 2. Tres funcionalidades principales del MVP

### C1 · Catálogo con filtros y gestión de flota → N2

- El cliente filtra por tipo, combustible, plazas y permiso necesario[cite: 13, 31].
- El administrador da de alta, edita y retira vehículos[cite: 13, 31].
- El filtro por permiso usa la tabla `permiso ↔ tipo de vehículo` (D3)[cite: 29, 31].

**Criterios de aceptación:**
- Con un permiso seleccionado, el catálogo no muestra vehículos que ese permiso no autoriza[cite: 19, 31].
- Los filtros se pueden combinar[cite: 31].
- Un vehículo retirado no aparece en el catálogo[cite: 31].

### C2 · Presupuesto, disponibilidad y reserva → N1, N3

- Calcula el total antes de confirmar: **días × tarifa diaria + km estimados × tarifa por km**, sin extras, fianza ni seguro (D2)[cite: 29, 31].
- Comprueba disponibilidad y rechaza solapes con otra reserva confirmada del mismo vehículo mediante regla de extremos inclusivos (`inicio_nuevo <= fin_existente` y `fin_nuevo >= inicio_existente`, D5)[cite: 26, 29, 31].
- Permite confirmar, consultar y cancelar la reserva. No hay cobro online: el pago es al recoger el vehículo (D1)[cite: 13, 29, 31].
- El administrador consulta las reservas[cite: 13, 31].

**Criterios de aceptación:**
- El total aparece antes del botón de confirmar y coincide con un cálculo manual[cite: 19, 31].
- Dos reservas del mismo vehículo en fechas solapadas no pueden confirmarse a la vez, ni siquiera con peticiones simultáneas[cite: 19, 31].
- Una reserva cancelada deja libres las fechas[cite: 31].

### C3 · Cuenta, documentación y comprobación de permiso → N2, N4, N5

- Registro y acceso seguro con Spring Security; contraseñas con hash BCrypt[cite: 18, 31].
- El cliente guarda sus datos para reutilizarlos. **Del carnet solo se guarda la categoría y la caducidad, sin imagen** (D4)[cite: 26, 29, 31].
- El sistema comprueba que la categoría declarada es compatible con el vehículo; si no lo es, bloquea la reserva y muestra el motivo (D3)[cite: 29, 31].
- El administrador revisa el permiso físico al entregar el vehículo (D4)[cite: 29, 31].

**Criterios de aceptación:**
- Un usuario registrado hace una segunda reserva sin reintroducir sus datos[cite: 19, 31].
- Un cliente no puede abrir una página de administrador[cite: 25, 31].
- La base de datos solo contiene los campos del apartado 5[cite: 25, 31].

## 3. Roadmap y fuera de alcance

| Roadmap (versiones futuras) | Fuera de alcance (ahora) |
|---|---|
| Pasarela de pago en modo de pruebas, informes PDF para seguros, mejoras de uso en móvil, asistente de búsqueda (D7)[cite: 14, 29, 31] | Pagos reales, app móvil nativa, GPS en tiempo real, integraciones con terceros, fianza y seguros[cite: 14, 29, 31] |

## 4. Características iniciales

- **Funcionales:** filtros combinados; cálculo de tarifa; comprobación de disponibilidad; cancelación; registro, login y roles; comprobación de permiso[cite: 14, 31].
- **Condicionantes técnicos (D6, D9):** arquitectura cliente-servidor; Java 17/21, Spring Boot 3.x, Spring Data JPA, Spring Security, MySQL 8; HTML5, CSS3 y JavaScript; despliegue local en la primera versión[cite: 14, 19, 21, 31].
- **Calidad (D10):** sin umbrales numéricos de rendimiento hasta una primera medición[cite: 29, 31]. Controles comprobables en el dossier (apartado 15): solapes, permiso, precio, seguridad de acceso, privacidad y usabilidad[cite: 7, 24, 25, 31].

## 5. Datos necesarios (nivel de diseño, no ERD completo)

- **Vehículo:** tipo, combustible, plazas, permiso requerido, tarifa por día, tarifa por km[cite: 24, 31].
- **Usuario:** credenciales (con hash BCrypt), rol[cite: 18, 24, 31].
- **Perfil:** datos de contacto, categoría y caducidad del permiso[cite: 24, 31].
- **Reserva:** usuario, vehículo, fechas, total, estado (`pendiente`, `confirmada`, `cancelada`; D5)[cite: 24, 26, 31].
- **Tabla de compatibilidad:** categoría de permiso ↔ tipo de vehículo[cite: 18, 31].

## 6. Reglas por confirmar en Fase 1

Estas reglas están pendientes de cierre definitivo antes de programar la lógica de negocio[cite: 20, 31]:

- **Confirmación de reserva:** *propuesta:* la reserva se crea como `pendiente` y pasa a `confirmada` de forma automática si supera la comprobación de permiso y de disponibilidad[cite: 31].
- **Tarifas exactas, redondeo e IVA:** confirmar con la docente (en el rol de cliente GoRide) las tarifas de la flota de demostración y si se muestra IVA desglosado[cite: 18, 21, 22].
- **Tabla completa permiso ↔ vehículo:** redactar la matriz exacta basada en el RD 818/2009 (incluyendo equivalencia B > 3 años con A1 en España)[cite: 18, 20, 31].
