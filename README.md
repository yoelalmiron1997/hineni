# Hineni · Landing de remeras

Página de exhibición con perchero animado, pop-up con frente y espalda giratorio y pedidos por WhatsApp. Es un sitio estático: no necesita servidor ni instalación.

## Archivos

- `index.html`: la página completa (estilos y código adentro).
- `img/`: fotos de cada remera, frente y espalda (`modelo-front.webp` / `modelo-back.webp`) y el logo.

## 1. Poné tu número de WhatsApp

Abrí `index.html`, buscá `WHATSAPP_NUMBER` y escribí tu número en formato internacional, sin `+`, espacios ni guiones:

```js
const WHATSAPP_NUMBER = "5491123456789"; // 54 + 9 + código de área sin 0 + número sin 15
```

Si lo dejás vacío, WhatsApp le pide al cliente que elija a quién mandarle el mensaje.

## 2. Subilo a GitHub Pages

1. Creá un repositorio nuevo en GitHub (por ejemplo `hineni`).
2. Subí `index.html` y la carpeta `img` completa (botón **Add file → Upload files**, arrastrás todo y **Commit**).
3. En el repo: **Settings → Pages → Build and deployment → Source: Deploy from a branch**, rama `main`, carpeta `/ (root)` → **Save**.
4. En uno o dos minutos la página queda en `https://TU-USUARIO.github.io/hineni/`.

## Cambiar precios o modelos

En `index.html`, dentro del bloque **CONFIGURACIÓN**:

- `PRICES`: precio anterior, precio actual y texto del descuento de básicas y oversize.
- `PRODUCTS`: un renglón por remera (`id`, nombre, línea `basica`/`oversize`, color, cita y versículo).

Para agregar una remera nueva: subí `img/nuevo-front.webp` e `img/nuevo-back.webp` (PNG con fondo transparente también sirve, cambiando la extensión en el código) y agregá un renglón en `PRODUCTS` con `id: "nuevo"`.

## Links directos a un modelo

Cada remera tiene su link, ideal para Instagram o estados: `https://TU-USUARIO.github.io/hineni/#emaus` abre la página con ese modelo en el pop-up.
