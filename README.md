un# Rubén Darío Carrillo López  
**Desarrollador de Software Full Stack**

---

## 📞 Contacto
- **Email:** rubendario921@hotmail.com  
- **Teléfono:** +593 0984322045

---

## 🎯 Perfil Profesional
Desarrollador de Software con sólida experiencia en desarrollo de aplicaciones web empresariales bajo arquitecturas modernas. Especializado en Frontend con Angular 17+ y Backend con .NET 8+ y Node.js (NestJS). Enfoque en calidad, escalabilidad y mejora continua.

---

## 💼 Experiencia Laboral

### **Desarrollador de Software** – NetBy IT Consulting  
*Octubre 2025 – Presente*  
- Diseño y desarrollo de aplicaciones escalables con arquitectura hexagonal y microservicios.  
- Implementación de Microfrontends con Angular 17+ y Nx, mejorando modularidad y UX.  
- Desarrollo de APIs RESTful con .NET 8+ y C#, integrando SQL Server mediante Entity Framework.  
- Gestión de pipelines CI/CD en Azure DevOps, optimizando despliegues.  
- Participación en equipos ágiles (Scrum) y revisiones de código.  

**Tecnologías:** C#, .NET 8+, Angular 17+, Microfrontends, Nx, SQL Server, Docker, Azure DevOps, Git  

### **Desarrollador de Software** – Nexti Business Solutions  
*Julio 2025 – Octubre 2025*  
- Desarrollo de APIs RESTful y GraphQL con .NET 8+ y NestJS.  
- Colaboración en migración de sistemas legacy a arquitectura moderna.  
- Mejora de interfaces con Angular 17+ y optimización de rendimiento.  

**Tecnologías:** C#, .NET 8+, NestJS, GraphQL, Angular 17+, SQL Server, Azure DevOps   

### **Desarrollador de Software** – BusinessWare Corp  
*Octubre 2024 – Julio 2025*  
- Participación en diseño, desarrollo y aseguramiento de calidad de aplicaciones.  
- Investigación e implementación de nuevas tecnologías y prácticas DevOps.  

**Tecnologías:** C#, .NET 8+, ASPX, Telerik, Docker, SQL Server, Azure DevOps  


# Instrucciones de Contexto para el Proyecto Final

## Perfil del Proyecto
- **Backend:** .NET 8/9, Web API, Entity Framework Core.
- **Frontend:** Angular (v17+), TypeScript, Arquitectura basada en componentes y servicios.
- **Estilo de Documentación:** Académico y profesional para entrega de fin de carrera.

## Reglas de Skill para Documentación
1. **Comentarios XML:** Siempre que se genere documentación en C#, usar el estándar de Microsoft (`<summary>`, `<param>`, `<returns>`). 
2. **JSDoc:** Para Angular/TypeScript, usar el estándar JSDoc explicando tipos de datos y propósitos de los métodos.
3. **Diagramas:** Preferir siempre Mermaid.js para diagramas de flujo, secuencia y entidad-relación.
4. **Idioma:** Toda la documentación pública y comentarios deben estar en español técnico profesional.

## Reglas de Arquitectura
- El código debe seguir principios SOLID y Clean Code.
- En .NET, separar claramente las Entities de los DTOs.
- En Angular, la lógica de negocio debe estar en Services, no en Components.

### **Desarrollador de Software** – Milenium360  
*Febrero 2024 – Octubre 2024*  
- Desarrollo de APIs y microservicios para gestión de datos.  
- Diseño de interfaces con enfoque UX/UI usando Angular y Tailwind CSS.  
- Metodología ágil Scrum.  

**Tecnologías:** C#, .NET 8+, Angular, Tailwind CSS, SQL Server, GitHub  

### **Desarrollador de Software** – GsColden  
*Octubre 2022 – Febrero 2024*  
- Desarrollo de soluciones con Python (Django) y Angular.  
- Creación de dashboards, KPIs y automatización de procesos.  
- Soporte técnico y control de operación.  

**Tecnologías:** Python, Django, Angular, Bootstrap, GitLab  

### **Prácticas Preprofesionales** – Jr Electry Supply  
*Enero 2023 – Marzo 2023*  
- Desarrollo de aplicaciones web con HTML, CSS, JavaScript y Angular.  
- Mantenimiento de sistemas y versionado con Git.  

**Tecnologías:** TypeScript, Node.js, NestJS, Angular, Bootstrap, GitLab  

### **Supervisor Contact Center** – Resona Contact Center  
*Marzo 2019 – Julio 2022*  
- Gestión de equipos, análisis de datos y control de indicadores.  
- Toma de decisiones operativas y cumplimiento de metas.  

---

## 🎓 Educación
- **Tecnología Superior en Desarrollo de Software** – Instituto Tecnológico Cordillera  
- **Tecnología Superior en Gestión del Talento Humano** – Instituto Tecnológico Cordillera  
- **Bachiller en Aplicaciones en Ciencias Informáticas** – Colegio Militar Nº 10 “Abdón Calderón”  

---

## 📜 Certificaciones
- Angular 17 – Udemy (Fernando Herrera)  
- CRUD Angular + .NET Core + Entity Framework – Udemy (Tomás Ruiz Díaz)  
- Analítica y Modelado de Datos con SQL – Ciencias de Datos Ecuador  
- Administración de Recursos Humanos – UTPL  
- C# .NET 8+ API Rest – Udemy (Alex Joel Pagoada)  
- NestJS: Node + TypeScript crear APIs – Udemy (Alejandro Lora)  

---

## 🛠️ Habilidades Técnicas
| Categoría | Tecnologías |
|-----------|-------------|
| **Lenguajes** | C#, TypeScript/JavaScript, Python, Java, SQL |
| **Frontend** | Angular 17+, Bootstrap, Tailwind CSS, Microfrontends, Nx |
| **Backend** | .NET 8+, NestJS, Django, Spring Boot, REST API, GraphQL, Microservicios |
| **Bases de Datos** | SQL Server, PostgreSQL, Entity Framework |
| **DevOps** | Git, GitHub, GitLab, Azure DevOps, Docker |
| **Arquitecturas** | Hexagonal, MVC, Microservicios |
| **Herramientas** | Power BI, Office |
| **Metodologías** | Scrum, Kanban |

---

## 🌐 Idiomas
- **Español:** Nativo  
- **Inglés:** Nivel B2 (Intermedio oral y escrito)  

---

# Script de Automatización de Documentación con Copilot CLI
Write-Host "🚀 Iniciando proceso de documentación técnica..." -ForegroundColor Cyan

# 1. Documentación de Código (Comentarios XML)
Write-Host "📝 Paso 1: Generando comentarios XML en el código..." -ForegroundColor Yellow
gh copilot suggest "Añade comentarios XML (<summary>, <param>, <returns>) a todos los métodos públicos en Controllers, DTOs y Entities de mi solución .NET siguiendo Clean Code. No cambies la lógica, solo añade los comentarios." 

# 2. Generación del Informe Técnico (Wiki)
Write-Host "📊 Paso 2: Generando Informe Técnico y Arquitectura..." -ForegroundColor Yellow
$reportPrompt = @"
Analiza mi solución .NET completa y genera un informe técnico en Markdown con:
- Resumen ejecutivo.
- Análisis de arquitectura por capas (Explicando la jerarquía de carpetas).
- Detalle de Seguridad (JWT, Middlewares).
- Guía de instalación y configuración del appsettings.json.
Estructura la respuesta con encabezados claros.
"@
gh copilot suggest $reportPrompt > Informe_Tecnico.md

# 3. Generación del Diagrama de Base de Datos (Mermaid)
Write-Host "🧜‍♂️ Paso 3: Generando diagrama de Entidad-Relación (Mermaid)..." -ForegroundColor Yellow
gh copilot suggest "Basado en mis clases de Entity Framework, genera un diagrama ER en formato Mermaid.js. Incluye relaciones 1:N y M:N." >> Informe_Tecnico.md

Write-Host "✅ ¡Proceso completado! Revisa Informe_Tecnico.md y los cambios en tu código." -ForegroundColor Green