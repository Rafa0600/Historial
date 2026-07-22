# Subir el dashboard a GitHub como app instalable (PWA)

## Archivos que van al repo
Solo estos 5 (todo lo demás —Python, .bat, worker— NO va a GitHub):

```
index.html
manifest.webmanifest
sw.js
icon-192.png
icon-512.png
```

## Pasos
1. Creá una cuenta en github.com (si no tenés) y un repositorio nuevo, ej. **`ventas-mikra`**.
2. Subí los 5 archivos de arriba (botón **Add file → Upload files** → arrastrás → **Commit**).
3. En el repo: **Settings → Pages**.
4. En *Source* elegí **Deploy from a branch**, branch **main**, carpeta **/ (root)** → **Save**.
5. Esperá ~1 minuto. Arriba te aparece la URL: `https://TU-USUARIO.github.io/ventas-mikra/`

## Instalarla como app (Chrome / Edge)
1. Abrí esa URL en Chrome.
2. En la barra de direcciones aparece un ícono de **instalar** (monitor con flecha) o **⋮ → Instalar Análisis de Ventas**.
3. Clic en **Instalar**. Queda como app con su ícono, ventana propia, y la abrís desde el escritorio.
4. En el celular (Android): menú **⋮ → Agregar a pantalla de inicio**.

## ⚠️ IMPORTANTE — privacidad
El dashboard consulta tus datos desde `ventas-analisis.rafaelassir.workers.dev`, que **hoy responde sin contraseña**. Si el repo de GitHub es **público**, cualquiera que encuentre la URL podría ver tus ventas (unidades, valor, ganancia).

Opciones:
- **Repo privado** (recomendado si te preocupa): GitHub Pages con repo privado requiere plan **GitHub Pro** (pago), o usás otra opción de hosting privado.
- **Cloudflare Pages + Cloudflare Access**: hosting gratis y podés ponerle login (solo tu mail). Es la opción más prolija y gratis para dejarlo privado.
- **Dejarlo público** (si no te molesta): la URL es difícil de adivinar, pero técnicamente los datos quedan accesibles.

Si querés, te ayudo a montarlo en **Cloudflare Pages con Access** para que quede privado y gratis — es muy parecido a lo que ya hiciste con el Worker.

## Actualizar la app más adelante
Si cambiamos el dashboard, subís de nuevo el `index.html` (y si tocamos el `sw.js`, cambiale la versión `ventas-mikra-v1` → `v2` para que Chrome tome los cambios).
