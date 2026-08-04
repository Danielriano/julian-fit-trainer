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

Las etiquetas (`46% OFF`, `12% · JULIAN2026`) solo aparecen donde hay un dato real que comunicar.

## Enlaces que ya funcionan

| Botón | Destino |
|---|---|
| Asesoría personal VIP | dash.fitmewise.com (mismo enlace que el VIP trimestral) |
| Reprograma tu cerebro — Mujeres | pay.hotmart.com/B106990362O (40% fundadores) |
| Reprograma tu cerebro — Hombres | pay.hotmart.com/B106989870G (40% fundadores) |
| Training Athletic Club | wa.me/573245505232 con mensaje ya escrito (46% OFF) |
| Suplementos Applied Nutrition | fuentesdistribution.com (12%, código JULIAN2026) |
| Contacto para publicidad y campañas | wa.me con mensaje ya escrito |
| Instagram | @julian.fitrainer |
| TikTok | @julian.trainer |
| YouTube | @julianfitrainer |
| Facebook | /julianfitrainer |
| WhatsApp | +57 323 414 4683 |


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

Los archivos originales sin optimizar están en `../_originales/`, fuera del repo, para que no se publiquen.
