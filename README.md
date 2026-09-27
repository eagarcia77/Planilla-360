# PlanillaPR 360 — ambiente de demostración

Repositorio para publicar **PlanillaPR 360 v1.1** como demostración de preparación contributiva con datos ficticios. **No está certificado para radicación electrónica; no introduzca datos contributivos reales.**

## Publicación del paquete existente

1. Descomprima `PlanillaPR360_v1.1.zip` y cargue **todos los archivos y directorios internos** directamente en la raíz de este repositorio (no cargue el ZIP como único archivo ni cree una carpeta contenedora adicional). En GitHub use **Add file → Upload files**, seleccione el contenido descomprimido y confirme el commit. Nota: la interfaz web de GitHub puede omitir carpetas que empiezan con punto; verifique explícitamente `.github/workflows`.
2. Compruebe que existen en la raíz `app/main.py`, `requirements.txt`, `RELEASE_MANIFEST.json`, `render.yaml`, `static/index.html` y `data/rules/2025.json`.
3. Publique en Render como **Web Service / Python** con comando de construcción `pip install -r requirements.txt`, comando de inicio `uvicorn app.main:app --host 0.0.0.0 --port $PORT`, variable `PLANILLAPR_ENV=staging` y health check `/api/health`.
4. Valide `/api/release-integrity` y `/api/health` antes de usar el sitio; si no coincide el manifiesto, el servicio debe fallar la comprobación de salud.

**Estado:** el repositorio se inicializó para la publicación. El código completo de v1.1 y un despliegue de Render no están confirmados por este README. No active almacenamiento de expedientes reales ni radicación. Consulte `SECURITY.md` y `docs/DEPLOY_RENDER.md` del paquete v1.1 cuando estén disponibles.