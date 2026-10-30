# Propuesta de Proyecto, MVP y Características Iniciales

## 1. Destinatarios del Producto
- Público entusiasta del motor que quiera probar vehículos de distintas gamas, potencia y permisos de conducir.
- Personas viajeras que necesiten transporte para sus desplazamientos.
- Empresas de organización de eventos que requieran vehículos especiales o furgonetas.

## 2. Diferenciación del Producto
GoRide se diferencia de otras páginas web por incorporar un catálogo muy extenso adaptado a todo tipo de público, ser intuitivo y contar con un filtrado avanzado potente para que el consumidor elija el vehículo adecuado.

## 3. Definición del MVP (3 Funcionalidades Principales)
1. **Catálogo interactivo con filtrado avanzado:** Búsqueda personalizada por tipo de vehículo, combustible, plazas y permiso necesario. El administrador gestiona la flota. *(Aborda Necesidad 2)*.
2. **Motor de cálculo de presupuesto dinámico y reserva:** Algoritmo que calcula el precio estimado en tiempo real según días y estimación de kilómetros. *(Aborda Necesidad 1)*.
3. **Gestión de perfiles y registro de documentación:** Autenticación segura con Spring Security para almacenar datos del usuario y vincular el carnet a sus reservas. *(Aborda Necesidades 3 y 4)*.

## 4. Fuera de Alcance (Out of Scope)
- Geolocalización GPS en tiempo real.
- Aplicación móvil nativa (iOS/Android).
- Pasarela de pago bancaria externa en vivo.

## 5. Características Iniciales
- **Características funcionales:** Registro, login, filtros combinados y fórmulas de cálculo de tarifas.
- **Condicionantes técnicos:** Arquitectura Cliente-Servidor (Java Spring Boot + MySQL + HTML/JS/CSS) con persistencia mediante Spring Data JPA.
- **Criterios de calidad:** Diseño adaptativo (responsive), tiempos de respuesta inferiores a 2 segundos y cumplimiento del RGPD en la custodia de datos personales y contraseñas.
