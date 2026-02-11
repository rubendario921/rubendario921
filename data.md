# =================================================================
# AUTOMATIZACIÓN DE DOCUMENTACIÓN PROFESIONAL .NET CON COPILOT CLI
# =================================================================

$PROYECTO_NOMBRE = "MiProyectoFinal" # Cambia esto por el nombre de tu proyecto
$OUTPUT_FILE = "Wiki_Tecnica_DotNet.md"

# Definición de "Skills" (Contexto que se enviará en cada petición)
$SKILLS_CONTEXT = @"
Contexto: Proyecto .NET 8/9 profesional. 
Reglas: Uso de Clean Architecture, comentarios XML nativos de C#, tono académico en español.
"@

Clear-Host
Write-Host "======================================================" -ForegroundColor Cyan
Write-Host "  🤖 COPILOT CLI: GENERADOR DE DOCUMENTACIÓN .NET" -ForegroundColor Cyan
Write-Host "======================================================" -ForegroundColor Cyan

# 1. Aplicar Comentarios XML al código fuente
Write-Host "`n[1/4] 📝 Documentando código fuente (XML)..." -ForegroundColor Yellow
$promptXml = "$SKILLS_CONTEXT Analiza todos los .cs en Controllers, Services y Models. Genera bloques <summary>, <param> y <returns> para cada método público."
gh copilot suggest $promptXml

# 2. Generar Informe Técnico de Arquitectura
Write-Host "[2/4] 🏛️ Generando análisis de arquitectura..." -ForegroundColor Yellow
$promptArch = "$SKILLS_CONTEXT Lee la estructura de archivos y explica la jerarquía de capas, Inyección de Dependencias y el flujo de datos. Formatea como Markdown."
gh copilot suggest $promptArch | Out-File -FilePath $OUTPUT_FILE -Encoding utf8

# 3. Generar Diagrama de Base de Datos
Write-Host "[3/4] 📊 Generando diagrama de Entidad-Relación..." -ForegroundColor Yellow
$promptDb = "$SKILLS_CONTEXT Basado en las clases de DbContext y Entities, genera un diagrama Mermaid.js tipo erDiagram."
$mermaidResult = gh copilot suggest $promptDb
Add-Content -Path $OUTPUT_FILE -Value "`n## Diagrama de Entidad-Relación`n"
Add-Content -Path $OUTPUT_FILE -Value "````mermaid"
Add-Content -Path $OUTPUT_FILE -Value $mermaidResult
Add-Content -Path $OUTPUT_FILE -Value "````"

# 4. Auditoría de Seguridad y Configuración
Write-Host "[4/4] 🔐 Analizando seguridad y appsettings..." -ForegroundColor Yellow
$promptSec = "$SKILLS_CONTEXT Explica cómo se maneja la autenticación y qué variables requiere el appsettings.json para funcionar."
gh copilot suggest $promptSec >> $OUTPUT_FILE

Write-Host "`n======================================================" -ForegroundColor Green
Write-Host " ✅ PROCESO FINALIZADO CON ÉXITO" -ForegroundColor Green
Write-Host " Archivo generado: $OUTPUT_FILE" -ForegroundColor White
Write-Host "======================================================" -ForegroundColor Green
