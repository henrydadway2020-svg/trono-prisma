# Trono Prisma

Landing page del torneo de paga de TCG Pocket y Pokémon Champions. Sitio estático (HTML/CSS/JS, sin build ni dependencias) pensado para GitHub Pages.

## Estructura

```
index.html                       → toda la página (un solo archivo)
assets/                          → favicons, trofeo, banners/stickers de campeones
data/campeones-tcg-pocket.json   → historial del Cuadro de Honor — TCG Pocket
data/campeones-champions.json    → historial del Cuadro de Honor — Pokémon Champions
```

## Cómo agregar un campeón al Cuadro de Honor

El Cuadro de Honor se genera automáticamente desde los archivos en `data/`. Para
agregar una edición, añade un objeto al final del arreglo del JSON correspondiente:

```json
{
  "torneo": "Trono Prisma #3",
  "fecha": "Septiembre 2026",
  "campeon": {
    "nombre": "NombreDelJugador",
    "banner": "assets/banners/edicion3-campeon.png",
    "sticker": "assets/stickers/edicion3-campeon.png"
  },
  "subcampeon": {
    "nombre": "OtroJugador",
    "sticker": "assets/stickers/edicion3-subcampeon.png"
  },
  "final_url": "https://www.tiktok.com/@..."
}
```

Notas:
- Todos los campos son opcionales excepto que el objeto exista; si falta `banner`,
  `sticker` o `final_url`, la tarjeta simplemente no muestra esa parte.
- Las rutas de imágenes (`banner`, `sticker`) son relativas a la raíz del repo.
- El sitio lee estos JSON y las imágenes referenciadas a través de jsDelivr
  (`cdn.jsdelivr.net/gh/...`), **no** directamente desde GitHub. Esto significa que
  después de hacer `push`, los cambios pueden tardar unos minutos (a veces más) en
  reflejarse en el sitio publicado, por caché del CDN. Si algo "no aparece" recién
  subido, espera un poco antes de asumir que hay un error.

## Configuración

Todo lo editable sin tocar el HTML/CSS vive en el bloque `CONFIG` al final de
`index.html`:

- `GITHUB_USER` / `GITHUB_REPO` / `BRANCH`: de dónde se leen los JSON e imágenes vía jsDelivr.
- `DATA_PATHS`: rutas a los JSON del Cuadro de Honor.
- `WHATSAPP_URL`: único lugar donde vive el link del grupo de WhatsApp. Si el grupo
  cambia, se actualiza solo aquí — todos los botones del sitio lo toman de ahí.

## Pendientes conocidos

- [ ] Subir `reglamento-trono-prisma.pdf` a la raíz del repo (el botón de descarga ya
      apunta ahí).
- [ ] Reemplazar los links de TikTok y YouTube en el CTA final (buscar `TODO` en
      `index.html`).
- [ ] Confirmar la URL final publicada en `og:url`, `og:image`, `canonical` y
      `sitemap.xml` si el sitio se sirve desde un dominio distinto al de GitHub Pages.
