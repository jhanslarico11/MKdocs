# 📷 Evidencias del Sistema

## 📌 Introducción

Esta sección presenta las principales interfaces desarrolladas para **Tridente Store**, evidenciando el funcionamiento de los módulos implementados durante el proyecto.

Las capturas muestran la evolución del sistema y permiten verificar visualmente cada funcionalidad.

---

# 🔐 Inicio de Sesión

!!! tip "Captura"

    ![Pantalla de inicio de sesión](../assets/capturas/login.png)

Descripción

- Autenticación de usuarios.
- Validación de credenciales.
- Acceso según rol.

---

# 🏠 Dashboard

!!! tip "Captura"

    ![Dashboard principal](../assets/capturas/dashboard.png)

Descripción

- Indicadores.
- Accesos rápidos.
- Estadísticas.

---

# 👥 Gestión de Usuarios

!!! tip "Captura"

    ![Módulo de gestión de usuarios](../assets/capturas/usuarios.png)

Funciones

- Registrar
- Editar
- Eliminar
- Roles

---

# 📦 Gestión de Productos

!!! tip "Captura"

    ![Módulo de gestión de productos](../assets/capturas/productos.png)

Funciones

- CRUD
- Stock
- Categorías

---

# 📂 Gestión de Categorías

!!! tip "Captura"

    ![Módulo de gestión de categorías](../assets/capturas/categorias.png)

---

# 👤 Gestión de Clientes

!!! tip "Captura"

    ![Módulo de gestión de clientes](../assets/capturas/clientes.png)

---

# 🚚 Gestión de Proveedores

!!! tip "Captura"

    ![Módulo de gestión de proveedores](../assets/capturas/proveedores.png)

---

# 💳 Registro de Ventas

!!! tip "Captura"

    ![Registro de ventas](../assets/capturas/ventas.png)

```mermaid
flowchart LR
    A[👤 Cliente] --> B[💳 Registrar venta]
    B --> C[📦 Actualizar stock]
    C --> D[(🗄️ Base de datos)]
    D --> E[📊 Generar reporte]
```

---

# 🛒 Registro de Compras

!!! tip "Captura"

    ![Registro de compras](../assets/capturas/compras.png)

---

# 📊 Reportes

!!! tip "Captura"

    ![Módulo de reportes](../assets/capturas/reportes.png)

---

# 📖 Documentación MKDocs

!!! tip "Captura"

    ![Documentación publicada en MKDocs](../assets/capturas/mkdocs.png)

---

# 🚀 GitHub

!!! tip "Captura"

    ![Repositorio en GitHub](../assets/capturas/github.png)

---

# 🧪 SonarCloud

!!! tip "Captura"

    ![Análisis en SonarCloud](../assets/capturas/sonarcloud.png)

---

# 🔐 Snyk

!!! tip "Captura"

    ![Análisis en Snyk](../assets/capturas/snyk.png)

---

# ⚡ k6

!!! tip "Captura"

    ![Resultado de pruebas de rendimiento con k6](../assets/capturas/k6.png)

---

# 📋 Resumen de Evidencias

| Evidencia | Estado |
|------------|:------:|
| Login | ✅ |
| Dashboard | ✅ |
| Usuarios | ✅ |
| Productos | ✅ |
| Categorías | ✅ |
| Clientes | ✅ |
| Proveedores | ✅ |
| Ventas | ✅ |
| Compras | ✅ |
| Reportes | ✅ |
| GitHub | ✅ |
| SonarCloud | ✅ |
| Snyk | ✅ |
| MKDocs | ✅ |

---

!!! success "Resultado"

    Las evidencias presentadas demuestran la implementación y funcionamiento de los módulos principales de Tridente Store, así como el uso de herramientas de calidad, documentación y control de versiones.
