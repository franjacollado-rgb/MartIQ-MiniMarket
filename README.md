# MartIQ — Mini Market Inteligente

> Sistema de mini market que implementa **6 estructuras de datos** fundamentales en una aplicación web real.

## Tecnologías

| Capa | Tecnología |
|---|---|
| Backend API | C# ASP.NET Core 8 |
| Base de datos | SQLite + Entity Framework Core 8 |
| Frontend | HTML5 + CSS3 + JavaScript ES2022 |
| Documentación API | Swagger UI |
| Metodología | SCRUM — 2 Sprints — 2 Semanas |

## Estructuras de datos implementadas

| Estructura | Tipo | Dónde se usa |
|---|---|---|
| Lista enlazada | Secuencial O(n) | Catálogo de productos — GET /api/products |
| Cola (Queue) | FIFO O(1) | Carrito de compras — POST /api/cart |
| Pila (Stack) | LIFO O(1) | Historial de pedidos — GET /api/orders |
| Árbol | Jerárquico | Categorías — GET /api/categories |
| Tabla Hash | O(1) promedio | Búsqueda — GET /api/products/search |
| Grafo | No dirigido | Productos relacionados — GET /api/products/graph |

## Cómo ejecutar el proyecto

### Requisitos
- Visual Studio 2022 con workload "ASP.NET and web development"
- .NET 8 SDK

### Pasos

```bash
# 1. Clonar el repositorio
git clone https://github.com/franjacollado-rgb/MartIQ-MiniMarket.git

# 2. Entrar a la carpeta de la API
cd MartIQ-MiniMarket/MartIQ.API

# 3. Crear la base de datos
dotnet ef migrations add InitialCreate
dotnet ef database update

# 4. Correr la API
dotnet run
```

La API estará disponible en `https://localhost:7100`
Swagger UI en `https://localhost:7100/swagger`

### Frontend
Abrir el archivo `frontend/mini-market.html` directamente en el navegador.
Asegurarse de que la API esté corriendo antes de abrir el HTML.

## Equipo

| Rol | Integrante |
|---|---|
| Product Owner | Integrante A |
| Scrum Master | Integrante B |
| Dev Backend | Integrante C |
| Dev Frontend | Integrante D |

## Documentación
La carpeta `/docs` contiene:
- Documentación técnica completa (PDF y Word)
- Presentación universitaria (PPTX)
- Fichas del proyecto con BD, controladores y API (Excel)

## Endpoints principales

```
GET  /api/products              Lista paginada de productos
GET  /api/products/search?q=    Búsqueda por nombre/categoría
GET  /api/products/{id}/related Productos relacionados (grafo)
GET  /api/categories            Árbol completo de categorías
GET  /api/cart                  Carrito de la sesión (FIFO)
POST /api/cart                  Agregar producto al carrito
POST /api/orders/checkout       Confirmar pedido (Cola → Pila)
GET  /api/orders                Historial de órdenes (LIFO)
```
