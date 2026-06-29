# 🏗 Fase 2 - Diseño

## Objetivo de la fase

Diseñar la estructura técnica del sistema **Tridente Store**, definiendo su arquitectura, componentes principales, flujo de información, base de datos y organización de módulos.

---

## 🧠 Enfoque de diseño

El sistema se diseñó bajo una arquitectura **cliente-servidor**, separando la interfaz de usuario, la lógica de negocio y la persistencia de datos.

Esta separación permite mejorar:

- Escalabilidad.
- Mantenibilidad.
- Seguridad.
- Rendimiento.
- Organización del código.
- Facilidad de despliegue.

---

## 🏛 Arquitectura propuesta

| Capa | Tecnología | Función |
|---|---|---|
| Frontend | React | Interfaz de usuario |
| Backend | Laravel | Lógica de negocio y API |
| Base de datos | MySQL / SQLite | Almacenamiento de información |
| Documentación API | Swagger | Documentación de endpoints |
| Control de versiones | GitHub | Gestión colaborativa del código |
| Calidad | SonarCloud / Snyk | Revisión de calidad y seguridad |

---

## 🧩 Componentes principales

<div class="cards">

<div class="card">
<h3>Frontend React</h3>
<p>Permite al usuario interactuar con el sistema mediante interfaces dinámicas y responsivas.</p>
</div>

<div class="card">
<h3>Backend Laravel</h3>
<p>Gestiona la lógica de negocio, validaciones, autenticación, API REST y comunicación con la base de datos.</p>
</div>

<div class="card">
<h3>Base de Datos</h3>
<p>Almacena usuarios, productos, categorías, clientes, proveedores, ventas, compras e inventario.</p>
</div>

<div class="card">
<h3>API REST</h3>
<p>Permite la comunicación entre frontend y backend mediante endpoints documentados con Swagger.</p>
</div>

</div>

---

## 🔐 Diseño de seguridad

El diseño del sistema considera autenticación, autorización y protección de datos mediante:

- Login de usuarios.
- Roles y permisos.
- Validación de formularios.
- Restricción de acceso por perfil.
- Uso de variables de entorno.
- Protección de credenciales sensibles.
- Revisión de vulnerabilidades con Snyk.
- Análisis de seguridad con SonarCloud.

---

## 🗃 Entidades principales del sistema

| Entidad | Descripción |
|---|---|
| Usuario | Persona con acceso al sistema |
| Rol | Define permisos y nivel de acceso |
| Producto | Artículo disponible para venta |
| Categoría | Clasificación de productos |
| Cliente | Persona que realiza compras |
| Proveedor | Entidad que abastece productos |
| Venta | Transacción comercial de salida |
| Compra | Transacción de ingreso de productos |
| Inventario | Control de stock disponible |
| Reporte | Información generada para análisis |

---

## 🔄 Diagrama de arquitectura

```mermaid
graph TD
    A[Usuario] --> B[Interfaz React]
    B --> C[API REST Laravel]
    C --> D[Controladores]
    D --> E[Modelos]
    E --> F[(Base de Datos MySQL)]

    C --> G[Autenticación]
    C --> H[Validaciones]
    C --> I[Reportes]
    C --> J[Inventario]

    K[Swagger] --> C
    L[GitHub] --> M[SonarCloud]
    L --> N[Snyk]
```

---

## 🧭 Flujo de venta diseñado

```mermaid
flowchart LR
    A[Cliente selecciona producto] --> B[Sistema verifica stock]
    B --> C{¿Hay stock?}
    C -- Sí --> D[Registrar venta]
    D --> E[Actualizar inventario]
    E --> F[Generar comprobante]
    F --> G[Mostrar reporte]
    C -- No --> H[Mostrar producto no disponible]
```

---

## 📦 Entregables de la fase

<div class="cards">

<div class="card">
<h3>🏛 Arquitectura del sistema</h3>
<p>Diseño general cliente-servidor con frontend, backend y base de datos.</p>
</div>

<div class="card">
<h3>🗃 Modelo de datos</h3>
<p>Identificación de entidades principales y relaciones del sistema.</p>
</div>

<div class="card">
<h3>🔐 Diseño de seguridad</h3>
<p>Definición de roles, permisos, autenticación y protección de credenciales.</p>
</div>

<div class="card">
<h3>🔄 Flujo del sistema</h3>
<p>Diseño del proceso de venta e inventario automatizado.</p>
</div>

</div>

---

## ✅ Resultado de la fase

La fase de diseño permitió definir la estructura técnica de **Tridente Store**, estableciendo una arquitectura clara basada en React, Laravel y base de datos relacional. Además, se diseñaron los módulos principales, el flujo de venta, la seguridad y los componentes necesarios para la implementación.