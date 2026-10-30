# GoRide - Web de Alquiler de Vehículos

> **Módulo:** Proyecto Intermodular (PIM)  
> **Curso Académico:** 2025-2026 | **Ciclo:** Desarrollo de Aplicaciones Web (DAW)  
> **Equipo:** Drake Anghelo Miranda Álvarez y Toni Izquierdo Carbonell  

---

## 1. Introducción del Proyecto

El proyecto consiste en una plataforma web de alquiler de vehículos (turismos, furgonetas, motos y vehículos especiales) con parte de servidor web y base de datos. El nombre de la empresa es GoRide, una empresa SL (Sociedad Limitada) de rent a car ficticia que usará la web para mostrar sus vehículos para alquilar y gestionar las reservas.

### Problemas identificados:
1. **Poco catálogo de vehículos y falta de filtros clave:** La mayoría de las webs de alquiler de vehículos suelen mostrar una lista básica donde el cliente tiene que revisar vehículo por vehículo para saber todos sus detalles y si se adapta a lo que busca.
2. **Falta de seguridad en los pagos en línea:** La falta de sistemas de pago seguros y validados genera desconfianza a los clientes a la hora de confirmar y pagar su reserva del vehículo por internet.

### Personas y colectivos afectados:
* Viajeros, grupos de amigos y familias que necesitan un vehículo para un viaje.
* Empresas de catering y de organización de eventos que necesitan furgonetas o vehículos especiales.
* Aficionados al motor que quieren probar vehículos de distintas gamas.
* La propia empresa de alquiler (GoRide), que pierde reservas por la desconfianza del usuario y atiende consultas evitables.

---

## 2. Propuesta de proyecto y MVP

El proyecto consiste en la creación de una página web para GoRide destinada al público entusiasta de los vehículos, personas viajeras y empresas de organización de eventos. Ofrecemos un catálogo muy extenso, interactivo, intuitivo y con un filtrado avanzado potente para que el consumidor elija el vehículo adecuado.

### Definición de las 3 Funcionalidades Principales del MVP:
1. **Catálogo interactivo con filtrado avanzado:** Búsqueda personalizada según el tipo de vehículo, combustible, número de plazas y permiso de conducir necesario. El administrador gestiona la flota.
2. **Motor de cálculo de presupuesto dinámico y reserva:** Algoritmo de tarifas que calcula el precio estimado en tiempo real según los días seleccionados y la tasa de kilometraje previsto.
3. **Gestión de perfiles de usuario y registro de documentación:** Sistema de autenticación y registro seguro (Spring Security) para almacenar los datos del usuario y vincular la documentación del carnet a sus reservas.

---

## 3. Fuera de alcance (Out of scope)

* Geolocalización GPS en tiempo real.
* Aplicación móvil nativa (iOS/Android).
* Pasarela de pago bancaria externa integrada en vivo (se pospone para garantizar la viabilidad técnica del MVP en los plazos del ciclo).

---

## 4. Sector, empresas y entorno

### Comparativa de 4 modelos de empresas TIC
1. **Software Factory / Desarrollo a Medida:** Crean aplicaciones desde cero según la petición del cliente (frontend/backend, UX/UI, gestión de proyectos).
2. **Empresa SaaS:** Desarrollan software estandarizado en alquiler por suscripción (soporte, producto, ventas).
3. **Marketplaces y Plataformas:** Sistemas que conectan oferta y demanda en tiempo real (búsqueda, pagos, seguridad).
4. **Agencia E-commerce:** Portales transaccionales y catálogos donde prima la velocidad, diseño y navegación.

### Modelo elegido: Software Factory
Encajamos como **Software Factory / Desarrollo a medida** al requerir una arquitectura desde cero con base de datos sólida y un motor de filtros ajustado a nuestras reglas de negocio.

* **Diferenciación clave:** Separación entre la empresa TIC desarrolladora (equipo técnico que programa el sistema web, la lógica de servidor y la BBDD) y el cliente final (empresa de rent a car GoRide que opera la flota).
* **Áreas de la empresa desarrolladora:** Diseño UX/UI, Desarrollo de Software (Frontend y Backend), Mantenimiento y Soporte.

---

## 5. Características iniciales

* **Características funcionales:** Registro, login, filtros combinados, fórmulas de cálculo de tarifas.
* **Condicionantes técnicos:** Arquitectura Cliente-Servidor (Java Spring Boot + MySQL + HTML/JS/CSS), persistencia con Spring Data JPA.
* **Criterios de calidad:** Diseño adaptativo (responsive), tiempos de respuesta < 2s, cumplimiento del RGPD en la custodia de datos personales y contraseñas.

---

## 6. Marco empresarial y ayudas

* **Obligaciones Laborales:** Alta en Seguridad Social (RETA para autónomos o Régimen General) y aplicación del *Convenio Colectivo Estatal de Empresas de Consultoría, Tecnologías de la Información y Estudios de Mercado* (BOE-A-2023-17238).
* **Obligaciones Fiscales:** Alta en el IAE bajo el *Epígrafe 844 (Servicios de tecnologías de la información)*, liquidaciones trimestrales de IVA, Impuesto de Sociedades o IRPF.
* **Prevención de Riesgos Laborales (PRL):** Cumplimiento de la Ley 31/1995, evaluación ergonómica de los puestos informáticos y seguridad visual/motora.
* **Ayudas y Subvenciones:**
  * **Kit Digital (Acelera Pyme):** Financiación para la digitalización y desarrollo web de Pymes y autónomos.
  * **ENISA Jóvenes Emprendedores:** Préstamo participativo para startups e iniciativas innovadoras.

---

## 7. Guión inicial de trabajo

| Fase | Descripción | Hito de cierre | Recursos y Asignación | Tiempo orientativo |
|---|---|---|---|---|
| **1. Análisis y Diseño UI/UX y BBDD** | Concretar requisitos, diseñar interfaces y modelar la base de datos | Diagrama ERD y wireframes aprobados | Figma, draw.io (Drake y Toni) | 15% |
| **2. Arquitectura base** | Creación del proyecto base, dependencias y conexión BBDD | Proyecto Spring Boot conectado a MySQL | IntelliJ, Java, Spring Boot, MySQL (Drake) | 10%-15% |
| **3. Desarrollo Core MVP** | Programación de entidades, catálogo interactivo y motor de tarifas | Módulo de catálogo y cálculo funcional | Java, Spring Data JPA, HTML/CSS/JS (Drake y Toni) | 35% |
| **4. Autenticación y Perfiles** | Sistema de registro, acceso seguro y subida de carnet | Registro/Login seguro funcional | Spring Security, RGPD (Toni) | 25% |
| **5. Pruebas y Despliegue** | Pruebas generales, corrección de errores y documentación | Web validada y documentada | Entorno local, Git, Plan de pruebas (Drake y Toni) | 10%-15% |

---

## 8. Conclusione

### Conclusión final
Para sacar adelante el proyecto GoRide de forma ordenada, hemos acordado la arquitectura clásica Cliente-Servidor en Java Spring Boot y MySQL, dando prioridad absoluta al MVP (catálogo con filtros por carnet, calculador dinámico y Spring Security) y organizándonos internamente como una Software Factory. En definitiva, GoRide sirve para transformar la experiencia de alquiler de vehículos, resolviendo de forma directa la opacidad en los precios y la falta de búsquedas adaptadas a los requisitos legales de los conductores.


---

## 9. Organización del repositorio y enlace

* `/` : Raíz del proyecto con el archivo `README.md`.
* `/docs` : Documentación detallada del análisis del sector, necesidades y DAFO:
  * `01-contexto-y-necesidades.md`
  * `02-mvp-y-alcance.md`
  * `03-sector-y-dafo.md`
