# Hineni · Landing de remeras

Página de exhibición con perchero animado, pop-up con frente y espalda giratorio y pedidos por WhatsApp. Es un sitio estático: no necesita servidor ni instalación.

## Archivos

- `index.html`: la página completa (estilos y código adentro).
- `img/`: fotos de cada remera, frente y espalda (`modelo-front.webp` / `modelo-back.webp`) y el logo.

## 1. Contacto de WhatsApp

El número **no está escrito en ningún lado** del código: está guardado codificado en `WA_CODE` (dentro de `index.html`) y el link a WhatsApp se arma recién cuando alguien toca un botón, y se borra enseguida.

Para cambiarlo, abrí la consola del navegador (F12) en la página y pegá esto con el número nuevo (formato `549` + área sin 0 + número sin 15):

```js
((n) => { const k = "hineni-perchero"; let b = ""; for (let i = 0; i < n.length; i++) b += String.fromCharCode(n.charCodeAt(i) ^ k.charCodeAt(i % k.length) ^ (i * 7 % 31)); return btoa(b).split("").reverse().join(""); })("549XXXXXXXXXX")
```

Copiá el resultado y reemplazá el valor de `WA_CODE`.

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
