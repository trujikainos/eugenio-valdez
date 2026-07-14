# Guía de despliegue — eugeniovaldez.com (Vercel)

Sitio estático (HTML/CSS/JS). No necesita build. Todo lo que se sube es el contenido de esta carpeta `sitio-web/`.

---

## Opción A — Vercel CLI (la más rápida)

En la computadora, dentro de esta carpeta `sitio-web/`:

```bash
# 1. Iniciar sesión en la cuenta de Vercel (abre el navegador)
npx vercel login

# 2. Desplegar a producción
npx vercel --prod
```

En la primera vez preguntará:
- **Set up and deploy?** → `Y`
- **Which scope?** → elegir la cuenta (la del amigo)
- **Link to existing project?** → `N`
- **Project name?** → `eugenio-valdez` (o el que quieran)
- **In which directory is your code?** → `./` (Enter)
- **Modify settings?** → `N`

Al terminar da una URL tipo `https://eugenio-valdez.vercel.app`. Listo.

---

## Opción B — Panel de Vercel + GitHub (recomendada a largo plazo)

1. Subir el contenido de `sitio-web/` a un repositorio de GitHub.
2. En vercel.com → **Add New… → Project → Import** ese repo.
3. Framework preset: **Other** (sitio estático). Root directory: la carpeta con `index.html`.
4. **Deploy**.

Ventaja: cada cambio que se suba a GitHub se publica solo.

---

## Conectar el dominio eugeniovaldez.com

1. En el proyecto de Vercel → **Settings → Domains → Add** → escribir `eugeniovaldez.com` (y `www.eugeniovaldez.com`).
2. Vercel mostrará los registros DNS a configurar. En el panel donde se compró el dominio (registrador), poner:
   - Registro **A** de `@` → `76.76.21.21`
   - Registro **CNAME** de `www` → `cname.vercel-dns.com`
   *(Vercel muestra los valores exactos; usar los que indique.)*
3. Esperar la propagación DNS (minutos a unas horas). El HTTPS se activa solo.

> Nota: el dominio lo compró Eugenio, no el amigo. Se agrega el dominio en el proyecto de Vercel del amigo y se apunta el DNS desde donde se compró el dominio. No hace falta transferir el dominio.

---

## Después de publicar (SEO)

Con el sitio ya en `https://eugeniovaldez.com`:

1. **Google Search Console** (search.google.com/search-console) → agregar propiedad de dominio → verificar → enviar `https://eugeniovaldez.com/sitemap.xml`.
2. **Bing Webmaster Tools** (bing.com/webmasters) → agregar sitio → verificar → enviar el mismo sitemap. (Bing alimenta las respuestas de ChatGPT.)

Archivos SEO ya incluidos en el sitio: `robots.txt`, `sitemap.xml`, `llms.txt`, datos estructurados JSON-LD y sección de Preguntas frecuentes.
