# Escuela de Lenguaje Bambú — Sitio Web

Sitio web oficial (One-Page) de la Escuela de Lenguaje Bambú. Educación inicial
especializada en el desarrollo del lenguaje, con 17 años de trayectoria (desde 2009).

🌐 **Sitio en producción:** https://www.escuelabambu.cl

## Tecnologías
- HTML5 + CSS3 personalizado
- Bootstrap 5 y Bootstrap Icons (vía CDN)
- Google Fonts
- Sitio 100% estático y responsivo
- Los años de trayectoria se calculan automáticamente por JS (desde 2009)

## Estructura
```
Sitio_Web_Bambu/
├── index.html          # Página principal
├── CNAME               # Dominio personalizado (www.escuelabambu.cl)
├── css/
│   ├── styles.css      # Estructura y estilos base (colores/fuentes en variables)
│   ├── theme-a.css     # Tema activo: Bambú & Dorado
│   ├── theme-b.css     # Tema alternativo: Cielo & Girasol
│   └── theme-c.css     # Tema alternativo: Lavanda & Salvia
└── assets/             # Imágenes (logo, equipo, pandas, frontis, etc.)
```

## Temas de color
Los colores y fuentes viven en variables CSS. Para cambiar la paleta, edita
en `index.html` la línea del `<link>` del tema:
```html
<link rel="stylesheet" href="css/theme-a.css?v=2" />
```
- `theme-a.css` → Bambú & Dorado (verde bambú claro + dorado) — **activo**
- `theme-b.css` → Cielo & Girasol
- `theme-c.css` → Lavanda & Salvia

Nota: el sufijo `?v=N` de los `<link>` de CSS es "cache-busting". Si haces
cambios de estilo y no se reflejan en el navegador, súbele el número (`?v=3`)
para forzar la recarga.

## Ver el sitio localmente
Opción rápida con un servidor local (recomendado, evita problemas de rutas):
```bash
python3 -m http.server 8000
```
Luego abre http://localhost:8000/ (recarga con Cmd+Shift+R para saltar caché).
Requiere conexión a internet para Bootstrap, íconos y fuentes (CDN).

## Actualizar el sitio (flujo de trabajo)
Cada cambio se publica con git; GitHub Pages reconstruye en 1–2 minutos.
```bash
git add <archivos>
git commit -m "descripción del cambio"
git push
```
- Repositorio: https://github.com/Rahumadat/sitio-web-bambu
- URL de GitHub Pages: https://rahumadat.github.io/sitio-web-bambu/

## Despliegue en GitHub Pages
Ya configurado. Para referencia:
1. Repo en GitHub con el código en la rama `main`.
2. **Settings → Pages** → "Deploy from a branch" → rama `main`, carpeta `/ (root)`.
3. El archivo `CNAME` (en la raíz) define el dominio personalizado.

## Dominio personalizado (www.escuelabambu.cl)
El dominio `.cl` se registró en NIC Chile. Como NIC solo permite indicar
*nameservers* (no registros A/CNAME), se usa **Cloudflare** como DNS intermediario.

Cadena completa: **NIC Chile → Cloudflare (DNS) → GitHub Pages → SSL**

### Configuración aplicada
1. **GitHub Pages** — dominio personalizado `www.escuelabambu.cl` (archivo `CNAME`).
2. **Cloudflare** — cuenta gratuita con el dominio `escuelabambu.cl` y estos
   registros DNS (todos en modo "DNS only" / nube gris):

   | Tipo  | Nombre                | Contenido            |
   |-------|-----------------------|----------------------|
   | CNAME | `www`                 | `rahumadat.github.io`|
   | A     | `@` (escuelabambu.cl) | `185.199.108.153`    |
   | A     | `@` (escuelabambu.cl) | `185.199.109.153`    |
   | A     | `@` (escuelabambu.cl) | `185.199.110.153`    |
   | A     | `@` (escuelabambu.cl) | `185.199.111.153`    |

3. **NIC Chile** — en "Configuración Técnica" → "Servidores DNS", apuntando a
   los nameservers de Cloudflare (sin punto final, sin secundario de NIC):
   - `logan.ns.cloudflare.com`
   - `perla.ns.cloudflare.com`

4. **HTTPS** — GitHub emitió el certificado SSL (cubre `www.escuelabambu.cl` y
   `escuelabambu.cl`) y "Enforce HTTPS" quedó activo. El http redirige a https,
   y `escuelabambu.cl` redirige a `www.escuelabambu.cl`.

> Nota: los nameservers de Cloudflare son propios de la cuenta; si algún día se
> recrea el sitio en Cloudflare, revisar que sigan siendo `logan`/`perla` o
> actualizarlos en NIC.

### Verificar el dominio desde terminal
```bash
dig +short NS escuelabambu.cl @8.8.8.8          # debe mostrar los ns de cloudflare
dig +short www.escuelabambu.cl @8.8.8.8         # debe resolver a rahumadat.github.io / IPs de GitHub
curl -s -o /dev/null -w "%{http_code}\n" https://www.escuelabambu.cl/   # 200
```

## Pendientes de contenido
- Reemplazar imágenes de ejemplo (Picsum) en el banner de Redes.
- Actualizar los enlaces reales de Facebook e Instagram.
- Ajustar el iframe del mapa a la dirección exacta (Calle Chagüal 719, Larapinta, Lampa).

## Contacto
- Dirección: Calle Chagüal 719, Sector Larapinta, Comuna de Lampa, Región Metropolitana
- Correo: escuelabambu@gmail.com
- Teléfono / WhatsApp: +56 44 319 3236
