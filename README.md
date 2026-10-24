# esHoy — sitio de descarga

Página pública con la información de esHoy y el enlace para descargar el APK.
**Este repositorio no contiene el código fuente de la app** (vive en un repositorio privado).

## Qué hay aquí
- `index.html` — página principal.
- `privacidad.html` — política de privacidad.
- `terminos.html` — términos y condiciones (mismo texto que Ajustes → Acerca de en la app, `termsContent.js`).
- `styles.css`, `assets/` — estilos y capturas.
- `_release/` — copia local del APK (ignorada por git; se sube como *Release*, no como archivo del repo).

## Publicar (una sola vez)
```bash
git init -b main
git add .
git commit -m "Sitio de esHoy"
git remote add origin https://github.com/BUMAPP-SV/eshoy-app.git
git push -u origin main
```
Luego, en GitHub: **Settings → Pages → Branch: `main` / carpeta `/ (root)`**.
La página queda en `https://bumapp-sv.github.io/eshoy-app/`.

## Publicar una versión del APK
1. En GitHub: **Releases → Draft a new release**, etiqueta `v1.1.7`.
2. Adjunta el archivo con el nombre exacto **`esHoy.apk`**.
3. Publica. El botón de la página apunta siempre al último release:
   `https://github.com/BUMAPP-SV/eshoy-app/releases/latest/download/esHoy.apk`

Con la CLI de GitHub (`gh`):
```bash
gh release create v1.1.7 _release/esHoy.apk --title "esHoy 1.1.7" --notes "Cambios de esta versión"
```

## Antes de repartirlo de verdad
- Firmar el APK con una llave **release** propia (hoy está firmado con la de depuración). Guardar la llave: si se pierde, nadie podrá actualizar.
- Actualizar el número de versión y el tamaño en `index.html` (texto "Versión … · … MB").
