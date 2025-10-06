# AGENTS.md - Plantilla de Contexto para Agentes de Código

> **INSTRUCCIONES PARA IA**: Esta es una plantilla para generar un documento AGENTS.md para cualquier proyecto.
> Completa cada sección con la información específica del proyecto analizado.
> Elimina estas instrucciones y los comentarios entre `<!-- -->` del documento final.

---

# AGENTS.md - Contexto del Proyecto para Agentes de Código

## 📋 Información General del Proyecto

### Identificación
<!-- Completar con información básica del proyecto -->
- **Nombre**: [nombre-del-proyecto]
- **Versión**: [versión actual, ej: 1.0.0]
- **Grupo/Organización**: [grupo maven, npm scope, namespace, etc.]
- **Descripción**: [Descripción breve del propósito del proyecto]
- **Puerto**: [puerto de ejecución si aplica]
- **Context Path**: [ruta base de la API si aplica]

### Stack Tecnológico
<!-- Listar todas las tecnologías, frameworks y versiones principales -->
- **Lenguaje**: [Java 21, Python 3.11, Node.js 20, etc.]
- **Framework Principal**: [Spring Boot 3.x, Django, Express, Next.js, etc.]
- **ORM/Database Layer**: [JPA/Hibernate, SQLAlchemy, TypeORM, etc.]
- **Base de Datos**: [PostgreSQL, MySQL, MongoDB, etc.]
- **Service Discovery**: [Eureka, Consul, etc. - si aplica]
- **Librerías Clave**: [Listar librerías importantes con versiones]
- **Build Tool**: [Maven, Gradle, npm, pip, etc.]
- **Contenedorización**: [Docker, Kubernetes - si aplica]

---

## 🏗️ Arquitectura del Proyecto

### Principios de Arquitectura Limpia (Clean Architecture)

Este proyecto sigue los principios de **Clean Architecture** para mantener el código desacoplado, testeable y mantenible:

#### Capas de la Arquitectura
<!-- Describir las capas específicas del proyecto -->

1. **Capa de Presentación (Controller/API/Views)**: 
   - Maneja las peticiones HTTP/gRPC/GraphQL y respuestas
   - Valida datos de entrada
   - Delega la lógica de negocio a los servicios
   - NO debe contener lógica de negocio

2. **Capa de Aplicación (Service/Use Cases)**: 
   - Contiene la lógica de negocio
   - Orquesta el flujo de datos
   - Es independiente del framework y la base de datos
   - Define interfaces (contratos) para la persistencia

3. **Capa de Dominio (Entity/Models/Domain)**: 
   - Contiene las reglas de negocio del dominio
   - Entidades y objetos de valor
   - Completamente independiente de frameworks externos

4. **Capa de Infraestructura (Repository/Persistence/External Services)**: 
   - Implementa los detalles técnicos
   - Acceso a base de datos
   - Servicios externos
   - Frameworks y herramientas

#### Regla de Dependencia
- Las dependencias apuntan HACIA ADENTRO
- Las capas internas NO conocen las capas externas
- El dominio no depende de la infraestructura
- Los servicios definen interfaces que la infraestructura implementa

### Principios SOLID

El código debe adherirse a los **principios SOLID**:

#### 1. Single Responsibility Principle (SRP)
- Cada clase debe tener una única responsabilidad
- Ejemplo: `[EntidadPrincipal]Service` solo maneja lógica de [entidad], no de [otra entidad]
- Los controladores solo manejan [protocolo de comunicación], no lógica de negocio

#### 2. Open/Closed Principle (OCP)
- Las clases deben estar abiertas a extensión pero cerradas a modificación
- Usar interfaces y composición sobre herencia
- Ejemplo: Nuevos tipos de validaciones sin modificar código existente

#### 3. Liskov Substitution Principle (LSP)
- Las implementaciones deben ser intercambiables con sus interfaces
- Los subtipos deben poder sustituir a sus tipos base
- Las implementaciones de servicios deben cumplir el contrato de la interfaz

#### 4. Interface Segregation Principle (ISP)
- Interfaces específicas son mejores que interfaces generales
- No forzar a las clases a implementar métodos que no usan
- Separar interfaces grandes en interfaces cohesivas más pequeñas

#### 5. Dependency Inversion Principle (DIP)
- Depender de abstracciones, no de implementaciones concretas
- Usar inyección de dependencias
- Las capas de alto nivel no deben depender de las de bajo nivel

### Estructura de Capas
<!-- Adaptar según la estructura real del proyecto -->
```
[raíz del proyecto]/
├── [capa_presentación]/     # [Descripción]
├── [capa_aplicación]/        # [Descripción]
│   └── [subcarpetas]/        # [Descripción]
├── [capa_dominio]/           # [Descripción]
│   ├── [entidades]/          # [Descripción]
│   └── [interfaces]/         # [Descripción]
├── [capa_infraestructura]/   # [Descripción]
├── [utilidades]/             # [Descripción]
└── [configuración]/          # [Descripción]
```

### Patrón de Diseño
<!-- Describir patrones arquitectónicos y de diseño utilizados -->
- **Arquitectura**: [Microservicios, Monolito Modular, Serverless, etc.]
- **Patrón Principal**: [MVC, MVP, MVVM, Clean Architecture, Hexagonal, etc.]
- **Patrón de Datos**: [Repository, DAO, Active Record, etc.]
- **Patrón de Mapeo**: [Mapper automático, manual, etc.]
- **Dependency Injection**: [Framework/método utilizado]
- **Interface-based Design**: [Cómo se implementa]

---

## 🗄️ Dominio de Datos

### Esquema de Base de Datos
<!-- Información sobre la base de datos -->
- **Schema/Database**: `[nombre_schema]`
- **Naming Strategy**: [Estrategia de nombres: snake_case, camelCase, etc.]
- **Migraciones**: [Herramienta: Flyway, Liquibase, Alembic, Sequelize, etc.]

### Entidades Principales ([N] total)
<!-- Listar y categorizar las entidades principales del dominio -->

#### Categoría 1: [Nombre de Categoría]
- [Entidad1], [Entidad2], [Entidad3]
- Descripción de la categoría y su propósito

#### Categoría 2: [Nombre de Categoría]
- [Entidad4], [Entidad5], [Entidad6]
- Descripción de la categoría y su propósito

#### Entidades de Negocio Principales
<!-- Describir las entidades más importantes con detalle -->
- **[EntidadClave1]**: [Descripción detallada, relaciones importantes]
- **[EntidadClave2]**: [Descripción detallada, relaciones importantes]
- **[EntidadClave3]**: [Descripción detallada, relaciones importantes]

#### Vistas/Consultas Materializadas
<!-- Si aplica -->
- **[Vista1]**: [Descripción y propósito]
- **[Vista2]**: [Descripción y propósito]

---

## 🔑 Funcionalidades Clave

### 1. [Funcionalidad Principal 1]
<!-- Describir cada funcionalidad importante del sistema -->
- [Descripción detallada]
- [Características principales]
- [Endpoints o puntos de entrada]
- **Documentación**: `[ruta a documento si existe]`

### 2. [Funcionalidad Principal 2]
- [Descripción detallada]
- [Características principales]
- [Endpoints o puntos de entrada]
- **Documentación**: `[ruta a documento si existe]`

### 3. [Funcionalidad Principal 3]
- [Descripción detallada]
- [Características principales]
- [Endpoints o puntos de entrada]
- **Documentación**: `[ruta a documento si existe]`

### 4. [Más funcionalidades según sea necesario]
- [Descripción]
- **Documentación**: `[ruta]`

---

## 🔧 Configuración

### Variables de Entorno Requeridas
<!-- Listar todas las variables de entorno necesarias -->
```bash
# Base de Datos
DB_HOST=[host de base de datos]
DB_PORT=[puerto]
DB_NAME=[nombre de bd]
DB_USER=[usuario]
DB_PASSWORD=[contraseña]

# API Keys y Servicios Externos
API_KEY_SERVICE=[descripción]
SERVICE_URL=[url del servicio]

# Configuración de la Aplicación
APP_PORT=[puerto]
APP_ENV=[development/production]
LOG_LEVEL=[nivel de logs]

# [Agregar más variables según el proyecto]
```

### Configuración de [Framework/Base de Datos]
<!-- Detalles importantes de configuración -->
- **[Configuración1]**: [valor y descripción]
- **[Configuración2]**: [valor y descripción]
- **[Configuración3]**: [valor y descripción]

### Configuración de Testing
<!-- Configuración específica para entorno de pruebas -->
- [Base de datos de prueba]
- [Servicios mockeados]
- [Configuraciones específicas]

---

## 📝 Convenciones de Código

### Documentación de Código

Todo el código debe estar documentado siguiendo las **convenciones estándar del lenguaje**:

<!-- PARA PROYECTOS JAVA -->
#### Estándares de Javadoc (Java)

- **Versión**: Javadoc compatible con [versión de Java]
- **Obligatorio**: Todas las clases públicas, interfaces, métodos públicos y protegidos deben tener Javadoc
- **Formato**: HTML5 estándar
- **Idioma**: [Español/Inglés]

##### Estructura para Clases

```java
/**
 * Descripción breve de la clase en una línea.
 * 
 * <p>Descripción detallada de la clase, su propósito y responsabilidades.</p>
 * 
 * @author [Nombre del Desarrollador]
 * @version [versión]
 * @since [versión del proyecto]
 * @see [Clases relacionadas]
 */
public class MiClase {
    // ...
}
```

##### Estructura para Métodos

```java
/**
 * Descripción breve del método.
 * 
 * <p>Descripción detallada del comportamiento.</p>
 * 
 * @param parametro descripción del parámetro
 * @return descripción del retorno
 * @throws Exception descripción de cuándo se lanza
 * @see [Referencias]
 */
public ReturnType metodo(ParamType parametro) {
    // ...
}
```

<!-- PARA PROYECTOS PYTHON -->
#### Estándares de Docstrings (Python)

- **Formato**: [Google Style, NumPy Style, reStructuredText]
- **Obligatorio**: Todas las clases, funciones y módulos públicos
- **Herramienta**: [Sphinx, pdoc, etc.]

```python
def funcion_ejemplo(parametro1: str, parametro2: int) -> bool:
    """
    Descripción breve de la función.
    
    Descripción detallada del comportamiento y casos de uso.
    
    Args:
        parametro1: Descripción del parámetro 1
        parametro2: Descripción del parámetro 2
    
    Returns:
        Descripción del valor de retorno
    
    Raises:
        ValueError: Descripción de cuándo se lanza
        
    Example:
        >>> funcion_ejemplo("test", 42)
        True
    """
    pass
```

<!-- PARA PROYECTOS JAVASCRIPT/TYPESCRIPT -->
#### Estándares de JSDoc/TSDoc (JavaScript/TypeScript)

- **Formato**: JSDoc 3 / TSDoc
- **Obligatorio**: Funciones exportadas, clases y métodos públicos
- **Herramienta**: TypeDoc, JSDoc

```typescript
/**
 * Descripción breve de la función.
 * 
 * Descripción detallada del comportamiento.
 * 
 * @param parametro1 - Descripción del parámetro
 * @param parametro2 - Descripción del parámetro
 * @returns Descripción del retorno
 * @throws {Error} Descripción del error
 * @example
 * ```ts
 * const resultado = miFuncion("test", 42);
 * ```
 */
function miFuncion(parametro1: string, parametro2: number): boolean {
    // ...
}
```

### Nomenclatura y Estilo

#### [Lenguaje]: Convenciones de Nomenclatura
<!-- Adaptar según el lenguaje del proyecto -->

**Clases/Tipos**:
- Formato: [PascalCase, snake_case, etc.]
- Ejemplo: `MiClase`, `UserRepository`
- Prefijos/Sufijos: [Si aplican, ej: `I` para interfaces, `Impl` para implementaciones]

**Métodos/Funciones**:
- Formato: [camelCase, snake_case, etc.]
- Ejemplo: `obtenerUsuario()`, `get_user()`
- Convenciones: [verbos de acción al inicio, etc.]

**Variables**:
- Formato: [camelCase, snake_case, etc.]
- Ejemplo: `nombreUsuario`, `user_name`
- Constantes: [UPPER_SNAKE_CASE, etc.]

**Archivos**:
- Formato: [kebab-case, PascalCase, snake_case]
- Ejemplo: `user-service.ts`, `UserService.java`, `user_service.py`

**Base de Datos**:
- Tablas: [snake_case, PascalCase, etc.]
- Columnas: [snake_case, camelCase, etc.]
- Prefijos para FK: [ej: `fk_`, `id_`, etc.]
- Prefijos para PK: [ej: `id_`, `pk_`, etc.]

### Organización de Archivos
<!-- Describir estructura y patrones de archivos -->

**[Tipo de Archivo 1]**: `[Patrón]`
- Request: `[Patrón]Request/Dto` 
- Response: `[Patrón]Response/Dto`
- Ejemplo: `UserRequestDto`, `UserResponseDto`

**[Tipo de Archivo 2]**: `[Patrón]`
- Interfaz: `[Patrón]Service`
- Implementación: `[Patrón]ServiceImpl`
- Ejemplo: `UserService`, `UserServiceImpl`

**[Tipo de Archivo 3]**: `[Patrón]`
- Controlador: `[Patrón]Controller`
- Repositorio: `[Patrón]Repository`

---

## 🚀 Scripts y Comandos

### Comandos de Desarrollo
```bash
# Instalación de dependencias
[comando para instalar dependencias]

# Ejecución en modo desarrollo
[comando para ejecutar en dev]

# Compilación/Build
[comando para compilar]

# Ejecución de tests
[comando para tests]

# Linting y formateo
[comando para lint]
[comando para format]

# [Otros comandos importantes]
```

### Scripts Personalizados
<!-- Si hay scripts SQL, bash, o de automatización -->
- `[nombre_script]`: [Descripción del propósito]
- `[otro_script]`: [Descripción del propósito]
- **Ubicación**: `[directorio de scripts]`

---

## 🐳 Docker y Despliegue

### Contenedorización
<!-- Si el proyecto usa Docker -->
- **Dockerfile**: [Descripción de stages si es multi-stage]
- **Docker Compose**: [Si aplica, servicios incluidos]
- **Imagen Base**: [Imagen utilizada]
- **Puerto Expuesto**: [Puerto]

### Despliegue
<!-- Información sobre deployment -->
- **Plataforma**: [Kubernetes, Cloud Run, EC2, Heroku, etc.]
- **CI/CD**: [GitHub Actions, GitLab CI, Jenkins, etc.]
- **Ambiente**: [Staging, Production, etc.]

---

## 📚 Documentación Adicional

### Documentos Disponibles
<!-- Listar documentación adicional del proyecto -->
1. **[NOMBRE_DOC.md]**: [Descripción breve del contenido]
2. **[NOMBRE_DOC.md]**: [Descripción breve del contenido]
3. **[NOMBRE_DOC.md]**: [Descripción breve del contenido]

### APIs y Endpoints
<!-- Si aplica -->
- **Documentación API**: [Swagger/OpenAPI, Postman, etc.]
- **URL Documentación**: [URL si está desplegada]
- **Colección**: [Ubicación de colección Postman u otros]

---

## ⚠️ Puntos Importantes para Agentes

### 1. [Área Crítica 1: ej. Modificación de Entidades]
<!-- Reglas estrictas que NUNCA se deben violar -->
- **NUNCA** [acción prohibida]
- **SIEMPRE** [acción requerida]
- [Más reglas específicas]

### 2. [Área Crítica 2: ej. Queries y Performance]
<!-- Mejores prácticas obligatorias -->
- Usar [técnica/patrón específico]
- Evitar [anti-patrón específico]
- Aplicar [optimización específica]

### 3. [Área Crítica 3: ej. DTOs y Validación]
<!-- Convenciones de datos -->
- [Regla de validación]
- [Regla de transformación]
- [Regla de serialización]

### 4. [Área Crítica 4: ej. Testing]
<!-- Estándares de testing -->
- Framework: [Jest, JUnit, pytest, etc.]
- Cobertura mínima: [porcentaje]
- Tests requeridos para: [casos específicos]
- Mocking: [librería y estrategia]

### 5. [Área Crítica 5: ej. APIs/Endpoints]
<!-- Convenciones de API -->
- Base path: `[ruta base]`
- Versionado: [estrategia]
- Formato de respuesta: [JSON, XML, etc.]
- Manejo de errores: [estrategia]
- Autenticación: [método]

### 6. [Área Crítica 6: ej. Base de Datos]
<!-- Gestión de BD -->
- Migraciones: [herramienta y proceso]
- Seeders: [si aplica]
- Backups: [estrategia]
- [Más consideraciones]

### 7. [Área Crítica 7: ej. Seguridad]
<!-- Consideraciones de seguridad -->
- [Prácticas de seguridad obligatorias]
- [Librerías de seguridad a usar]
- [Validaciones requeridas]
- [Manejo de secretos]

### 8. [Más áreas según necesidad]
<!-- Agregar tantas secciones como sea necesario -->
- [Reglas específicas]

---

## 🎯 Tareas Comunes

### Agregar una Nueva [Entidad/Feature]
<!-- Checklist paso a paso -->
1. [Paso 1: Crear modelo/entidad]
2. [Paso 2: Crear repositorio/DAO]
3. [Paso 3: Crear DTOs]
4. [Paso 4: Crear servicio]
5. [Paso 5: Crear controlador/endpoint]
6. [Paso 6: Agregar tests]
7. [Paso 7: Actualizar documentación]

### Agregar un Endpoint/Ruta
1. [Paso 1]
2. [Paso 2]
3. [Paso 3]
4. [Paso 4]

### Optimizar Performance
1. [Paso 1: Identificar bottleneck]
2. [Paso 2: Aplicar optimización]
3. [Paso 3: Medir impacto]
4. [Paso 4: Documentar cambio]

### [Otras tareas comunes del proyecto]
1. [Pasos específicos]

---

## 🔍 Debugging y Troubleshooting

### Logs
<!-- Configuración de logs -->
- **Ubicación**: [directorio de logs]
- **Nivel**: [INFO, DEBUG, etc.]
- **Formato**: [JSON, texto plano]
- **Rotación**: [estrategia de rotación]

### Problemas Comunes
<!-- Documentar problemas frecuentes y soluciones -->

#### [Problema 1]
- **Síntoma**: [Descripción]
- **Causa**: [Explicación]
- **Solución**: [Pasos para resolver]

#### [Problema 2]
- **Síntoma**: [Descripción]
- **Causa**: [Explicación]
- **Solución**: [Pasos para resolver]

---

## 📞 Información de Contexto

<!-- Contexto general del proyecto -->
- **Proyecto**: [Nombre completo del sistema]
- **Empresa/Organización**: [Nombre]
- **Tipo**: [Microservicio, Aplicación web, API, etc.]
- **Propósito**: [Descripción del propósito del proyecto]
- **Integración**: [Cómo se integra con otros sistemas]
- **Stakeholders**: [Equipos o personas clave]

---

## 📈 Métricas y Monitoring

<!-- Si aplica -->
- **Herramientas**: [Prometheus, Grafana, New Relic, etc.]
- **Métricas clave**: [Latencia, throughput, error rate, etc.]
- **Alertas**: [Configuración de alertas]
- **Dashboard**: [URL del dashboard si existe]

---

## 🔐 Seguridad y Compliance

<!-- Consideraciones de seguridad -->
- **Autenticación**: [JWT, OAuth, Session-based, etc.]
- **Autorización**: [RBAC, ABAC, etc.]
- **Encriptación**: [TLS, campos encriptados, etc.]
- **Auditoría**: [Logging de acciones, etc.]
- **Compliance**: [GDPR, HIPAA, etc. si aplica]

---

## 🌐 Internacionalización (i18n)

<!-- Si el proyecto maneja múltiples idiomas -->
- **Idiomas soportados**: [Lista de idiomas]
- **Librería**: [i18next, react-intl, etc.]
- **Archivos de traducción**: [Ubicación]
- **Idioma por defecto**: [idioma]

---

## 📱 Responsive y Compatibilidad

<!-- Para proyectos frontend -->
- **Browsers soportados**: [Chrome, Firefox, Safari, etc.]
- **Versiones mínimas**: [Especificar]
- **Mobile**: [iOS, Android - versiones]
- **Breakpoints**: [Responsive breakpoints si aplica]

---

## 🧪 Testing Strategy

### Tipos de Tests
- **Unitarios**: [Framework y cobertura esperada]
- **Integración**: [Scope y herramientas]
- **E2E**: [Herramienta: Cypress, Playwright, Selenium, etc.]
- **Performance**: [Herramientas de load testing]

### Comandos de Testing
```bash
# Tests unitarios
[comando]

# Tests de integración
[comando]

# Tests E2E
[comando]

# Cobertura
[comando]
```

---

## 🔄 Versionado y Releases

- **Estrategia**: [Semantic Versioning, CalVer, etc.]
- **Branches**: [GitFlow, trunk-based, etc.]
- **Changelog**: [Ubicación y formato]
- **Release Process**: [Descripción del proceso]

---

## 👥 Contribución

<!-- Guías para contribuidores -->
- **Proceso de PR**: [Descripción]
- **Code Review**: [Requisitos]
- **Standards**: [Link a guía de estilo]
- **Commits**: [Conventional commits, etc.]

---

**Última actualización**: [YYYY-MM-DD]
**Versión del documento**: [X.Y.Z]
**Mantenedor**: [Nombre/Equipo]

---

## 📋 Checklist para Completar esta Plantilla

Al generar un AGENTS.md desde esta plantilla, asegúrate de:

- [ ] Analizar completamente el proyecto
- [ ] Identificar todas las tecnologías y versiones
- [ ] Mapear la estructura de directorios
- [ ] Documentar todas las entidades del dominio
- [ ] Listar variables de entorno requeridas
- [ ] Incluir ejemplos de código reales del proyecto
- [ ] Documentar convenciones de nomenclatura observadas
- [ ] Identificar patrones de diseño utilizados
- [ ] Listar comandos funcionales (verificados)
- [ ] Incluir información de seguridad relevante
- [ ] Eliminar secciones que no apliquen al proyecto
- [ ] Agregar secciones adicionales específicas del proyecto
- [ ] Verificar que toda la información sea precisa
- [ ] Eliminar estos comentarios e instrucciones

---

## 💡 Notas para la IA Generadora

**Cómo usar esta plantilla**:

1. **Analiza el proyecto completo**: Lee archivos clave como `package.json`, `pom.xml`, `requirements.txt`, configuraciones, etc.

2. **Identifica el stack tecnológico**: Determina lenguajes, frameworks, bases de datos, y herramientas.

3. **Mapea la arquitectura**: Identifica cómo está organizado el código y qué patrones sigue.

4. **Extrae entidades y dominio**: Encuentra modelos, entidades, tablas, y sus relaciones.

5. **Documenta funcionalidades**: Identifica los módulos principales y qué hace cada uno.

6. **Captura convenciones**: Observa patrones de nomenclatura, estructura de archivos, y estándares de código.

7. **Incluye ejemplos reales**: Usa snippets del código actual, no genéricos.

8. **Personaliza secciones**: Elimina lo que no aplique, agrega lo que falte.

9. **Verifica comandos**: Asegúrate que los comandos listados funcionan.

10. **Sé específico**: Evita generalidades, proporciona información precisa y verificable.

**Secciones críticas** (no omitir):
- Información General y Stack
- Arquitectura y Principios SOLID
- Estructura de Capas
- Dominio de Datos
- Convenciones de Código y Documentación
- Puntos Importantes para Agentes

**Adapta según el tipo de proyecto**:
- **Backend API**: Enfócate en endpoints, base de datos, servicios
- **Frontend**: Enfócate en componentes, estado, routing, UI
- **Fullstack**: Balancea ambos aspectos
- **CLI/Library**: Enfócate en API pública, configuración, uso

**Tono y estilo**:
- Claro y conciso
- Usa listas y bullets
- Incluye emojis para secciones (mejora legibilidad)
- Formato markdown correcto
- Ejemplos de código con syntax highlighting

