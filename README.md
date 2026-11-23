# alejandraotelo.com

Sitio web de **Alejandra Otelo**, oficiante de ceremonias simbólicas de boda.
Hecho por LA REAL.

```
index.html     ← toda la página (textos, diseño y funciones)
assets/        ← fotos, logotipos y tipografías
scripts/       ← traducción al inglés (solo si se cambian textos)
```

---

## Cómo poner el Píxel de Meta (5 minutos, sin instalar nada)

**1. Copia el código del píxel en Meta**

1. Entra a [Administrador de eventos de Meta](https://business.facebook.com/events_manager2).
2. Elige el píxel (o conjunto de datos) de Alejandra Otelo.
3. *Configurar* → *Instalar el código manualmente* → **Copiar código**.
   El código empieza con `<!-- Meta Pixel Code -->` y termina con
   `<!-- End Meta Pixel Code -->`. Cópialo completo.

**2. Pégalo en la página desde GitHub**

1. En este repositorio, abre el archivo **`index.html`**.
2. Haz clic en el lápiz ✏️ (*Edit this file*), arriba a la derecha.
3. Busca con `Ctrl + F` (Windows) o `Cmd + F` (Mac): **`PEGAR AQUI EL PIXEL DE META`**.
   Vas a ver esto:

   ```html
   <!-- ↓↓↓ PEGAR AQUI EL PIXEL DE META ↓↓↓ -->

   <!-- ↑↑↑ FIN DEL PIXEL DE META ↑↑↑ -->
   ```

4. Pega el código en la línea vacía que está **entre esas dos líneas**.
   No borres ni cambies nada más del archivo.
5. Botón verde **Commit changes…** → escribe algo como "Agrego el píxel de Meta" → **Commit changes**.

**3. Comprueba que quedó**

- En 1 a 3 minutos el cambio está en la página publicada.
- Abre la página con la extensión
  [Meta Pixel Helper](https://chromewebstore.google.com/detail/meta-pixel-helper/fdgfkebogiimcoedlicjlajpkdmockpc)
  de Chrome, o usa *Probar eventos* en el Administrador de eventos.
  Debe aparecer el evento **PageView**.

### Eventos que ya vienen listos

La página ya tiene programados estos eventos. Se activan solos en cuanto el
píxel está pegado; no hay que hacer nada más:

| Cuando la persona… | Evento de Meta |
|---|---|
| Entra a la página | `PageView` (lo trae el código del píxel) |
| Hace clic en cualquier botón de agendar (Calendly) | `Schedule` |
| Hace clic en Instagram, WhatsApp o correo | `Contact` |

`Schedule` es el que conviene usar como conversión en las campañas.

---

## Otros cambios

- **Textos:** se editan igual, en `index.html`. La versión en inglés vive en
  `scripts/traduccion-ingles.py`: si cambias un texto en español, cambia ahí
  también su llave y su traducción y corre `python3 scripts/traduccion-ingles.py`
  (desde un computador con el repositorio descargado).
- **Fotos:** se suben a `assets/` y se cambia el nombre del archivo en `index.html`.
  Mejor en `.jpg` de máximo ~400 KB para que la página siga cargando rápido.
- Si no estás seguro de un cambio, pide revisión a LA REAL antes de guardarlo:
  todo lo que se guarda en la rama `main` se publica de inmediato.

## Publicación

alejandraotelo.com se sirve desde **Cloudflare Pages** (proyecto `alejandra-otelo`).
**Cada cambio que se guarda en la rama `main` de este repositorio se publica solo**
en el dominio en 1–2 minutos (GitHub Action "Publicar en alejandraotelo.com",
pestaña *Actions*). Solo se publican `index.html` y la carpeta `assets/`.

- Si la publicación falla, sale una ✗ roja en la pestaña *Actions* y el sitio
  sigue mostrando la última versión buena.
- Para volver a publicar sin cambiar nada: *Actions* → "Publicar en
  alejandraotelo.com" → *Run workflow*.
- La copia de GitHub Pages (juanfelareal.github.io/alejandra-otelo-web) es solo
  una vista previa.
