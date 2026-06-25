# Nomos — landing (sitio estático)

Landing de marketing de **Nomos** (SaaS jurídico con IA para despachos en México). Un `index.html`
**self-contained** (0 dependencias): qué hace, para quién, precios y CTA al piloto. Estática → **GitHub → Hostinger**.

> ⚠️ Esto es **solo el SITIO** (landing). La **app Nomos** (Flask + DB, en `C:\Nomos`) es otra cosa y va en
> un **host Python** (VPS o PaaS tipo Railway/Render), NO en el Hostinger estático.

```
index.html · favicon.svg · robots.txt · sitemap.xml
.github/workflows/deploy.yml   ← auto-deploy a Hostinger por FTP (opcional)
```

## 1) Publicar como repo
Copia esta carpeta a un lugar propio (p. ej. `C:\nomos-site`), crea un repo vacío en GitHub y:
```bash
cd C:\nomos-site
git init && git add . && git commit -m "Nomos landing — inicial"
git branch -M main
git remote add origin https://github.com/sodpiloko-ship-it/usanomos.git
git push -u origin main
```

## 2) Hostinger
- **A · Git nativo:** hPanel → Avanzado → GIT → URL del repo, rama `main`, directorio = el `public_html`
  del dominio/subdominio de la landing → Create (+ webhook para auto-deploy).
- **B · Actions FTP:** agrega `FTP_SERVER`/`FTP_USERNAME`/`FTP_PASSWORD` (el workflow ya está listo, se
  salta en verde sin secrets).

## Pendiente (no bloquea el deploy)
- **Dominio:** `nomos.mx` es un placeholder (canonical/sitemap/CTA). **Confirma el dominio real** y lo ajusto.
- **Email de contacto:** el CTA usa `mailto:hola@usanomos.com` — crea ese buzón o cámbialo.
- **CTA a demo/Calendly** en vez de mailto, si prefieres.
