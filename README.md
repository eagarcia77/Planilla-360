# PlanillaPR 360 — staging demostrativo

**Solo datos ficticios. No está certificado para radicación electrónica ante Hacienda.**

## Importación con un solo ZIP

Este repositorio incluye [un flujo de importación](.github/workflows/importar-paquete.yml). Para cargar el paquete existente:

1. Descargue `PlanillaPR360_v1.1.zip` del chat; **no lo descomprima**.
2. En GitHub, abra [Add file → Upload files](https://github.com/eagarcia77/Planilla-360/upload/main), arrastre el ZIP sin cambiarle el nombre y confirme el commit en `main`.
3. Consulte [Actions](https://github.com/eagarcia77/Planilla-360/actions/workflows/importar-paquete.yml). El flujo valida rutas del ZIP, verifica el manifiesto SHA-256 y ejecuta pruebas automáticas. Si todo pasa, incorpora el código y elimina el ZIP del repositorio. Si falla, NO se publica el código; consulte el log.
4. Compruebe que aparecen `app/main.py`, `static/index.html`, `requirements.txt`, `RELEASE_MANIFEST.json` y `render.yaml` en la raíz.

El flujo no importa automáticamente otros paquetes/versiones y no reemplaza los workflows existentes desde el ZIP. La validación SHA-256 comprueba integridad de los archivos respecto al manifiesto incluido, **no** certifica cumplimiento contributivo ni garantiza que ese manifiesto no haya sido alterado.

## Render — solo después de la importación exitosa

Cree un Web Service desde este repositorio con runtime Python, build `pip install -r requirements.txt`, start `uvicorn app.main:app --host 0.0.0.0 --port $PORT`, `PLANILLAPR_ENV=staging` y health check `/api/health`. Pruebe `/api/release-integrity` y `/api/health` antes de compartir el enlace.

No habilite base de datos contributiva, importación de documentos reales ni transmisión oficial. El proceso de radicación requiere certificación y controles adicionales.