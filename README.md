# Julian Fit Trainer — linktree

Sitio estático de una sola página. Dominio: **julianfitrainer.com**

Sin build, sin dependencias. Lo que está en este repo es exactamente lo que se publica.

## Previsualizar en local

```bash
python3 -m http.server 8000
```

Abrir <http://localhost:8000>

## Publicar

```bash
git add -A && git commit -m "descripción del cambio" && git push
```

Hostinger recibe el webhook y publica solo. Verificar en <https://julianfitrainer.com>

## Estructura

| Archivo | Qué es |
|---|---|
| `index.html` | La página completa |
| `css/style.css` | Estilos. Las variables de `:root` controlan todo el tema |
| `assets/` | Imágenes e íconos |
| `robots.txt` | Permite indexación |

Para cambiar colores o tipografía, tocar solo las variables al inicio de `css/style.css`.

## Pendientes de fase 2

Los `href` con `#PENDIENTE_*` en `index.html` son placeholders. Reemplazar por:

- [ ] `#PENDIENTE_WHATSAPP` → `https://wa.me/<código país + número, sin espacios ni +>`
- [ ] `#PENDIENTE_INSTAGRAM` → perfil de Instagram
- [ ] `#PENDIENTE_TIKTOK` → perfil de TikTok
- [ ] `#PENDIENTE_CHECKOUT` → URL de venta de planes
- [ ] `#PENDIENTE_CALENDLY` → URL de agenda (Calendly / Cal.com)

Assets a reemplazar:

- [ ] `assets/avatar.svg` → foto real de Julian (cuadrada, mínimo 400×400, WebP o JPG optimizado)
- [ ] `assets/favicon.svg` → favicon derivado del logo
- [ ] `assets/og-image.jpg` → imagen 1200×630 para cuando se comparta el link (aún no existe; sin ella el link se ve sin miniatura en WhatsApp)

Diseño final: paleta, tipografía y layout definitivos, a partir de los referentes visuales.
