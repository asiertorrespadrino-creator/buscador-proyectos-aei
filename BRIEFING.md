# Briefing — Buscador de Proyectos AEI (versión web)

> Documento de continuidad para retomar el trabajo en una nueva sesión con Claude Code.
> Última actualización: **2026-04-08**.

---

## Qué es este proyecto

Migración de la herramienta de escritorio **Buscador de Proyectos AEI**
(`Buscador_Proyectos.exe`, Tkinter + win32com + xlsxwriter, 1.277 líneas)
a una **aplicación web** accesible sin instalación, desplegada en Hugging Face Spaces
y preparada para integrarse en la web institucional de la AEI (Drupal 9.5.11).

Busca proyectos de I+D+i financiados por la AEI desde 2018 por palabras clave,
con filtros opcionales por CIF/NIF y convocatoria, y genera estadísticas,
gráfico, mapa coroplético de CCAA, Excel (3 hojas) y PDF.

---

## Estado actual: APLICACIÓN FUNCIONAL Y DESPLEGADA

| Componente | Estado |
|---|---|
| Backend FastAPI + SQLite | ✅ Completo |
| Frontend HTML/JS vanilla | ✅ Completo |
| Excel (3 hojas) con logo, gráfico y mapa | ✅ Completo |
| PDF con WeasyPrint (Linux/Docker) | ✅ Completo |
| Mapa coroplético CCAA | ✅ Completo |
| Filtro por CIF/NIF | ✅ Completo |
| Filtro por convocatoria | ✅ Completo |
| Marca 2025* (convocatorias pendientes) | ✅ Completo |
| Despliegue en Hugging Face Spaces | ✅ Activo |
| Base de datos (142 MB) en HF LFS | ✅ Configurado |

---

## URLs activas

| Recurso | URL |
|---|---|
| Aplicación en producción | `https://malorasa-buscadoproyectos.hf.space` |
| Repositorio GitHub | `https://github.com/ramirez-santigosa/buscador-proyectos-aei` |
| HF Spaces (repo+deploy) | `https://huggingface.co/spaces/malorasa/BuscadorProyectos` |
| API health check | `https://malorasa-buscadoproyectos.hf.space/health` |
| API docs (Swagger) | `https://malorasa-buscadoproyectos.hf.space/docs` |

---

## Comandos habituales

```bash
# Arrancar el servidor en local (para probar antes de subir)
uvicorn api.main:app --reload

# Publicar cambios
git add <ficheros_modificados>
git commit -m "descripción del cambio"
git push origin main    # GitHub
git push space main     # Hugging Face → rebuild automático (~2 min)
```
