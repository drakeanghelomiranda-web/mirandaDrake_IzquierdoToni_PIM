# Nombre Empresa: GoRide - Web de Alquiler de Vehiculos

> **Modulo:** Proyecto Intermodular (PIM)  
> **Curso Academico:** 2025-2026 | **Ciclo:** Desarrollo de Aplicaciones Web (DAW)  
> **Equipo:** Drake Anghelo Miranda Alvarez y Toni Izquierdo Carbonell  

---

## 1. Introduccion del Proyecto

El proyecto consiste en una Web web de alquiler de vehiculos. El nombre de la empresa es GoRide, una empresa SL (Sociedad Limitada) que se encarga de rent a car que usara la web para mostrar sus vehiculos para alquilar y gestionar las reservas.

### Problemas que se identifico:
1. **Hay poco catalogo de vehiculos y falta de filtros necesarios para facilitar la busqueda:** La mayoria de las webs de alquiler de vehiculos suelen mostrar una lista basica donde el cliente tiene que revisar vehiculo por vehiculo para saber todos sus detalles y si se adapta a lo que busca.
2. **Falta de seguridad en los pagos en linea:** La falta de sistemas de pago seguros y verificados puede generar desconfianza a los clientes a la hora de confirmar y pagar su reserva del vehiculo por internet.

### Personas afectados:
* Viajeros, grupos de amigos y familias que necesitan un vehiculo para un viaje.
* Empresas y de organizacion de eventos que necesitan furgonetas o vehiculos especiales.
* Aficionados al motor que quieren probar vehiculos de distintas gamas.

---

## 2. Propuesta de proyecto y MVP

El proyecto consiste en la creacion de una pagina web para GoRide destinada al publico entusiasta de los vehiculos, personas viajeras y empresas de organizacion de eventos. NOfrecemos un catalogo muy extenso, interactivo, intuitivo y con un filtrado avanzado potente.

### Definicion de las 3 Funcionalidades Principales del MVP:
1. **Catalogo interactivo con filtrado avanzado:** Busqueda personalizada segun el tipo de vehiculo, combustible, numero de plazas y permiso de conducir necesario. El administrador gestiona la flota.
2. **Motor de calculo de presupuesto dinamico y reserva:** Calcula el precio estimado en tiempo real de las tarifas segun los dias seleccionados y la tasa de kilometraje previsto.
3. **Gestion de perfiles de usuario y registro de documentacion:** Sistema de autenticacion y registro seguro (Spring Security) para almacenar los datos del usuario y vincular la documentacion del carnet a sus reservas.

---

## 3. Fuera de alcance

* Geolocalizacion GPS en tiempo real.
* Aplicacion movil nativa (iOS/Android).

---

## 4. Sector, empresas y entorno

### Comparativa de 4 modelos de empresas TIC
1. **Software Factory / Desarrollo a Medida:** Crean aplicaciones desde cero segun la peticion del cliente (frontend/backend, UX/UI, gestion de proyectos).
2. **Empresa SaaS:** Desarrollan software estandarizado en alquiler por suscripcion (soporte, producto, ventas).
3. **Marketplaces y Plataformas:** Sistemas que conectan oferta y demanda en tiempo real (busqueda, pagos, seguridad).
4. **Agencia E-commerce:** Portales transaccionales y catalogos donde prima la velocidad, diseno y navegacion.

### Modelo elegido: Software Factory
Encajamos como **Software Factory / Desarrollo a medida** al requerir una arquitectura desde cero con base de datos solida y un motor de filtros ajustado a nuestras reglas.

* **Diferenciacion clave:** Separacion entre la empresa TIC desarrolladora (equipo tecnico) y el cliente final (empresa de rent a car GoRide).
* **Areas de la empresa desarrolladora:** Diseno UX/UI, Desarrollo de Software (Frontend y Backend) y Mantenimiento y Soporte.
---

## 5. Caracteristicas iniciales

* **Caracteristicas funcionales:** Registro, login, filtros combinados, formulas de calculo de tarifas.
* **Condicionantes tecnicos:** Arquitectura Cliente-Servidor (Java Spring Boot + MySQL + HTML/JS/CSS), persistencia con Spring Data JPA.
* **Criterios de calidad:** Diseno adaptativo (responsive), tiempos de respuesta < 2s, cumplimiento del RGPD en la custodia de datos personales y contraseñas.

---

## 6. Organizacion del repositorio

* `/` : Raiz del proyecto con el archivo `README.md`.
* `/docs` : Documentacion detallada del analisis del sector, necesidades y DAFO:
  * `01-contexto-y-necesidades.md`
  * `02-mvp-y-alcance.md`
  * `03-sector-y-dafo.md`
