# 📊 Calidad del Software

## 📌 Introducción

La calidad del software desarrollado en **Tridente Store** fue evaluada considerando los atributos definidos por la norma **ISO/IEC 25010**, además de herramientas automáticas para análisis estático, seguridad y rendimiento.

---

# 🏛 Modelo de Calidad

```mermaid
graph TD

ISO[ISO 25010]

ISO --> FUNC[Funcionalidad]

ISO --> PERF[Rendimiento]

ISO --> USAB[Usabilidad]

ISO --> CONF[Confiabilidad]

ISO --> MANT[Mantenibilidad]

ISO --> SEG[Seguridad]

ISO --> PORT[Portabilidad]
```

---

# Herramientas utilizadas

| Herramienta | Objetivo |
|-------------|----------|
| SonarCloud | Calidad del código |
| Snyk | Seguridad |
| k6 | Rendimiento |
| GitHub | Versionamiento |
| Swagger | API |
| MKDocs | Documentación |

---

# Flujo de Calidad

```mermaid
flowchart LR

Código

-->

GitHub

-->

SonarCloud

-->

Snyk

-->

k6

-->

Resultado
```

---

# Métricas evaluadas

| Métrica | Estado |
|----------|--------|
| Bugs | ✅ |
| Vulnerabilidades | ✅ |
| Code Smells | ✅ |
| Duplicación | ✅ |
| Cobertura | ✅ |
| Rendimiento | ✅ |

---

# Evaluación ISO 25010

| Característica | Evaluación |
|----------------|------------|
| Funcionalidad | Excelente |
| Confiabilidad | Muy Buena |
| Rendimiento | Muy Bueno |
| Usabilidad | Excelente |
| Seguridad | Muy Buena |
| Mantenibilidad | Excelente |
| Compatibilidad | Muy Buena |

---

# Arquitectura de Calidad

```mermaid
graph TD

Código

-->

SonarCloud

-->

Bugs

Código

-->

Snyk

-->

Seguridad

Código

-->

k6

-->

Performance
```

---

!!! success "Resultado"

La aplicación cumple con los criterios principales de calidad establecidos por ISO/IEC 25010 y fue apoyada por herramientas automáticas para asegurar la mantenibilidad, seguridad y rendimiento.