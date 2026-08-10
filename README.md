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

Hostinger publica solo en menos de 10 segundos.

## Diseño

Paleta del cliente: blanco humo `#F5F5F2`, arena `#C89A6A`, negro `#111111`. Todo vive en las variables de `:root` en `css/style.css` — para retematizar, cambiar solo esas.

El arena viene del tono de piel de Julian, así que la foto no termina en un borde recto: se disuelve hacia abajo en ese color mediante una máscara de degradado. Es el único gesto llamativo de la página; el resto se mantiene quieto para que ese se note.

Los botones "Mujeres" y "Hombres" están agrupados bajo un solo título porque son el mismo curso en dos versiones. Separarlos obligaría a repetir un título de 45 caracteres dos veces.

Las etiquetas (`40% fundadores`, `12% · JULIAN2026`) solo aparecen donde hay un dato real que comunicar.

## Enlaces que ya funcionan

| Botón | Destino |
|---|---|
| Asesoría personal VIP | dash.fitmewise.com (mismo enlace que el VIP trimestral) |
| Reprograma tu cerebro — Mujeres | pay.hotmart.com/B106990362O (40% fundadores) |
| Reprograma tu cerebro — Hombres | pay.hotmart.com/B106989870G (40% fundadores) |
| Suplementos Applied Nutrition | fuentesdistribution.com (12%, código JULIAN2026) |
| Contacto para publicidad y campañas | wa.me con mensaje ya escrito |
| Instagram | @julian.fitrainer |
| TikTok | @julian.trainer |
| YouTube | @julianfitrainer |
| Facebook | /julianfitrainer |
| WhatsApp | +57 323 414 4683 |

## Enlaces retirados

**Training Athletic Club** (retirado el 9 de agosto de 2026, a pedido de Julian). Abría un chat a wa.me/573245505232 con el mensaje de inscripción ya escrito y llevaba etiqueta `46% OFF`. Si vuelve, el bloque completo está en el historial: `git log -S "Training Athletic Club"`.

Al quitar el botón también salieron sus rastros: la mención a "Athletic Club" en las dos meta descriptions y el pendiente sobre si el `46% OFF` seguía teniendo sentido. El evento `ClicEnlace` del píxel no hubo que tocarlo — saca el nombre del texto del propio botón, así que desapareció solo.

## Oferta de fundadores

Los dos enlaces de Hotmart apuntan hoy a la oferta de **primera generación, 40% fundadores** (parámetro `?off=` en la URL). Cuando esa tanda cierre hay que reemplazarlos por los enlaces a precio completo y quitar la etiqueta `40% fundadores` del bloque `.grupo__cabecera` en `index.html`.

## Analítica

Dos herramientas, cada una para algo distinto:

**Cloudflare Web Analytics** — visitas, de dónde vienen, qué páginas ven. Sin cookies, así que no requiere banner de consentimiento. Token propio de este dominio (`46a2886e…`), en el `<script type="module">` al final del `<body>`. Panel: dash.cloudflare.com → Analytics & Logs → Web Analytics.

**Píxel de Meta** (`248856401510528`) — el mismo en los dos sitios, a propósito: permite armar audiencias que crucen las marcas. Cada evento incluye el dominio en el parámetro `sitio` para poder separarlas.

Además del `PageView`, se registra un evento **`ClicEnlace`** cada vez que alguien toca un botón, con:

- `enlace` — el texto del botón (ej. "Asesoría personal VIP")
- `sitio` — el dominio

Eso es lo que dice qué producto vende. El nombre sale del texto del propio botón, así que **al añadir enlaces nuevos no hay que tocar el script**.

Para verificar: extensión *Meta Pixel Helper* en Chrome, o Administrador de eventos → Eventos de prueba.

### Pendiente

El píxel usa cookies. En Colombia la Ley 1581 pide aviso de tratamiento de datos: falta un enlace a política de privacidad en el pie.

## Pendiente menor

- [ ] `og-image` propio de 1200×630. Ahora se comparte la foto cuadrada, que WhatsApp recorta.

## Qué se queda fuera del repo

Como Hostinger publica el repo tal cual, **todo lo que se commitea queda accesible por URL**. De ahí que estén fuera:

- Los archivos originales sin optimizar, en `../_originales/`.
- `.vscode/` (en `.gitignore`) — es configuración local del editor. Si se subiera, `julianfitrainer.com/.vscode/settings.json` sería una página pública.
