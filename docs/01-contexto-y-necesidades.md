# Contexto del Proyecto y Análisis de Necesidades

## 1. Contexto del Proyecto y Ámbito
El proyecto consiste en una plataforma web de alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales) con parte de servidor web y base de datos.
* **Empresa cliente:** GoRide, una corporación de rent a car ficticia que usará la plataforma para mostrar su flota y gestionar las reservas.

## 2. Problemas Identificados
1. **Poco catálogo de vehículos y falta de filtros clave:** La mayoría de las webs de alquiler muestran una lista básica donde el usuario tiene que revisar vehículo por vehículo para saber si se adapta a sus necesidades.
2. **Falta de seguridad en las transacciones en línea:** La ausencia de sistemas de pago seguros y validados genera desconfianza en los clientes a la hora de confirmar y pagar su reserva por Internet.

## 3. Personas y Colectivos Afectados
* Viajeros, grupos de amigos y familias que necesitan un vehículo para un viaje.
* Empresas de catering y de organización de eventos que necesitan furgonetas o vehículos especiales.
* Aficionados al motor que quieren probar vehículos de distintas gamas.
* La propia empresa de alquiler (GoRide), que pierde reservas por la desconfianza del usuario y atiende consultas evitables.

## 4. Evolución respecto a la UT0
Mantenemos la propuesta original de GoRide presentada en la UT0. En la UT1 concretamos la parte técnica: aunque en la UT0 identificamos la falta de seguridad en transacciones como un problema, para garantizar la viabilidad del MVP en los plazos del ciclo dejamos la pasarela de pago para el roadmap futuro y nos centramos exclusivamente en tres capacidades:
* Catálogo interactivo con filtrado avanzado.
* Motor de cálculo de presupuesto dinámico y reserva.
* Gestión de perfiles de usuario y registro de documentación (Spring Security).

## 5. Tabla de Necesidades
* **Necesidad 1 (Importancia Alta):** Conocer el coste total estimado de forma transparente antes de reservar (días, kilómetros, extras).
  * *Afectados:* Viajeros, familias, eventos.
  * *Evidencia:* UT0 (Falta de cálculo transparente).
* **Necesidad 2 (Importancia Alta):** Encontrar un vehículo que encaje con las necesidades y requisitos legales (carnet) sin revisarlos uno a uno.
  * *Afectados:* Todos los usuarios.
  * *Evidencia:* UT0 (Poco catálogo y falta de filtros clave).
* **Necesidad 3 (Importancia Media/Alta):** No repetir datos y documentación en cada reserva para agilizar el proceso.
  * *Afectados:* Usuarios y empresas recurrentes.
  * *Evidencia:* Estudio del mercado y valoración de posible fallo potencial.
* **Necesidad 4 (Importancia Media - a aplicar al final):** Aplicar una plataforma de pagos que sea de confianza y gestionar los datos del cliente de forma segura.
  * *Afectados:* Todos los usuarios.
  * *Evidencia:* UT0 (Falta de seguridad en transacciones); RGPD.

## 6. Oportunidades Identificadas
* **Transparencia Tarifaria Dinámica (Prioridad Alta):** Elimina sorpresas de precio en el mostrador (Abarca Necesidad 1).
* **Búsqueda Guiada por Requisitos Legales (Prioridad Alta):** Evita que el usuario alquile un vehículo que legalmente no puede conducir, ej. motos A2 vs A (Abarca Necesidad 2).
* **Fidelización y Gestión de Perfil Único (Prioridad Media):** Agiliza reservas recurrentes sin reintroducir datos (Abarca Necesidades 3 y 4).
* **Asistente de búsqueda rápida / IA / Filtros avanzados (Prioridad Baja/Media):** Agiliza búsquedas complejas para el usuario (Abarca Necesidad 2).
