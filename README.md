# agent-md-template

**Una plantilla práctica para documentar tu proyecto de forma que tanto humanos como IAs lo entiendan perfectamente.**

---

## 🤔 ¿Qué problema resuelve?

Imagina estas situaciones comunes:

- **Un nuevo desarrollador se une al equipo** y tarda semanas en entender cómo está organizado el proyecto, qué convenciones seguir, y dónde encontrar información clave.
- **Usas una IA (como GitHub Copilot, ChatGPT, Claude)** para ayudarte a programar, pero la IA no conoce las reglas específicas de tu proyecto y genera código que rompe las convenciones del equipo.
- **La documentación está dispersa** entre README.md, wikis, comentarios en código, mensajes de Slack... y nadie sabe dónde buscar la información correcta.
- **Cambias de proyecto cada cierto tiempo** y necesitas reaprender todo desde cero porque cada repo documenta las cosas de forma diferente.

**Esta plantilla resuelve todo esto.**

---

## 💡 ¿Qué es AGENTS.md?

\`AGENTS.md\` es un **documento único y centralizado** que concentra todo el contexto operativo de tu proyecto en un formato estándar. Piénsalo como el "manual de instrucciones" definitivo de tu aplicación.

### ¿Qué contiene?

Un AGENTS.md completo documenta:

1. **Información General**: Nombre, versión, tecnologías, propósito del proyecto
2. **Arquitectura**: Cómo está organizado el código (capas, patrones de diseño, principios SOLID)
3. **Dominio de Datos**: Entidades, tablas, relaciones, esquemas de base de datos
4. **Funcionalidades**: Qué hace el sistema, endpoints principales, módulos
5. **Configuración**: Variables de entorno, configuraciones necesarias
6. **Convenciones**: Cómo nombrar clases, funciones, archivos; cómo documentar código
7. **Scripts y Comandos**: Cómo instalar, ejecutar, compilar, testear
8. **Puntos Críticos**: Reglas que NUNCA se deben romper, mejores prácticas obligatorias
9. **Tareas Comunes**: Guías paso a paso para agregar features, endpoints, optimizar
10. **Debugging**: Dónde están los logs, problemas comunes y soluciones

### ¿Para quién es útil?

**Para desarrolladores humanos:**

- ✅ Onboarding de nuevos miembros en minutos, no en semanas
- ✅ Referencia rápida al programar: "¿cómo nombramos los DTOs aquí?"
- ✅ Consistencia entre equipos y proyectos
- ✅ Documentación siempre actualizada y en un solo lugar

**Para IAs y agentes de código:**

- ✅ La IA entiende las convenciones específicas de tu proyecto
- ✅ Genera código que sigue tus estándares automáticamente
- ✅ Respeta las reglas críticas ("NUNCA modifiques esta entidad directamente")
- ✅ Sugiere soluciones alineadas con tu arquitectura

---

## 🎯 ¿Cómo usar esta plantilla?

Esta plantilla (\`AGENTS_TEMPLATE.md\`) es una **guía estructurada** que te ayuda a crear tu propio \`AGENTS.md\` personalizado.

### Tres formas de usarla

####  Opción 1: Rellenarla manualmente (ideal para aprender)

**Cuándo usar:** Primera vez que creas un AGENTS.md, proyecto pequeño, o quieres entender bien cada sección.

**Pasos:**

1. Copia la plantilla a tu proyecto:
   \`\`\`bash
   # Clona este repositorio
   git clone https://github.com/AgnosticSix/agent-md-template.git
   
   # Copia la plantilla a tu proyecto
   cp agent-md-template/AGENTS_TEMPLATE.md /ruta/a/tu/proyecto/AGENTS.md
   \`\`\`

2. Abre \`AGENTS.md\` en tu editor favorito

3. Lee cada sección y complétala con información real de tu proyecto:
   - Reemplaza \`[nombre-del-proyecto]\` con el nombre real
   - Completa las tecnologías, versiones, configuraciones
   - Documenta tus convenciones actuales
   - Agrega ejemplos de código reales

4. Borra secciones que no apliquen (por ejemplo, si no usas Docker, borra esa sección)

5. Elimina los comentarios \`<!-- ... -->\` y el bloque de instrucciones iniciales

**Tiempo estimado:** 1-3 horas para un proyecto mediano

#### Opción 2: Usar una IA para generarlo (rápido y eficiente)

**Cuándo usar:** Proyecto grande con mucho código, quieres un borrador rápido, o ya tienes experiencia con AGENTS.md.

**Pasos:**

1. Abre tu IA favorita (ChatGPT, Claude, GitHub Copilot Chat)

2. Usa uno de estos prompts (copia y pega):

**Prompt básico:**
\`\`\`text
Actúa como un agente de documentación técnica. Genera un archivo AGENTS.md para este proyecto usando estrictamente la estructura y secciones de AGENTS_TEMPLATE.md.

Requisitos:
- Elimina el bloque de instrucciones iniciales y todos los comentarios <!-- ... --> del documento final.
- Completa solo con información verificada del repositorio; cuando falte información, usa un placeholder claro (por ejemplo: [PENDIENTE]) y sugiere dónde obtenerla.
- Mantén el tono claro y conciso en español.
- Conserva los encabezados, emojis y el formato Markdown.

Entrega: Un único archivo AGENTS.md listo para commit en la raíz del repo.
\`\`\`

**Prompt con contexto específico:**
\`\`\`text
Usa AGENTS_TEMPLATE.md como guía y genera AGENTS.md para este repositorio.

Enfócate en:
- Stack tecnológico y arquitectura observada.
- Dominio de datos y entidades encontradas.
- Variables de entorno y configuración.

Analiza estos archivos: package.json, src/**, docs/**, Dockerfile, docker-compose.yml.
No inventes datos: marca con [PENDIENTE] lo desconocido.
\`\`\`

**Prompt para proyectos específicos:**
\`\`\`text
Genera AGENTS.md (usando AGENTS_TEMPLATE.md) para un proyecto [Backend API | Frontend | Fullstack | CLI/Library].

- Si es Backend API: Detalla endpoints, base de datos y servicios.
- Si es Frontend: Componentes, estado, routing y UI.
- Si es CLI/Library: API pública, configuración y ejemplos de uso.

Rellena desconocidos con [PENDIENTE] y sugiere evidencias a revisar.
\`\`\`

3. Revisa el resultado y completa los [PENDIENTE]

4. Guarda el archivo en la raíz de tu proyecto como \`AGENTS.md\`

**Tiempo estimado:** 10-30 minutos

#### Opción 3: Híbrido (recomendado para la mayoría)

**Cuándo usar:** Proyecto mediano/grande, quieres velocidad pero también precisión.

**Pasos:**

1. Usa una IA para generar el borrador inicial (Opción 2)
2. Revisa sección por sección y ajusta:
   - Verifica que las tecnologías y versiones sean correctas
   - Completa las reglas críticas específicas de tu equipo
   - Agrega ejemplos de código reales
   - Documenta los "porqués" de decisiones arquitectónicas importantes
3. Comparte el borrador con el equipo para feedback
4. Ajusta y commitea

**Tiempo estimado:** 30 minutos - 1 hora

---

## 💡 Consejos para mejores resultados

### Si lo haces manualmente

- **No te abrumes:** Completa una sección a la vez
- **Empieza por lo básico:** Información General y Stack son las más fáciles
- **Pide ayuda al equipo:** La sección de "Puntos Importantes" debería ser colaborativa
- **Mantén ejemplos reales:** No inventes código, copia ejemplos de tu proyecto actual
- **Itera:** No tiene que ser perfecto desde el inicio, mejóralo con el tiempo

### Si usas una IA

- **Sé específico en el prompt:** Indica rutas de archivos clave (\`package.json\`, \`src/\`, etc.)
- **Pide que no invente:** Instrúyele explícitamente que use \`[PENDIENTE]\` para lo desconocido
- **Revisa todo:** Las IAs pueden alucinar o asumir cosas incorrectas
- **Proporciona contexto:** Menciona el tipo de proyecto (API REST, SPA, CLI, etc.)
- **Itera:** Si el resultado no es bueno, refina el prompt y vuelve a intentar

### Mantenimiento continuo

- **Actualiza cuando cambies arquitectura:** Si refactorizas o cambias tecnologías principales
- **Actualiza con nuevas convenciones:** Si el equipo adopta nuevas prácticas
- **Revisa trimestralmente:** Asegúrate que sigue siendo preciso
- **Involucra al equipo:** Es un documento vivo, todos deberían poder editarlo

---

## 🎓 Para principiantes

**Si eres nuevo en desarrollo o documentación, aquí hay una guía simple:**

### Términos que verás en la plantilla

- **Stack Tecnológico:** Las herramientas y lenguajes que usa tu proyecto (Node.js, Python, React, etc.)
- **Arquitectura:** Cómo está organizado tu código (por capas, módulos, etc.)
- **Entidad/Modelo:** Una representación de algo en tu base de datos (Usuario, Producto, etc.)
- **DTO (Data Transfer Object):** Un objeto que solo transporta datos entre capas
- **Endpoint:** Una URL de tu API que responde a peticiones (ej: \`/api/users\`)
- **CI/CD:** Integración Continua / Despliegue Continuo (automatización de tests y deploys)

### Empieza aquí

1. **Lee la plantilla completa primero** para familiarizarte con las secciones
2. **Completa solo estas secciones esenciales:**
   - Información General del Proyecto
   - Stack Tecnológico
   - Scripts y Comandos (cómo correr el proyecto)
3. **Pide ayuda** a un compañero más experimentado para las secciones de Arquitectura y Puntos Críticos
4. **Ve agregando más secciones** conforme aprendas más del proyecto

---

## 🚀 Para expertos

**Si ya tienes experiencia, aquí hay tips avanzados:**

### Personalización de la plantilla

- **Adapta secciones:** Agrega secciones específicas de tu dominio (ej: "Machine Learning Models", "Blockchain Contracts")
- **Integra con CI/CD:** Valida que AGENTS.md esté actualizado en cada PR
- **Genera automáticamente:** Crea scripts que extraigan info de \`package.json\`, \`pom.xml\`, etc.
- **Versiona por entorno:** Considera tener \`AGENTS.dev.md\`, \`AGENTS.prod.md\` si difieren mucho

### Casos de uso avanzados

1. **Multi-repo/Monorepo:** Un AGENTS.md raíz con enlaces a AGENTS.md de cada módulo
2. **Microservicios:** Plantilla extendida con sección "Dependencias entre Servicios"
3. **Open Source:** Usa AGENTS.md para facilitar contribuciones externas
4. **Compliance:** Documenta en "Seguridad y Compliance" los requisitos regulatorios

---

## ❓ Preguntas Frecuentes (FAQ)

### ¿Por qué se llama AGENTS.md y no CONTEXT.md o PROJECT.md?

Porque está diseñado específicamente para que "agentes" (humanos e IAs) entiendan el proyecto. El nombre hace explícita la intención de ser un documento consumible por sistemas automatizados.

### ¿Es obligatorio usar todas las secciones?

No. Usa solo las que apliquen a tu proyecto. Un proyecto pequeño puede tener un AGENTS.md de 2 páginas, uno enterprise puede tener 20.

### ¿Dónde va AGENTS.md en el repositorio?

En la raíz, junto al README.md. Así es fácil de encontrar tanto para humanos como para herramientas automatizadas.

### ¿AGENTS.md reemplaza al README.md?

No. Son complementarios:
- **README.md:** Para usuarios externos, cómo instalar/usar tu proyecto
- **AGENTS.md:** Para desarrolladores internos, cómo trabajar EN el proyecto

### ¿Cada cuánto debo actualizar AGENTS.md?

Actualízalo cuando:
- Cambies tecnologías principales (framework, base de datos)
- Refactorices la arquitectura
- Agregues convenciones nuevas importantes
- Encuentres que la información está desactualizada

Revisa trimestralmente para asegurar precisión.

### ¿Funciona para proyectos no-web?

¡Sí! Adapta las secciones. Para móvil agrega "Targets de compilación", para CLI agrega "Comandos disponibles", para ML agrega "Modelos y datasets", etc.

---

## 🤝 Contribuir

¿Tienes ideas para mejorar la plantilla? ¡Excelente!

**Formas de contribuir:**

1. **Reporta problemas:** Abre un [issue](https://github.com/AgnosticSix/agent-md-template/issues) si encuentras errores o secciones confusas
2. **Sugiere mejoras:** Propón nuevas secciones o mejoras a las existentes
3. **Comparte ejemplos:** Si creaste un AGENTS.md exitoso, comparte tu experiencia
4. **Envía un PR:** Mejoras de redacción, correcciones, nuevos ejemplos

---

## 📄 Licencia

Consulta el archivo [LICENSE](LICENSE) para más información.

---

## 🙏 Créditos

**Autor y Mantenedor:** [AgnosticSix](https://github.com/AgnosticSix)

**Inspirado en:**
- Buenas prácticas de documentación de GitHub
- Standard README
- Clean Architecture de Robert C. Martin
- Principios SOLID
- Experiencias reales de equipos de desarrollo

---

¿Listo para mejorar la documentación de tu proyecto? Empieza copiando \`AGENTS_TEMPLATE.md\` a tu repositorio y personalízalo. ¡Tu yo del futuro (y tu equipo) te lo agradecerán! 🚀
