# GoRide - Plataforma Web de Alquiler de Vehiculos

> **Modulo:** Proyecto Intermodular (PIM - UT1)  
> **Curso Academico:** 2025-2026 | **Ciclo:** Desarrollo de Aplicaciones Web (DAW)  
> **Equipo:** Drake Anghelo Miranda Alvarez, Toni Izquierdo Carbonell  

---

## 1. Contexto del Proyecto

GoRide es una plataforma web de alquiler de vehiculos (turismos, furgonetas, motos y vehiculos especiales) que cuenta con servidor web y base de datos. El sistema esta pensado para ser utilizado por una empresa ficticia de rent a car (GoRide) para mostrar su flota y gestionar las reservas de los usuarios.

### Problemas que aborda el proyecto:
1. **Poco catalogo y falta de filtros clave:** Las webs habituales muestran listas basicas que obligan al usuario a revisar vehiculo por vehiculo para ver si se adapta a lo que busca.
2. **Falta de seguridad en las transacciones en linea:** Genera desconfianza al cliente al confirmar y pagar sus reservas por Internet.

### Colectivos afectados:
* Viajeros, familias y grupos de amigos que necesitan un vehiculo para un viaje.
* Empresas de catering y eventos que requieren furgonetas o vehiculos especiales.
* Aficionados al motor que quieren probar vehiculos de distintas gamas.
* La propia empresa de alquiler (GoRide), que pierde reservas por la desconfianza del usuario.

### Evolucion respecto a la UT0:
Se simplifica la propuesta a un MVP de 3 capacidades principales para garantizar la viabilidad tecnica en los plazos del ciclo formativo. La pasarela de pago se aplaza para el roadmap futuro.

---

## 2. Alcance del MVP (3 Funcionalidades Principales)

1. **Catalogo interactivo con filtrado avanzado:** Busqueda personalizada segun el tipo de vehiculo, combustible, numero de plazas y permiso de conducir necesario. Incluye la gestion de la flota por parte del administrador.
2. **Motor de calculo de presupuesto dinamico y reserva:** Algoritmo de tarifas que calcula el precio estimado en tiempo real segun los dias seleccionados y la tasa de kilometraje previsto.
3. **Gestion de perfiles de usuario y registro de documentacion:** Sistema de autenticacion y registro seguro con Spring Security para almacenar los datos del usuario y vincular la documentacion del carnet a sus reservas.

---

## 3. Fuera de Alcance (Out of Scope)

* Geolocalizacion GPS en tiempo real de los vehiculos.
* Aplicacion movil nativa (iOS/Android).
* Pasarela de pagos en linea integrada en vivo.

---

## 4. Clasificacion del Modelo TIC

* **Modelo de empresa:** Software Factory / Desarrollo a medida. Se disenara desde cero una arquitectura con base de datos solida y un motor de filtros interactivo ajustado a reglas de negocio especificas.
* **Diferenciacion clave:** Se separa la empresa TIC desarrolladora (equipo tecnico que programa el sistema) del cliente final (empresa de rent a car GoRide que opera la plataforma).
* **Areas internas de la empresa desarrolladora:**
  * Diseno UX/UI.
  * Desarrollo de Software (Frontend y Backend).
  * Mantenimiento y Soporte.

---

## 5. Caracteristicas Tecnicas Iniciales

* **Caracteristicas funcionales:** Registro, login, filtros combinados y formulas de calculo de tarifas.
* **Condicionantes tecnicos:** Arquitectura Cliente-Servidor (Java Spring Boot + MySQL + HTML/JS/CSS) con persistencia mediante Spring Data JPA.
* **Criterios de calidad:** Diseno adaptativo (responsive), tiempos de respuesta inferiores a 2 segundos y cumplimiento del RGPD en la custodia de datos personales y contraseñas.

---

## 6. Organizacion del Repositorio

* `/` : Raiz del proyecto con la configuracion general.
* `README.md` : Sistema de contexto del proyecto.
* `/docs` : Documentacion del analisis de sector, necesidades, DAFO y planificacion.

---

## ⚠️ ALERTAS: INFORMACION PENDIENTE DE COMPLETAR

> Las siguientes secciones contienen datos incompletos en el borrador original que deben resolverse antes de la entrega final:

1. **Integrantes del equipo:** El enunciado requiere un equipo de **3 personas**. En la portada solo figuran Drake Anghelo Miranda Alvarez y Toni Izquierdo Carbonell. Falta incluir al tercer integrante o la autorizacion docente.
2. **Conclusion estrategica del DAFO:** Falta redactar la frase final de cierre del apartado 3.3 que justifique formalmente el alcance elegido para el proyecto.
3. **Punto 3.6 (Marco empresarial - Tabla legal):** Falta completar en el borrador la tabla resumen con los detalles de las obligaciones laborales, fiscales y de PRL (se dejaron unicamente las instrucciones generales de la plantilla).
4. **Enlace al repositorio GitHub (Punto 9):** El enlace proporcionado apunta a la pantalla de configuracion privada (`/settings/access?...`). Debe sustituirse por la URL publica principal del repositorio: `https://github.com/drakeanghelomiranda-web/mirandaDrake_IzquierdoToni_PIM`.
