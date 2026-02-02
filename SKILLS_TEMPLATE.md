# SKILLS.md - Habilidades y Capacidades del Agente

> **INSTRUCCIONES PARA IA**: Este archivo complementa AGENTS.md y define las habilidades/skills específicas
> que los agentes de código deben tener para trabajar efectivamente en este proyecto.
> Completa cada sección con información específica del proyecto.
> Elimina estas instrucciones y los comentarios entre `<!-- -->` del documento final.

---

## 📚 Sobre este Documento

Este archivo define las **habilidades especializadas** que los agentes de código necesitan para trabajar en este proyecto. Mientras que [AGENTS.md](./AGENTS.md) describe QUÉ es el proyecto y CÓMO está estructurado, este documento describe QUÉ PUEDE HACER un agente y CÓMO debe hacerlo.

**Relación con AGENTS.md**:
- **AGENTS.md**: Contexto del proyecto, arquitectura, estructura de código
- **SKILLS.md**: Capacidades específicas, tareas ejecutables, procedimientos

---

## 🎯 Skills Básicas Requeridas

### Para Proyectos Backend

#### 1. Database Management
**Propósito**: Gestión y manipulación de base de datos

**Capacidades**:
- Crear, modificar y eliminar tablas/entidades
- Escribir migraciones de base de datos
- Optimizar queries y índices
- Diseñar relaciones entre entidades

**Herramientas requeridas**:
- [ORM/Framework: JPA, TypeORM, SQLAlchemy, etc.]
- [Migration Tool: Flyway, Alembic, etc.]

**Ejemplos de tareas**:
```
- "Agrega una migración para crear la tabla users"
- "Optimiza la query de búsqueda de productos"
- "Crea un índice para mejorar el rendimiento"
```

---

#### 2. API Development
**Propósito**: Desarrollo y mantenimiento de endpoints REST/GraphQL

**Capacidades**:
- Crear nuevos endpoints siguiendo convenciones
- Implementar validación de datos de entrada
- Manejar respuestas y errores correctamente
- Aplicar autenticación y autorización

**Herramientas requeridas**:
- [Framework: Spring Boot, Express, FastAPI, etc.]
- [Validation: Bean Validation, Joi, Pydantic, etc.]

**Ejemplos de tareas**:
```
- "Crea un endpoint POST /api/users para crear usuarios"
- "Agrega validación a los parámetros del endpoint"
- "Implementa rate limiting en la API"
```

---

#### 3. Business Logic Implementation
**Propósito**: Implementación de lógica de negocio en la capa de servicio

**Capacidades**:
- Implementar casos de uso complejos
- Orquestar múltiples operaciones
- Aplicar reglas de negocio
- Manejar transacciones

**Ejemplos de tareas**:
```
- "Implementa la lógica de cálculo de descuentos"
- "Agrega validación de reglas de negocio en el servicio"
- "Implementa el flujo de procesamiento de pedidos"
```

---

#### 4. Integration & External Services
**Propósito**: Integración con APIs externas y servicios de terceros

**Capacidades**:
- Consumir APIs REST/SOAP
- Implementar clientes HTTP
- Manejar autenticación OAuth/API Keys
- Implementar circuit breakers y retry logic

**Herramientas requeridas**:
- [HTTP Client: RestTemplate, Axios, Requests, etc.]
- [Resilience: Resilience4j, etc.]

**Ejemplos de tareas**:
```
- "Integra con la API de pagos de Stripe"
- "Implementa retry logic para llamadas externas"
- "Agrega circuit breaker para el servicio de email"
```

---

#### 5. Testing & Quality Assurance
**Propósito**: Escribir y mantener tests de calidad

**Capacidades**:
- Escribir unit tests
- Implementar integration tests
- Crear mocks y fixtures
- Asegurar cobertura de código

**Herramientas requeridas**:
- [Testing Framework: JUnit, Jest, pytest, etc.]
- [Mocking: Mockito, Sinon, etc.]

**Ejemplos de tareas**:
```
- "Escribe tests unitarios para UserService"
- "Crea tests de integración para el endpoint de login"
- "Agrega test coverage al módulo de pagos"
```

---

#### 6. Performance Optimization
**Propósito**: Optimización de rendimiento y recursos

**Capacidades**:
- Identificar bottlenecks
- Implementar caching
- Optimizar queries N+1
- Configurar connection pooling

**Herramientas requeridas**:
- [Cache: Redis, Caffeine, Memcached, etc.]
- [Profiling tools]

**Ejemplos de tareas**:
```
- "Implementa caching para la consulta de productos"
- "Resuelve el problema N+1 en la carga de usuarios"
- "Optimiza el tiempo de respuesta del endpoint"
```

---

### Para Proyectos Frontend

#### 1. Component Development
**Propósito**: Desarrollo de componentes UI reutilizables

**Capacidades**:
- Crear componentes siguiendo patrones establecidos
- Implementar props y state management
- Aplicar composición de componentes
- Seguir principios de diseño atómico

**Herramientas requeridas**:
- [Framework: React, Vue, Angular, Svelte, etc.]
- [Styling: CSS Modules, Styled Components, Tailwind, etc.]

**Ejemplos de tareas**:
```
- "Crea un componente Button reutilizable"
- "Implementa un formulario con validación"
- "Refactoriza el componente en piezas más pequeñas"
```

---

#### 2. State Management
**Propósito**: Manejo del estado de la aplicación

**Capacidades**:
- Implementar state global y local
- Usar context API / stores
- Optimizar re-renders
- Sincronizar estado con backend

**Herramientas requeridas**:
- [State Management: Redux, Zustand, Pinia, NgRx, etc.]
- [Server State: React Query, SWR, etc.]

**Ejemplos de tareas**:
```
- "Implementa el store de autenticación"
- "Agrega manejo de estado para el carrito de compras"
- "Optimiza los re-renders del componente"
```

---

#### 3. API Integration & Data Fetching
**Propósito**: Integración con APIs backend

**Capacidades**:
- Implementar llamadas HTTP
- Manejar loading/error states
- Implementar retry y cache
- Validar respuestas del servidor

**Herramientas requeridas**:
- [HTTP Client: Axios, Fetch API, etc.]
- [Data Fetching: React Query, SWR, Apollo, etc.]

**Ejemplos de tareas**:
```
- "Implementa el fetch de datos de usuarios"
- "Agrega manejo de errores en las peticiones"
- "Implementa infinite scroll con paginación"
```

---

#### 4. Routing & Navigation
**Propósito**: Manejo de rutas y navegación

**Capacidades**:
- Configurar rutas
- Implementar navegación dinámica
- Proteger rutas privadas
- Manejar parámetros y query strings

**Herramientas requeridas**:
- [Router: React Router, Vue Router, Angular Router, etc.]

**Ejemplos de tareas**:
```
- "Agrega una nueva ruta para el dashboard"
- "Implementa protección de rutas autenticadas"
- "Configura lazy loading de rutas"
```

---

#### 5. Form Handling & Validation
**Propósito**: Manejo y validación de formularios

**Capacidades**:
- Crear formularios controlados
- Implementar validación client-side
- Manejar envío de formularios
- Mostrar errores de validación

**Herramientas requeridas**:
- [Form Library: React Hook Form, Formik, VeeValidate, etc.]
- [Validation: Yup, Zod, Joi, etc.]

**Ejemplos de tareas**:
```
- "Crea un formulario de registro con validación"
- "Implementa validación asíncrona del email"
- "Agrega manejo de errores del servidor"
```

---

#### 6. UI/UX & Styling
**Propósito**: Implementación de diseño y estilos

**Capacidades**:
- Implementar diseños responsivos
- Aplicar design system
- Crear animaciones y transiciones
- Asegurar accesibilidad (a11y)

**Herramientas requeridas**:
- [CSS Framework: Tailwind, Bootstrap, Material UI, etc.]
- [Animation: Framer Motion, GSAP, etc.]

**Ejemplos de tareas**:
```
- "Implementa el diseño responsive de la landing page"
- "Agrega animaciones a las transiciones de página"
- "Asegura accesibilidad WCAG AA"
```

---

#### 7. Performance & Optimization
**Propósito**: Optimización de rendimiento frontend

**Capacidades**:
- Implementar code splitting
- Optimizar imágenes y assets
- Usar lazy loading
- Minimizar bundle size

**Herramientas requeridas**:
- [Bundler: Webpack, Vite, Rollup, etc.]
- [Optimization: Image optimization, tree shaking, etc.]

**Ejemplos de tareas**:
```
- "Implementa lazy loading de componentes"
- "Optimiza el bundle size de la aplicación"
- "Agrega prefetching de datos críticos"
```

---

## 🔧 Skills Específicas del Proyecto

<!-- Agregar skills únicas de este proyecto -->

### [Nombre de Skill Personalizada 1]
**Propósito**: [Descripción del propósito]

**Capacidades**:
- [Capacidad 1]
- [Capacidad 2]
- [Capacidad 3]

**Contexto del proyecto**:
[Explicar por qué esta skill es necesaria en este proyecto específico]

**Herramientas/Frameworks**:
- [Herramienta específica]
- [Configuración particular]

**Procedimiento**:
```
1. [Paso 1]
2. [Paso 2]
3. [Paso 3]
```

**Ejemplos de código**:
```[lenguaje]
// Ejemplo real del proyecto
[código de ejemplo]
```

**Ejemplos de tareas**:
```
- "Tarea de ejemplo 1"
- "Tarea de ejemplo 2"
```

**Checklist**:
- [ ] [Verificación 1]
- [ ] [Verificación 2]
- [ ] [Verificación 3]

**Referencias**:
- [Documentación interna: ruta/archivo.md]
- [Código de referencia: src/example/file.ts]

---

### [Nombre de Skill Personalizada 2]
<!-- Repetir estructura anterior -->

---

## 🎨 Skills Transversales (Frontend + Backend)

### Authentication & Authorization
**Propósito**: Implementación de seguridad y control de acceso

**Capacidades**:
- Implementar login/logout
- Manejar tokens JWT
- Implementar refresh tokens
- Aplicar RBAC/ABAC

**Aplica a**:
- **Backend**: Validación de tokens, generación de JWT, middleware de autorización
- **Frontend**: Almacenamiento de tokens, interceptores HTTP, protección de rutas

**Ejemplos de tareas**:
```
Backend: "Implementa middleware de autenticación JWT"
Frontend: "Agrega interceptor para incluir token en requests"
```

---

### Error Handling
**Propósito**: Manejo robusto de errores

**Capacidades**:
- Implementar error boundaries/handlers
- Logging estructurado
- Notificación de errores
- Recovery strategies

**Aplica a**:
- **Backend**: Exception handlers, logging, error responses
- **Frontend**: Error boundaries, toast notifications, fallback UI

**Ejemplos de tareas**:
```
Backend: "Implementa global exception handler"
Frontend: "Agrega error boundary para la aplicación"
```

---

### Configuration Management
**Propósito**: Gestión de configuración y variables de entorno

**Capacidades**:
- Manejar variables de entorno
- Configuración por ambiente
- Secrets management
- Feature flags

**Aplica a**:
- **Backend**: Config files, env variables, secrets vault
- **Frontend**: Build-time variables, runtime config

**Ejemplos de tareas**:
```
Backend: "Configura variables de entorno para producción"
Frontend: "Implementa feature flag para nueva funcionalidad"
```

---

## 📝 Procedimientos Estándar

### Procedimiento: Agregar Nueva Funcionalidad

**Cuándo usar**: Al implementar una nueva feature completa

**Pasos**:

1. **Análisis y Diseño**
   ```
   - Revisar AGENTS.md para entender arquitectura
   - Identificar capas afectadas
   - Diseñar contratos (DTOs, interfaces)
   ```

2. **Backend (si aplica)**
   ```
   - Crear/actualizar entidad de dominio
   - Implementar repositorio
   - Crear DTOs de request/response
   - Implementar servicio con lógica de negocio
   - Crear controlador/endpoint
   - Agregar validaciones
   ```

3. **Frontend (si aplica)**
   ```
   - Crear componentes necesarios
   - Implementar state management
   - Agregar llamadas a API
   - Implementar manejo de errores
   - Agregar validación de formularios
   ```

4. **Testing**
   ```
   - Escribir unit tests
   - Crear integration tests
   - Verificar cobertura
   ```

5. **Documentación**
   ```
   - Actualizar AGENTS.md si hay cambios arquitectónicos
   - Documentar código (Javadoc/JSDoc/etc)
   - Actualizar README si es necesario
   ```

**Verificación**:
- [ ] Código sigue convenciones del proyecto
- [ ] Tests pasan correctamente
- [ ] Documentación actualizada
- [ ] Sin errores de lint
- [ ] Performance aceptable

---

### Procedimiento: Debugging de Problemas

**Cuándo usar**: Al investigar bugs o comportamientos inesperados

**Pasos**:

1. **Reproducir el problema**
   ```
   - Identificar steps to reproduce
   - Verificar en qué ambiente ocurre
   - Revisar logs relevantes
   ```

2. **Investigación**
   ```
   - Revisar código relacionado
   - Verificar cambios recientes (git log)
   - Revisar tests existentes
   - Agregar logging adicional si es necesario
   ```

3. **Diagnóstico**
   ```
   - Identificar causa raíz
   - Evaluar impacto
   - Considerar side effects
   ```

4. **Solución**
   ```
   - Implementar fix
   - Agregar test que cubra el caso
   - Verificar que no rompe funcionalidad existente
   ```

5. **Prevención**
   ```
   - Documentar en TROUBLESHOOTING.md
   - Actualizar guías si es patrón común
   ```

---

### Procedimiento: Refactoring de Código

**Cuándo usar**: Al mejorar código existente sin cambiar funcionalidad

**Pasos**:

1. **Preparación**
   ```
   - Asegurar que hay tests existentes
   - Identificar smell codes o anti-patterns
   - Planificar cambios incrementales
   ```

2. **Refactoring**
   ```
   - Aplicar cambios pequeños e incrementales
   - Ejecutar tests después de cada cambio
   - Mantener commits atómicos
   ```

3. **Verificación**
   ```
   - Tests pasan
   - Funcionalidad sin cambios
   - Performance no degradada
   - Mejora en métricas de calidad
   ```

**Principios a seguir**:
- SOLID principles (ver AGENTS.md)
- DRY (Don't Repeat Yourself)
- KISS (Keep It Simple, Stupid)
- YAGNI (You Aren't Gonna Need It)

---

## 🚀 Quick Reference: Comandos por Skill

### Database Management
```bash
# Crear migración
[comando específico del proyecto]

# Ejecutar migraciones
[comando]

# Rollback
[comando]

# Seed database
[comando]
```

### Testing
```bash
# Run all tests
[comando]

# Run specific test file
[comando]

# Run with coverage
[comando]

# Watch mode
[comando]
```

### Build & Deploy
```bash
# Development build
[comando]

# Production build
[comando]

# Run locally
[comando]

# Deploy
[comando]
```

---

## 🎯 Skill Matrix

<!-- Tabla de referencia rápida de qué skill usar según la tarea -->

| Tarea | Skill Primaria | Skills Secundarias |
|-------|---------------|-------------------|
| Agregar endpoint REST | API Development | Business Logic, Testing |
| Crear componente UI | Component Development | UI/UX, State Management |
| Optimizar query lenta | Performance Optimization | Database Management |
| Implementar autenticación | Authentication | API Development, State Management |
| Integrar API externa | Integration & External Services | Error Handling, Testing |
| Crear formulario | Form Handling & Validation | Component Development, API Integration |
| [Más tareas comunes] | [Skill] | [Skills] |

---

## 📚 Recursos y Referencias

### Documentación Técnica
- **[Nombre de Doc]**: [Ruta o URL] - [Descripción]
- **[Nombre de Doc]**: [Ruta o URL] - [Descripción]

### Ejemplos de Código
- **[Feature]**: Ver [ruta/archivo.ext] - [Descripción]
- **[Pattern]**: Ver [ruta/archivo.ext] - [Descripción]

### Guías Externas
- **[Framework Docs]**: [URL]
- **[Best Practices]**: [URL]

---

## 🔄 Actualización de Skills

### Cuándo Actualizar este Documento

Actualiza SKILLS.md cuando:
- Se agrega una nueva capacidad técnica al proyecto
- Cambian procedimientos estándar
- Se adoptan nuevas herramientas o frameworks
- Se identifican nuevos patrones recomendados
- Se documenta una solución a un problema recurrente

### Versionado
- **Versión actual**: [X.Y.Z]
- **Última actualización**: [YYYY-MM-DD]
- **Mantenedor**: [Nombre/Equipo]

---

## 💡 Para la IA Generadora

Al completar esta plantilla:

1. **Analiza las capacidades reales** del proyecto
2. **Prioriza skills según frecuencia de uso** en el proyecto
3. **Incluye ejemplos de código reales**, no genéricos
4. **Documenta procedimientos actuales**, no ideales
5. **Sé específico con herramientas y versiones**
6. **Conecta con AGENTS.md**: referencia secciones relevantes
7. **Agrega comandos verificados** que realmente funcionan
8. **Personaliza para el tipo de proyecto**: no todas las skills aplican

**Balance Frontend/Backend**:
- Proyectos full-stack: incluir ambos
- Solo backend: enfocarse en skills de servidor
- Solo frontend: enfocarse en skills de UI/UX

**Elimina**:
- Skills que no se usan en el proyecto
- Secciones genéricas sin valor específico
- Estas instrucciones y comentarios
