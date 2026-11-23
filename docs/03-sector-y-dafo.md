# 03 · Sector, Modelos TIC y Matriz DAFO

> Última revisión: 22/11/2026[cite: 29].

## 1. Comparativa del Sector TIC (4 Modelos)
1. **Software Factory / Desarrollo a Medida:** Crean aplicaciones desde cero ajustándose al 100% a lo que pide cada cliente, con departamentos de frontend/backend, UX/UI y gestión de proyectos[cite: 9, 30].
2. **Empresa de Producto SaaS:** Desarrollan un software propio estandarizado y lo alquilan mediante suscripción a múltiples clientes[cite: 9, 30].
3. **Desarrolladora de Marketplaces y Plataformas:** Especializadas en conectar oferta y demanda en tiempo real, enfocadas en motores de búsqueda y seguridad[cite: 9, 30].
4. **Agencia de Desarrollo Web / E-commerce:** Enfocadas en portales transaccionales y catálogos interactivos priorizando velocidad y experiencia visual[cite: 9, 30].

## 2. Encaje de la Empresa Desarrolladora
La empresa que desarrolla el producto encaja como una **Software Factory / Desarrollo a medida**, ya que requiere diseñar desde cero una arquitectura con base de datos sólida y un motor de filtros interactivo ajustado a las reglas de negocio del cliente[cite: 9, 30].

* **Diferenciación clave:** Se separa formalmente a la empresa TIC desarrolladora (equipo técnico que programa la web, la lógica de servidor y la BBDD) del cliente final (la empresa de *rent a car* GoRide que opera las reservas y flota)[cite: 9, 30].
* **Áreas de la empresa desarrolladora (agrupadas para equipo de 2 personas):**
  * Gestión de proyecto y análisis[cite: 10].
  * Diseño UX/UI y Desarrollo Frontend (Toni Izquierdo)[cite: 10, 22].
  * Desarrollo Backend, Seguridad y BBDD (Drake Miranda)[cite: 10, 22].

## 3. Matriz DAFO

### Factores Positivos
* **Fortalezas (Internas):**
  1. Filtro por permiso de conducir y requisitos legales, poco habitual en webs generalistas[cite: 12].
  2. Precio total estimado transparente antes de confirmar la reserva[cite: 12].
* **Oportunidades (Externas):**
  1. Crecimiento de la demanda de alquiler para viajes, familias y eventos (Fuente: ESDiario Motor, `https://www.esdiario.com/motor/241219/149212/alquiladoras-preven-cerrar-2024-facturacion-aproximada-2-100-millones.html`, consulta: 20/11/2026)[cite: 12].
  2. Espacio de mercado para una web más guiada y clara que las generalistas[cite: 12].

### Factores Negativos
* **Debilidades (Internas):**
  1. Equipo pequeño (2 personas) y plazo limitado, por lo que se excluyen pagos online y app móvil nativa[cite: 12, 21].
  2. Catálogo inicial reducido (flota de demostración para alquiler, sin vehículos reales disponibles)[cite: 12].
* **Amenazas (Externas):**
  1. Competidores grandes con marca reconocida y flotas masivas[cite: 12].
  2. Obligaciones estrictas del RGPD al gestionar datos personales y del permiso de conducir[cite: 12].

### Conclusión Estratégica del DAFO
No se compite en tamaño de flota frente a grandes operadores (A1), sino diferenciándose mediante el filtrado legal por permiso (F1) y la transparencia tarifaria (F2) para captar la demanda creciente (O1)[cite: 13]. Las limitaciones del equipo (D1) acotan el MVP a 3 capacidades sin pagos ni app nativa, mientras que la amenaza normativa (A2) se mitiga aplicando minimización de datos (sin subir imágenes del carnet) y cifrado BCrypt[cite: 13, 18, 26].
