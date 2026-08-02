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

## FALTA: 2 enlaces sin destino

Estos botones están visualmente atenuados y **no son clicables** hasta que se les ponga URL. Buscar `PENDIENTE` en `index.html`:

- [ ] `#PENDIENTE_HOTMART_MUJERES` → checkout de Hotmart, versión mujeres
- [ ] `#PENDIENTE_HOTMART_HOMBRES` → checkout de Hotmart, versión hombres

Al poner la URL real, quitar también el atributo `data-pendiente` del mismo elemento — es lo que lo mantiene desactivado.

## Enlaces que ya funcionan

| Botón | Destino |
|---|---|
| Asesoría personal VIP | dash.fitmewise.com (mismo enlace que el VIP trimestral) |
| Training Athletic Club | dash.fitmewise.com (46% OFF) |
| Suplementos Applied Nutrition | fuentesdistribution.com (12%, código JULIAN2026) |
| Contacto para publicidad y campañas | wa.me con mensaje ya escrito |
| Instagram | @julian.fitrainer |
| TikTok | @julian.trainer |
| YouTube | @julianfitrainer |
| Facebook | /julianfitrainer |
| WhatsApp | +57 323 414 4683 |

## Pendiente menor

- [ ] `og-image` propio de 1200×630. Ahora se comparte la foto cuadrada, que WhatsApp recorta.

Los archivos originales sin optimizar están en `../_originales/`, fuera del repo, para que no se publiquen.
