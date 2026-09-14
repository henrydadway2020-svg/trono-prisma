# Checklist de revisión — Trono Prisma

Usa esto después de pegar el `index.html` en GitHub y que Cloudflare Pages
termine de desplegar (dale 1-2 minutos). Revisa en **trono-prisma.pages.dev**
con Ctrl+Shift+R (recarga sin caché).

## 1. Que el archivo correcto quedó en GitHub

- [ ] En github.com, abre `index.html` y busca (Ctrl+F) `localClock` → deben
      aparecer 2 resultados.
- [ ] Busca `70% de lo recaudado` → debe aparecer.
- [ ] Busca `TU-USUARIO` → **no debe aparecer nada** (si aparece, es la
      versión vieja otra vez).

## 2. Reloj de hora local

- [ ] Debajo del tag "Torneo de paga · próxima edición abierta", antes del
      trofeo, se ve un texto gris chico: *"Tu hora local ahora: ..."*.
- [ ] El texto cambia si cambias la hora del sistema o esperas ~30 segundos.

## 3. Reparto de premios (debe decir 70/20/10 en TODOS lados, no 90/10)

- [ ] Menú "El torneo" → pestaña TCG Pocket → barra "Reparto del bote".
- [ ] Menú "El torneo" → pestaña Pokémon Champions → misma barra.
- [ ] Menú "Premios" → columna Campeón (70%) y Subcampeón (20%).
- [ ] Sección hero → estadística rápida "70% para el campeón".
- [ ] Sección "Acerca de" → tarjeta "Reparto del premio".
- [ ] Sección "Reglamento" → punto 9 (70% / 20% / 10%).
- [ ] Sección "FAQ" → pregunta "¿Cómo se reparten los premios?".

## 4. Secciones completas

- [ ] Acerca de (7 tarjetas).
- [ ] Cuadro de Honor (TCG Pocket + Champions, aunque estén vacíos).
- [ ] Reglamento oficial (14 puntos, del 1 al 14).
- [ ] Preguntas frecuentes (8 preguntas).
- [ ] CTA final "¿Listo para pelear por el trono?".

## 5. Enlaces de WhatsApp

- [ ] Botón "Unirme al grupo de WhatsApp" (sección de inscripción) abre el
      grupo correcto.
- [ ] Link "chat.whatsapp.com/..." dentro del Reglamento (sección 14,
      Contacto oficial) abre el mismo grupo.
- [ ] Si el grupo cambia algún día, solo se edita `WHATSAPP_URL` dentro de
      `CONFIG` al final del archivo — no hay que tocar los botones.

## 6. Menú móvil (achica la ventana del navegador o pruébalo en el celular)

- [ ] El botón ☰ abre y cierra el menú.
- [ ] Tocar un link como "Acerca de" dentro del menú móvil, cierra el menú
      solo.
- [ ] Tocar fuera del menú (en cualquier otra parte de la página) también
      lo cierra.

## 7. Consola del navegador (F12 → Console)

- [ ] No hay ningún error en **rojo**.
- [ ] Puede aparecer un *warning* amarillo sobre el Cuadro de Honor mientras
      el caché del CDN (jsDelivr) se actualiza — es normal, no es un error
      del código. Si sigue después de 10-15 minutos, revisa que
      `data/campeones-tcg-pocket.json` y `data/campeones-champions.json`
      existan en el repo con contenido `[]`.

## 8. Pendientes ya conocidos (no son bugs, son cosas por hacer)

- [ ] Subir `reglamento-trono-prisma.pdf` a la raíz del repo (el botón de
      descarga ya apunta ahí, pero el archivo no existe todavía).
- [ ] Reemplazar los links `#` de TikTok y YouTube en el CTA final por los
      reales (buscar `TODO` en el archivo).
- [ ] Decidir el dominio final del sitio (¿`trono-prisma.pages.dev` es
      definitivo, o van a usar un dominio propio?) y actualizar `og:url`,
      `og:image` y `canonical` en el `<head>` para que coincidan — hoy
      todavía apuntan a una URL de GitHub Pages que no es la que están
      usando.
