# =================================================================
# AUTOMATIZACIÓN DE DOCUMENTACIÓN CON COPILOT CLI
# =================================================================

$PROYECTO_NOMBRE = "Documentacion_Tecnica" # Cambia esto por el nombre de tu proyecto
$OUTPUT_FILE = "Wiki_Tecnica.md"

# Lectura del Proyecto o Solucion
Write-Host " Lectura del Proyecto - Stack Tecnologico" -ForegroundColor Yellow

#Promt inicial para generar el Stack Tecnologico
$reportPrompt = "Realiza un análisis exhaustivo de la solución: lee la estructura de archivos y su contenido. Entrega un Stack Tecnologico en formato Markdown(encabezados y listas claras)"
copilot -p "suggest $reportPrompt" | Out-File -FilePath "Stack_Tecnologico.md" -Encoding UTF8

# Carga el contenido para usarlo como contexto real
$stack = Get-Content ".\Stack_Tecnologico.md" -Raw

# Definición de "Skills" (Contexto que se enviará en cada petición)
$SKILLS_CONTEXT = @"
Contexto (Stack Tecnológico detectado):
$stack
Reglas:
- Usa Clean Code.
- No cambies la lógica de negocio.
- Tono técnico profesional en español.
"@

Clear-Host
Write-Host " COPILOT CLI: GENERADOR DE DOCUMENTO .NET" -ForegroundColor Cyan
Write-Host "======================================================" -ForegroundColor Cyan

# 1. Aplicar Comentarios XML al código fuente
Write-Host "`n[1/5] 📝 Documentando código fuente (XML)..." -ForegroundColor Yellow
$promptXml = "$SKILLS_CONTEXT Analiza todos los .cs en Controllers, Services, DTOs y Models. Genera bloques <summary>, <param> y <returns>usando comentarios XML nativos de C# para cada método y clase."
copilot -p "suggest $promptXml"

# 2. Generar Informe Técnico de Arquitectura
Write-Host "[2/5] 🏛️ Generando análisis de arquitectura..." -ForegroundColor Yellow
$promptArch = "$SKILLS_CONTEXT Lee la estructura de archivos y explica la jerarquía de capas, inyección de Dependencias y el flujo de datos. Genera un informe tecnico en Markdown con:
- Resumen ejecutivo.
- Análisis de arquitectura por capas (Explicando la jerarquía de carpetas).
- Detalle de Seguridad (JWT, Middlewares).
- Guía de instalación y configuración del appsettings.json.
Estructura la respuesta con encabezados claros.
Formatea como Markdown."
copilot -p "suggest $promptArch" ` | Out-File -FilePath $OUTPUT_FILE -Encoding utf8

# 3. Generar Diagrama de Base de Datos
Write-Host "[3/5] 📊 Generando diagrama de Entidad-Relación..." -ForegroundColor Yellow
$promptDb = "$SKILLS_CONTEXT Basado en las clases de DbContext y Entities, genera un diagrama Mermaid.js tipo erDiagram."
$mermaidResult = copilot -p "suggest $promptDb"
Add-Content -Path $OUTPUT_FILE -Value "`n## Diagrama de Entidad-Relación`n" -Encoding UTF8
Add-Content -Path $OUTPUT_FILE -Value "```mermaid" -Encoding UTF8
Add-Content -Path $OUTPUT_FILE -Value $mermaidResult -Encoding UTF8

# 4. Auditoría de Seguridad y Configuración
Write-Host "[4/5] 🔐 Analizando seguridad y appsettings..." -ForegroundColor Yellow
$promptSec = "$SKILLS_CONTEXT Explica cómo se maneja la autenticación y qué variables requiere el appsettings.json para funcionar."
copilot -p "suggest $promptSec" >> $OUTPUT_FILE

# 5. Generacion del Historial de Cambios
Write-Host "`n[5/5] 📝 Generando Historial de Cambios..." -ForegroundColor Yellow
$promptCommit = "$SKILLS_CONTEXT Revisa mis últimos 5 commits y genera un resumen en Markdown para la sección Historial_de_cambios, explicando las funcionalidades que se modificaron o agregaron"
copilot -p "suggest $promptCommit" | Out-File -FilePath "Historial_de_cambios.md" -Encoding utf8

Write-Host "`n======================================================" -ForegroundColor Green
Write-Host " ✅ PROCESO FINALIZADO CON ÉXITO" -ForegroundColor Green
Write-Host " ✅Archivo generado: $OUTPUT_FILE" -ForegroundColor Green
Write-Host "✅ Revisa los informes y los cambios en tu código" -ForegroundColor Green
Write-Host "======================================================" -ForegroundColor Green
