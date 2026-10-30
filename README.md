# GoRide - Plataforma Web de Alquiler de Vehiculos

> **Modulo:** Proyecto Intermodular (PIM - UT1)  
> **Curso Academico:** 2025-2026 | **Ciclo:** Desarrollo de Aplicaciones Web (DAW)  
> **Equipo:** Drake Anghelo Miranda Alvarez, Toni Izquierdo Carbonell, [Nombre del 3er Integrante]

---

## 1. Contexto del Proyecto y Problema Real

GoRide es un proyecto enfocado en el desarrollo de una plataforma web transaccional para la gestion y alquiler de vehiculos (turisticos, comerciales y de gama especial).

El proyecto resuelve tres problemas clave detectados en el sector:
1. **Opacidad en tarifas:** Falta de calculo transparente del coste final segun el uso y kilometraje estimado del usuario.
2. **Catalogos rigidos sin filtros clave:** Dificultad para filtrar la flota segun los requisitos legales del conductor (tipo de carnet de conducir B, A2, C).
3. **Ineficiencia en la gestion documental:** Repeticion en la recopilacion de datos de la licencia de conducir en cada reserva.

---

## 2. Alcance del MVP (3 Funcionalidades Principales)

Para garantizar la viabilidad tecnica dentro de los plazos academicos, la propuesta inicial se acota a un MVP de 3 funcionalidades principales:

1. **Catalogo interactivo con filtrado avanzado:** Busqueda combinada por tipo de vehiculo, combustible, plazas y permiso de conducir necesario.
2. **Motor de calculo de presupuesto dinamico y reserva:** Algoritmo en servidor que calcula el precio estimado en tiempo real segun los dias seleccionados y la tasa de kilometraje previsto.
3. **Gestion de perfiles de usuario y registro de documentacion:** Sistema de autenticacion seguro (Spring Security) para almacenar los datos del usuario y vincular la informacion de su carnet de conducir a las reservas.

---

## 3. Fuera de Alcance (Out of Scope)

* Aplicacion movil nativa (iOS/Android).
* Geolocalizacion GPS en tiempo real de los vehiculos.
* Pasarela de pago bancaria externa integrada en vivo.

---

## 4. Tecnologias y Arquitectura

* **Modelo TIC:** Software Factory / Desarrollo a medida.
* **Backend:** Java, Spring Boot, Spring Data JPA, Spring Security.
* **Base de Datos:** MySQL.
* **Frontend:** HTML5, CSS3, JavaScript (Fetch API).
* **Control de Versiones:** Git y GitHub.

---

## 5. Organizacion del Repositorio

* `/` : Raiz del proyecto con el codigo fuente y configuracion general.
* `README.md` : Resumen ejecutivo y sistema de contexto inicial.
* `/docs` : Documentacion tecnica del analisis de sector, modelo DAFO y arquitectura base.
