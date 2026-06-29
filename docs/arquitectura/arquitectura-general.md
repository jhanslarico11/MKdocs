# 🏛 Arquitectura General del Sistema

## 📌 Visión General

La arquitectura de **Tridente Store** está diseñada bajo un enfoque **cliente-servidor**, separando la interfaz de usuario, la lógica de negocio y la persistencia de datos.

Esta separación permite que el sistema sea más organizado, mantenible, escalable y seguro.

---

## 🎯 Objetivos de la arquitectura

- Separar responsabilidades entre frontend, backend y base de datos.
- Facilitar el mantenimiento del código.
- Permitir el crecimiento futuro del sistema.
- Mejorar la seguridad mediante control de acceso.
- Centralizar la lógica de negocio en el backend.
- Documentar la API mediante Swagger.
- Integrar herramientas de calidad como SonarCloud y Snyk.

---

## 🏗 Vista general de arquitectura

```mermaid
graph TD
    subgraph Usuario
        U[👤 Administrador / Usuario]
    end

    subgraph Frontend
        R[⚛️ React Frontend]
    end

    subgraph Backend
        L[🟢 Laravel API]
        AUTH[🔐 Autenticación]
        INV[📦 Inventario]
        VEN[💳 Ventas]
        COM[🛒 Compras]
        REP[📊 Reportes]
    end

    subgraph Datos
        DB[(🗄️ MySQL / SQLite)]
    end

    subgraph Documentacion
        SW[📚 Swagger API]
        MK[📘 MKDocs]
        GP[🌐 GitHub Pages]
    end

    subgraph Calidad
        SC[🟢 SonarCloud]
        SN[🛡️ Snyk]
        K6[⚡ k6]
    end

    U --> R
    R --> L
    L --> AUTH
    L --> INV
    L --> VEN
    L --> COM
    L --> REP
    L --> DB

    L --> SW
    MK --> GP
    L --> SC
    L --> SN
    L --> K6
```

---

## 🧱 Capas principales

| Capa | Tecnología | Responsabilidad |
|---|---|---|
| Presentación | React | Interfaz de usuario |
| Aplicación | Laravel | Controladores, rutas, validaciones y lógica |
| Dominio | Modelos Laravel | Entidades del negocio |
| Persistencia | MySQL / SQLite | Almacenamiento de datos |
| Documentación | Swagger / MKDocs | API y documentación técnica |
| Calidad | SonarCloud / Snyk / k6 | Análisis, seguridad y rendimiento |

---

## 🧩 Módulos principales

<div class="cards">

<div class="card">
<h3>🔐 Usuarios y roles</h3>
<p>Gestiona autenticación, autorización, roles y permisos.</p>
</div>

<div class="card">
<h3>📦 Productos</h3>
<p>Administra productos, categorías y control de stock.</p>
</div>

<div class="card">
<h3>👥 Clientes</h3>
<p>Registra y mantiene información de clientes.</p>
</div>

<div class="card">
<h3>🚚 Proveedores</h3>
<p>Administra proveedores asociados a las compras.</p>
</div>

<div class="card">
<h3>💳 Ventas</h3>
<p>Registra ventas y actualiza inventario automáticamente.</p>
</div>

<div class="card">
<h3>🛒 Compras</h3>
<p>Registra compras y aumenta el stock disponible.</p>
</div>

<div class="card">
<h3>📊 Reportes</h3>
<p>Genera reportes de ventas, compras e inventario.</p>
</div>

<div class="card">
<h3>🧪 Calidad</h3>
<p>Integra SonarCloud, Snyk y k6 para evaluar el sistema.</p>
</div>

</div>

---

## 🔄 Flujo general del sistema

```mermaid
sequenceDiagram
    actor Usuario
    participant React as Frontend React
    participant Laravel as Backend Laravel
    participant DB as Base de Datos
    participant Reportes as Módulo Reportes

    Usuario->>React: Solicita operación
    React->>Laravel: Envía petición HTTP
    Laravel->>Laravel: Valida datos y permisos
    Laravel->>DB: Consulta o registra información
    DB-->>Laravel: Retorna resultado
    Laravel->>Reportes: Genera información si corresponde
    Laravel-->>React: Respuesta JSON
    React-->>Usuario: Muestra resultado
```

---

## ✅ Beneficios arquitectónicos

| Beneficio | Descripción |
|---|---|
| Escalabilidad | Permite agregar nuevos módulos sin afectar todo el sistema. |
| Mantenibilidad | La separación por capas facilita correcciones y mejoras. |
| Seguridad | El backend centraliza autenticación, roles y permisos. |
| Trazabilidad | Las operaciones comerciales quedan registradas. |
| Calidad | Las herramientas de análisis permiten detectar mejoras. |
| Documentación | Swagger y MKDocs facilitan comprensión y mantenimiento. |

---

## 📦 Resultado

La arquitectura general de **Tridente Store** permite construir un sistema comercial modular, seguro y mantenible, preparado para crecer e integrarse con herramientas modernas de desarrollo, documentación y calidad.