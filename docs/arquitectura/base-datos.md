# 🗄 Arquitectura de Base de Datos

## 📌 Visión general

La base de datos de **Tridente Store** permite almacenar y relacionar la información principal del sistema: usuarios, roles, productos, categorías, clientes, proveedores, ventas, compras e inventario.

El diseño busca garantizar integridad, trazabilidad y consistencia en las operaciones comerciales.

---

## 🧱 Entidades principales

| Entidad | Descripción |
|---|---|
| Usuarios | Almacena los usuarios que acceden al sistema. |
| Roles | Define el nivel de acceso de cada usuario. |
| Productos | Registra los productos disponibles para venta. |
| Categorías | Clasifica los productos. |
| Clientes | Almacena información de los clientes. |
| Proveedores | Registra proveedores asociados a compras. |
| Ventas | Registra transacciones de salida de productos. |
| Detalle de venta | Guarda los productos vendidos por transacción. |
| Compras | Registra ingreso de productos al inventario. |
| Detalle de compra | Guarda productos adquiridos en cada compra. |

---

## 🏗 Diagrama Entidad - Relación

```mermaid
erDiagram
    USERS ||--o{ SALES : registra
    CLIENTS ||--o{ SALES : realiza
    SALES ||--|{ SALE_DETAILS : contiene
    PRODUCTS ||--o{ SALE_DETAILS : vendido_en

    SUPPLIERS ||--o{ PURCHASES : abastece
    PURCHASES ||--|{ PURCHASE_DETAILS : contiene
    PRODUCTS ||--o{ PURCHASE_DETAILS : comprado_en

    CATEGORIES ||--o{ PRODUCTS : clasifica
    ROLES ||--o{ USERS : asigna

    USERS {
        int id
        string name
        string email
        string password
        int role_id
    }

    ROLES {
        int id
        string name
    }

    PRODUCTS {
        int id
        string name
        decimal price
        int stock
        int category_id
    }

    CATEGORIES {
        int id
        string name
    }

    CLIENTS {
        int id
        string dni
        string full_name
    }

    SUPPLIERS {
        int id
        string ruc
        string business_name
    }

    SALES {
        int id
        date sale_date
        int client_id
        int user_id
    }

    SALE_DETAILS {
        int id
        int sale_id
        int product_id
        int quantity
        decimal sale_price
    }

    PURCHASES {
        int id
        date purchase_date
        int supplier_id
        int user_id
    }

    PURCHASE_DETAILS {
        int id
        int purchase_id
        int product_id
        int quantity
        decimal purchase_price
    }
```

---

## 🔄 Flujo de actualización de stock

```mermaid
flowchart TD
    A[Registro de venta o compra]
    B{Tipo de operación}
    C[Venta]
    D[Compra]
    E[Disminuir stock]
    F[Aumentar stock]
    G[Actualizar producto]
    H[Guardar transacción]
    I[Generar reporte]

    A --> B
    B --> C
    B --> D
    C --> E
    D --> F
    E --> G
    F --> G
    G --> H
    H --> I
```

---

## 🔐 Integridad de datos

| Regla | Aplicación |
|---|---|
| Claves primarias | Identifican cada registro de forma única. |
| Claves foráneas | Relacionan ventas, compras, productos, clientes y proveedores. |
| Validación de stock | Evita ventas con productos insuficientes. |
| Transacciones | Garantizan consistencia al registrar ventas o compras. |
| Historial | Permite trazabilidad de operaciones comerciales. |

---

## 📊 Beneficios del diseño

- Control de inventario en tiempo real.
- Trazabilidad de ventas y compras.
- Organización de productos por categorías.
- Relación entre clientes, proveedores y transacciones.
- Reducción de errores manuales.
- Información confiable para reportes.

---

!!! success "Conclusión"

    La arquitectura de base de datos permite que **Tridente Store** mantenga información organizada, consistente y confiable para la gestión comercial.