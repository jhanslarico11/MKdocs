# 🧩 Arquitectura MVC

## 📌 Visión general

El sistema **Tridente Store** utiliza una organización basada en el patrón **MVC (Modelo - Vista - Controlador)**, permitiendo separar la interfaz de usuario, la lógica de negocio y el acceso a datos.

Esta estructura facilita el mantenimiento, la escalabilidad y la organización del código.

---

## 🏗 Diagrama MVC aplicado a Tridente Store

```mermaid
graph TD
    U[👤 Usuario] --> V[Vista / View<br>React Frontend]

    V --> C[Controlador / Controller<br>Laravel Controllers]

    C --> M[Modelo / Model<br>Laravel Models]

    M --> DB[(🗄️ Base de Datos<br>MySQL / SQLite)]

    C --> S[Servicios<br>Validaciones y reglas de negocio]

    S --> M
```

---

## 📦 Responsabilidades por capa

| Capa MVC | Tecnología | Responsabilidad |
|---|---|---|
| Vista | React | Presentar interfaces, formularios, tablas y reportes. |
| Controlador | Laravel Controllers | Procesar solicitudes, validar datos y coordinar la lógica. |
| Modelo | Laravel Models | Representar entidades como productos, usuarios, ventas y compras. |
| Base de Datos | MySQL / SQLite | Almacenar información persistente del sistema. |

---

## 🔄 Flujo MVC en una venta

```mermaid
sequenceDiagram
    actor Usuario
    participant Vista as React View
    participant Controller as SaleController
    participant Model as Sale / Product Models
    participant DB as MySQL

    Usuario->>Vista: Ingresa datos de venta
    Vista->>Controller: Envía solicitud POST /ventas
    Controller->>Controller: Valida datos
    Controller->>Model: Crea venta y detalle
    Model->>DB: Guarda transacción
    Controller->>Model: Actualiza stock
    Model->>DB: Actualiza producto
    Controller-->>Vista: Retorna respuesta exitosa
    Vista-->>Usuario: Muestra venta registrada
```

---

## 🧠 Aplicación en módulos

| Módulo | Vista | Controlador | Modelo |
|---|---|---|---|
| Usuarios | Pantalla de usuarios | UserController | User |
| Productos | Pantalla de productos | ProductController | Product |
| Categorías | Pantalla de categorías | CategoryController | Category |
| Clientes | Pantalla de clientes | ClientController | Client |
| Proveedores | Pantalla de proveedores | SupplierController | Supplier |
| Ventas | Pantalla de ventas | SaleController | Sale |
| Compras | Pantalla de compras | PurchaseController | Purchase |
| Reportes | Dashboard / reportes | ReportController | Sale / Purchase / Product |

---

## ✅ Beneficios del patrón MVC

- Mejora la organización del código.
- Facilita el mantenimiento del sistema.
- Permite separar responsabilidades.
- Reduce el acoplamiento entre interfaz y lógica.
- Facilita pruebas y validaciones.
- Permite escalar módulos de forma independiente.

---

!!! success "Conclusión"

    La arquitectura MVC permite que **Tridente Store** mantenga una estructura clara y profesional, separando la presentación en React, la lógica de negocio en Laravel y la persistencia en MySQL/SQLite.