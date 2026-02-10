# Landing QR - Aldeas Infantiles SOS Chile (Planes)

Landing page estática para que una sola impresión de **QR** lleve a una página donde el usuario elige su **aporte mensual** y luego continúa el proceso en **VirtualPOS**.

## Qué incluye
- Página única (`index.html`) con 4 planes (Desayunos, Colaciones y materiales, Salud Mental, Voluntario)
- Estilos (`styles.css`) inspirados en la identidad visual de Aldeas Infantiles SOS Chile
- Logos oficiales descargados desde `aldeasinfantilessos.cl` en `assets/`

## Editar planes (URLs)
Los links están definidos en `index.html` dentro de la sección **Elige tu aporte mensual**. Busca `PLACEHOLDER_PLAN_1`, `PLACEHOLDER_PLAN_2`, etc., y reemplázalos con las URLs reales de VirtualPOS.

## Deploy gratis con GitHub Pages (Project Pages)
1. Sube estos archivos a la rama `main` del repo `aldeasinfantilessos-cl/hazte-socio`:
   - `index.html`
   - `styles.css`
   - `assets/` (con `logo.png`, `footer-logo.png`, `favicon.ico`)
2. En GitHub: **Settings → Pages**
   - **Source**: `Deploy from a branch`
   - **Branch**: `main` + `/ (root)`
3. Espera 1–2 minutos. Tu URL quedará como:
   - `https://aldeasinfantilessos-cl.github.io/hazte-socio/`

## Generar el QR (para la calle)
Este repo incluye un script para generar un PNG con el QR apuntando a:
- `https://aldeasinfantilessos-cl.github.io/hazte-socio/`

Instala dependencias y genera el archivo:

```bash
python3 -m pip install -r requirements.txt
python3 scripts/generate_qr.py
```

Salida por defecto:
- `assets/qr-hazte-socio.png`

Opcional (cambiar URL o nombre de archivo):

```bash
python3 scripts/generate_qr.py --url "https://example.com" --out "assets/qr.png"
```

## Desarrollo local

```bash
python3 -m http.server 8000
```

Abre `http://localhost:8000` en el navegador.

## Notas
- Esta landing **no procesa pagos**. Solo redirige al flujo oficial de suscripción.
- El diseño usa la fuente `Nunito` cargada desde Google Fonts.
- Los colores de marca son `#51AEDB` (azul) y `#A4394B` (rosa) sobre fondo blanco.
