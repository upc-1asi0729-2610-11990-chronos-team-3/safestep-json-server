# SafeStep JSON Server

API falsa basada en `json-server` para el desarrollo frontend de la plataforma SafeStep.

## Archivo `db.json`

Contiene datos simulados organizados en 5 colecciones principales:

### `identityAccess`
Gestión de identidad y acceso de usuarios.

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| `sampleUser` | `object` | Perfil del usuario autenticado (Ana Torres) |
| `demoUsers` | `array` | Lista de 8 usuarios demo con niveles, XP, rachas y SafeCoins |
| `authProviders` | `array` | Proveedores de autenticación (email, teléfono, Google, Microsoft) |
| `passwordRules` | `array` | Reglas de seguridad para contraseñas |
| `securityEvents` | `array` | Historial de eventos de seguridad del usuario |
| `notifications` | `array` | Notificaciones del usuario (ofertas, stock bajo) |
| `userProfiles` | `array` | Perfiles extendidos de usuario (nombre, idioma, fechas) |

### `medicalSimulations`
Simulaciones médicas interactivas.

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| `simulations` | `array` | 18 escenarios de simulación (RCP, atragantamiento, quemaduras, sismos, hemorragias, fracturas, intoxicación, convulsiones, desmayo, shock, heridas, anafilaxia, golpe de calor, accidentes tránsito, bioseguridad, evacuación, pediatría, botiquín). Cada simulación incluye pasos con opciones múltiples, retroalimentación, sugerencias de producto y recompensas. |
| `attempts` | `array` | Intentos de simulación con puntuación, errores y tiempo |

### `gamification`
Sistema de gamificación con misiones, insignias y ranking.

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| `levelSummary` | `object` | Resumen de nivel, XP, SafeCoins, racha y ranking semanal |
| `missions` | `array` | 7 misiones diarias y 7 semanales con progreso, recompensas y requisitos |
| `badges` | `array` | 17 insignias con rarezas (Común, Rara, Épica, Legendaria) |
| `leaderboard` | `array` | Ranking top 20 de usuarios con XP y racha |
| `coinTransactions` | `array` | Historial de transacciones de SafeCoins por simulación |

### `ecommerce`
Catálogo de productos, pedidos y comercio electrónico.

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| `products` | `array` | 24 productos organizados en categorías (kits, emergencia, RCP, vendajes, protección personal, etc.) con precios, rating, stock y etiquetas |
| `coupons` | `array` | 12 cupones canjeables con SafeCoins (descuentos del 8% al 25%) |
| `orders` | `array` | 10 pedidos con estados (Comprado, Entregado, En camino, Preparando, Cancelado) |
| `categories` | `array` | 14 categorías de productos con conteo |
| `reviews` | `array` | 40 reseñas de productos con puntuación y comentario |
| `cartItems` | `array` | Items en carrito de compras |
| `shippingAddresses` | `array` | Direcciones de envío con datos completos |
| `paymentMethods` | `array` | Métodos de pago (tarjeta, transferencia, billetera digital) |
| `personalizedRecommendations` | `array` | Recomendaciones personalizadas ligadas a errores en simulaciones |
| `emergencyKits` | `array` | 4 kits de emergencia agrupados con ahorro |

### `statistics`
Estadísticas y progreso del usuario.

| Propiedad | Tipo | Descripción |
|-----------|------|-------------|
| `summary` | `array` | 6 métricas generales (simulaciones, precisión, XP, productos, insignias, racha) |
| `simulationTypes` | `array` | Precisión por tipo de emergencia (12 tipos) |
| `weeklyActivity` | `array` | Actividad diaria de las últimas 2 semanas (XP y simulaciones) |
| `monthlyActivity` | `array` | Actividad semanal de los últimos 3 meses |
| `commonMistakes` | `array` | Errores frecuentes ordenados por incidencia |
| `skillProgress` | `array` | Progreso por habilidad (0-100%) |
| `recommendations` | `array` | Recomendaciones de mejora con prioridad |
| `performanceByDifficulty` | `array` | Rendimiento por dificultad (Básico, Intermedio, Avanzado) |
| `progressVisuals` | `array` | Progreso visual por escenario con puntuaciones y errores |
| `evaluationResults` | `array` | Resultados de evaluaciones con desglose por área |
| `certificates` | `array` | Certificados emitidos con código de verificación |
| `attempts` | `array` | Historial completo de intentos |

## Endpoints disponibles

| Ruta | Método | Descripción |
|------|--------|-------------|
| `/identityAccess` | GET | Todos los datos de identidad y acceso |
| `/identityAccess/sampleUser` | GET | Usuario autenticado |
| `/identityAccess/demoUsers` | GET | Usuarios demo |
| `/identityAccess/notifications` | GET | Notificaciones |
| `/medicalSimulations` | GET | Todas las simulaciones médicas |
| `/medicalSimulations/simulations` | GET | Escenarios de simulación |
| `/medicalSimulations/attempts` | GET | Intentos de simulación |
| `/gamification` | GET | Todos los datos de gamificación |
| `/gamification/missions` | GET | Misiones diarias y semanales |
| `/gamification/badges` | GET | Insignias |
| `/gamification/leaderboard` | GET | Ranking de usuarios |
| `/ecommerce` | GET | Todos los datos de comercio |
| `/ecommerce/products` | GET | Catálogo de productos |
| `/ecommerce/coupons` | GET | Cupones disponibles |
| `/ecommerce/orders` | GET | Historial de pedidos |
| `/statistics` | GET | Todas las estadísticas |
| `/statistics/summary` | GET | Resumen de métricas |

> Todos los endpoints soportan filtros, paginación y ordenación de json-server. Ej: `/ecommerce/products?category=Kits` o `/medicalSimulations/simulations?status=Completado`.
