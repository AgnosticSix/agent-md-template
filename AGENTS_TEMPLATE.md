# AGENTS.md - Plantilla de Contexto para Agentes de Código

> **INSTRUCCIONES PARA IA**: Esta es una plantilla para generar un documento AGENTS.md para cualquier proyecto.
> Completa cada sección con la información específica del proyecto analizado.
> Elimina estas instrucciones y los comentarios entre `<!-- -->` del documento final.
> 
> **IMPORTANTE**: Este documento debe usarse junto con [SKILLS.md](./SKILLS.md):
> - **AGENTS.md** (este archivo): Define QUÉ es el proyecto, CÓMO está estructurado
> - **SKILLS.md**: Define QUÉ PUEDE HACER el agente, procedimientos y tareas ejecutables

---

# AGENTS.md - Contexto del Proyecto para Agentes de Código

## 📖 Propósito de este Documento

Este documento proporciona el **contexto fundamental** del proyecto para agentes de código (IA).
Describe la arquitectura, estructura, convenciones y reglas del proyecto.

**Documentos complementarios**:
- **[SKILLS.md](./SKILLS.md)**: Habilidades, capacidades y procedimientos ejecutables
- **README.md**: Información general y guía de inicio para humanos
- **Documentación técnica**: Detalles de implementación y APIs

## � Relación AGENTS.md ↔ SKILLS.md

**División de responsabilidades**:

| AGENTS.md (este documento) | SKILLS.md |
|---------------------------|----------|
| ✅ QUÉ es el proyecto | ✅ QUÉ PUEDE HACER el agente |
| ✅ CÓMO está estructurado | ✅ CÓMO ejecutar tareas |
| ✅ Arquitectura y patrones | ✅ Procedimientos paso a paso |
| ✅ Convenciones y reglas | ✅ Comandos y herramientas |
| ✅ Entidades y dominio | ✅ Ejemplos de código ejecutable |
| ✅ Configuración del proyecto | ✅ Checklists y verificaciones |

**Flujo de trabajo recomendado**:
1. Lee **AGENTS.md** para entender el contexto del proyecto
2. Consulta **SKILLS.md** para encontrar la skill apropiada para tu tarea
3. Ejecuta el procedimiento siguiendo las convenciones de AGENTS.md

---

## �📋 Información General del Proyecto

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

<!-- Para cada funcionalidad, describe QUÉ hace y CÓMO está estructurada.
     Para procedimientos de CÓMO IMPLEMENTAR, ver SKILLS.md -->

### 1. [Funcionalidad Principal 1]
**Descripción**: [Descripción detallada de qué hace esta funcionalidad]

**Módulos involucrados**:
- [Módulo/Servicio 1]: [Responsabilidad]
- [Módulo/Servicio 2]: [Responsabilidad]

**Endpoints/Puntos de entrada**:
- `[METHOD] /api/path`: [Descripción]
- `[METHOD] /api/path`: [Descripción]

**Entidades relacionadas**: [Entity1, Entity2, Entity3]

**Skills relacionadas**: Ver [SKILLS.md - Skill Específica](./SKILLS.md#skill-específica)

**Documentación adicional**: `[ruta a documento si existe]`

---

### 2. [Funcionalidad Principal 2]
**Descripción**: [Descripción detallada]

**Módulos involucrados**:
- [Módulo]: [Responsabilidad]

**Endpoints/Puntos de entrada**:
- `[METHOD] /api/path`: [Descripción]

**Entidades relacionadas**: [Entidades]

**Skills relacionadas**: Ver [SKILLS.md](./SKILLS.md)

**Documentación adicional**: `[ruta]`

---

### 3. [Funcionalidad Principal 3]
**Descripción**: [Descripción detallada]

**Flujo de datos**:
```
[Cliente] -> [Controller] -> [Service] -> [Repository] -> [Database]
                              ↓
                        [External API]
```

**Módulos involucrados**: [Lista]

**Skills relacionadas**: Ver [SKILLS.md](./SKILLS.md)

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

> **REGLAS CRÍTICAS**: Estas reglas NUNCA deben violarse. Son específicas de este proyecto.
> Para procedimientos y mejores prácticas generales, consulta [SKILLS.md](./SKILLS.md)

### 1. [Área Crítica 1: ej. Modificación de Entidades]
**Contexto**: [Por qué es crítica esta área]

**Reglas estrictas**:
- ❌ **NUNCA** [acción prohibida] porque [razón]
- ✅ **SIEMPRE** [acción requerida] porque [razón]
- ⚠️ **PRECAUCIÓN** [acción que requiere cuidado]

**Ejemplo correcto**:
```[lenguaje]
// Código de ejemplo que muestra la forma correcta
```

**Ejemplo incorrecto**:
```[lenguaje]
// Código de ejemplo que muestra lo que NO hacer
```

**Ver también**: [SKILLS.md - Skill Relacionada](./SKILLS.md#skill)

---

### 2. [Área Crítica 2: ej. Queries y Performance]
**Contexto**: [Por qué es crítica esta área]

**Reglas**:
- ✅ Usar [técnica/patrón específico] para [caso de uso]
- ❌ Evitar [anti-patrón específico] porque [impacto]
- 🎯 Aplicar [optimización específica] cuando [condición]

**Threshold de performance**:
- Queries: < [X]ms
- Endpoints: < [Y]ms
- [Otra métrica]: < [Z]

**Ver también**: [SKILLS.md - Performance Optimization](./SKILLS.md#performance-optimization)

---

### 3. [Área Crítica 3: ej. DTOs y Validación]
**Contexto**: [Por qué es crítica esta área]

**Reglas de validación**:
- [Campo]: [Regla y razón]
- [Campo]: [Regla y razón]

**Reglas de transformación**:
- [Transformación]: [Cuándo y cómo]

**Ejemplo de DTO válido**:
```[lenguaje]
// Ejemplo real del proyecto
```

---

### 4. [Área Crítica 4: ej. Testing]
**Contexto**: Estándares de calidad obligatorios

**Requisitos mínimos**:
- Framework: [Jest, JUnit, pytest, etc.]
- Cobertura mínima: [porcentaje]%
- Tests obligatorios para:
  - [Caso 1]
  - [Caso 2]
  - [Caso 3]

**Estrategia de mocking**: [Descripción]

**Ver también**: [SKILLS.md - Testing & Quality Assurance](./SKILLS.md#testing--quality-assurance)

---

### 5. [Área Crítica 5: ej. APIs/Endpoints]
**Contexto**: Convenciones de API que deben respetarse

**Estándares**:
- Base path: `[ruta base]`
- Versionado: [estrategia - ej: `/v1/`, header, etc.]
- Formato respuesta: [JSON, XML, etc.]
- Status codes:
  - `200`: [Uso]
  - `201`: [Uso]
  - `400`: [Uso]
  - `401`: [Uso]
  - `404`: [Uso]
  - `500`: [Uso]

**Estructura de respuesta**:
```json
{
  "[campo]": "[descripción]",
  "[campo]": "[descripción]"
}
```

**Manejo de errores**:
```json
{
  "error": {
    "code": "[CODE]",
    "message": "[mensaje]",
    "details": {}
  }
}
```

**Autenticación**: [Método y detalles]

**Ver también**: [SKILLS.md - API Development](./SKILLS.md#api-development)

---

### 6. [Área Crítica 6: ej. Base de Datos]
**Contexto**: Gestión de base de datos

**Reglas de migraciones**:
- Herramienta: [Flyway, Liquibase, Alembic, etc.]
- Naming: `[patrón de nombre]`
- ❌ NUNCA modificar migraciones ya aplicadas
- ✅ SIEMPRE crear nueva migración para cambios

**Naming de columnas/tablas**: [Estrategia]

**Backups**: [Estrategia y frecuencia]

**Ver también**: [SKILLS.md - Database Management](./SKILLS.md#database-management)

---

### 7. [Área Crítica 7: ej. Seguridad]
**Contexto**: Prácticas de seguridad obligatorias

**Validación y sanitización**:
- ✅ Validar TODOS los inputs del usuario
- ✅ Usar [librería de validación]
- ❌ NUNCA confiar en datos del cliente

**Secretos y credenciales**:
- ✅ Usar variables de entorno
- ❌ NUNCA hardcodear secretos
- ✅ Usar [servicio de secrets: AWS Secrets Manager, etc.]

**Librerías de seguridad**:
- [Librería 1]: [Propósito]
- [Librería 2]: [Propósito]

**Ver también**: [SKILLS.md - Authentication & Authorization](./SKILLS.md#authentication--authorization)

---

## 🎯 Tareas Comunes

> **NOTA**: Esta sección proporciona un overview rápido. Para procedimientos detallados paso a paso,
> consulta [SKILLS.md - Procedimientos Estándar](./SKILLS.md#procedimientos-estándar)

### Agregar una Nueva [Entidad/Feature]
**Quick checklist**:
1. Crear modelo/entidad en `[directorio]`
2. Crear repositorio en `[directorio]`
3. Crear DTOs en `[directorio]`
4. Implementar servicio en `[directorio]`
5. Crear controlador/endpoint en `[directorio]`
6. Agregar tests en `[directorio]`
7. Actualizar documentación

**Ver procedimiento completo**: [SKILLS.md - Agregar Nueva Funcionalidad](./SKILLS.md#procedimiento-agregar-nueva-funcionalidad)

**Skills necesarias**: 
- [Skill 1: Database Management](./SKILLS.md#database-management)
- [Skill 2: API Development](./SKILLS.md#api-development)
- [Skill 3: Testing](./SKILLS.md#testing--quality-assurance)

---

### Agregar un Endpoint/Ruta
**Quick checklist**:
1. Definir ruta en controlador siguiendo patrón: `[patrón]`
2. Implementar DTOs de request/response
3. Agregar validaciones
4. Implementar lógica en servicio
5. Agregar tests
6. Actualizar documentación API

**Ver procedimiento completo**: [SKILLS.md - API Development](./SKILLS.md#api-development)

---

### Optimizar Performance
**Quick checklist**:
1. Identificar bottleneck con [herramienta]
2. Analizar queries/código problemático
3. Aplicar optimización (caching, indexing, etc.)
4. Medir impacto
5. Documentar cambio

**Ver procedimiento completo**: [SKILLS.md - Performance Optimization](./SKILLS.md#performance-optimization)

---

### Debugging de Problemas
**Ver procedimiento completo**: [SKILLS.md - Debugging de Problemas](./SKILLS.md#procedimiento-debugging-de-problemas)

### Refactoring de Código
**Ver procedimiento completo**: [SKILLS.md - Refactoring de Código](./SKILLS.md#procedimiento-refactoring-de-código)

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

Al generar AGENTS.md + SKILLS.md desde estas plantillas, asegúrate de:

### AGENTS.md (Contexto del Proyecto)
- [ ] Analizar completamente el proyecto
- [ ] Identificar todas las tecnologías y versiones
- [ ] Mapear la estructura de directorios
- [ ] Documentar todas las entidades del dominio
- [ ] Listar variables de entorno requeridas
- [ ] Incluir ejemplos de código reales del proyecto
- [ ] Documentar convenciones de nomenclatura observadas
- [ ] Identificar patrones de diseño utilizados
- [ ] Incluir información de seguridad relevante
- [ ] Eliminar secciones que no apliquen al proyecto
- [ ] Agregar secciones adicionales específicas del proyecto
- [ ] Crear referencias cruzadas a SKILLS.md
- [ ] Verificar que toda la información sea precisa
- [ ] Eliminar estos comentarios e instrucciones

### SKILLS.md (Capacidades y Procedimientos)
- [ ] Identificar skills requeridas según tipo de proyecto (frontend/backend)
- [ ] Documentar procedimientos estándar del proyecto
- [ ] Incluir comandos verificados y funcionales
- [ ] Agregar skills personalizadas específicas del proyecto
- [ ] Crear ejemplos de código ejecutables
- [ ] Documentar checklist de verificación para cada procedimiento
- [ ] Incluir quick reference de comandos
- [ ] Crear skill matrix para referencia rápida
- [ ] Referencias cruzadas a AGENTS.md donde sea relevante
- [ ] Eliminar skills no aplicables al proyecto
- [ ] Eliminar comentarios e instrucciones

### Integración
- [ ] Verificar que las referencias cruzadas funcionen
- [ ] Asegurar consistencia entre ambos documentos
- [ ] No duplicar información (división clara de responsabilidades)
- [ ] AGENTS.md enfocado en QUÉ/CÓMO es el proyecto
- [ ] SKILLS.md enfocado en QUÉ/CÓMO HACER tareas

---

## 💡 Notas para la IA Generadora

**Flujo de trabajo para generar documentación completa**:

### Paso 1: Análisis del Proyecto
1. **Analiza el proyecto completo**: Lee `package.json`, `pom.xml`, `requirements.txt`, configs, etc.
2. **Identifica el stack tecnológico**: Lenguajes, frameworks, bases de datos, herramientas
3. **Determina el tipo**: Backend, Frontend, Fullstack, CLI, Library
4. **Mapea la arquitectura**: Organización del código, patrones, capas
5. **Extrae entidades y dominio**: Modelos, tablas, relaciones
6. **Identifica funcionalidades**: Módulos principales y sus responsabilidades

### Paso 2: Generar AGENTS.md
**Enfoque**: Contexto del proyecto - QUÉ es y CÓMO está estructurado

**Incluir**:
- ✅ Información general y stack tecnológico
- ✅ Arquitectura, capas y principios SOLID
- ✅ Estructura de directorios
- ✅ Entidades y dominio de datos
- ✅ Convenciones de nomenclatura y estilo
- ✅ Reglas críticas específicas del proyecto
- ✅ Configuración y variables de entorno
- ✅ Referencias a SKILLS.md para procedimientos

**Evitar**:
- ❌ Procedimientos paso a paso detallados (van en SKILLS.md)
- ❌ Comandos de ejecución (van en SKILLS.md)
- ❌ Ejemplos de tareas específicas (van en SKILLS.md)

### Paso 3: Generar SKILLS.md
**Enfoque**: Capacidades del agente - QUÉ PUEDE HACER y CÓMO ejecutarlo

**Incluir**:
- ✅ Skills básicas según tipo (Frontend/Backend)
- ✅ Skills personalizadas del proyecto
- ✅ Procedimientos estándar paso a paso
- ✅ Comandos verificados y funcionales
- ✅ Ejemplos de código ejecutables
- ✅ Checklists de verificación
- ✅ Quick reference de comandos
- ✅ Referencias a AGENTS.md para contexto

**Priorizar skills según frecuencia de uso en el proyecto**

### Paso 4: Integración
- ✅ Crear referencias cruzadas claras entre ambos documentos
- ✅ Asegurar consistencia en terminología
- ✅ Evitar duplicación de información
- ✅ División clara de responsabilidades:
  - AGENTS.md = Conocimiento del proyecto
  - SKILLS.md = Capacidades de acción

**Secciones críticas de AGENTS.md** (no omitir):
- Relación AGENTS.md ↔ SKILLS.md
- Información General y Stack
- Arquitectura y Principios SOLID
- Estructura de Capas
- Dominio de Datos
- Convenciones de Código
- Puntos Importantes para Agentes

**Secciones críticas de SKILLS.md** (no omitir):
- Skills Básicas (Frontend o Backend según corresponda)
- Skills Específicas del Proyecto
- Procedimientos Estándar
- Quick Reference de Comandos

**Adapta según el tipo de proyecto**:
- **Backend API**: 
  - AGENTS.md: arquitectura de servicios, entidades, APIs
  - SKILLS.md: Database Management, API Development, Testing
- **Frontend**: 
  - AGENTS.md: estructura de componentes, estado, routing
  - SKILLS.md: Component Development, State Management, UI/UX
- **Fullstack**: 
  - AGENTS.md: arquitectura completa (cliente y servidor)
  - SKILLS.md: balance de skills frontend + backend
- **CLI/Library**: 
  - AGENTS.md: API pública, configuración
  - SKILLS.md: Usage patterns, testing, packaging

**Tono y estilo** (ambos documentos):
- Claro y conciso
- Usa listas y bullets
- Incluye emojis para secciones (mejora legibilidad)
- Formato markdown correcto
- Ejemplos de código con syntax highlighting
- Información específica y verificable, no genérica

