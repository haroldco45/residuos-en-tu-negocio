# Residuos en tu negocio

**Biblioteca Legal Colombiana** · Guía legal sobre manejo de residuos para establecimientos comerciales en Colombia.

PWA de un solo archivo, sin backend, sin login y sin recolección de datos. Pensada para repartir por WhatsApp entre comerciantes de barrio.

Normas verificadas al **7 de septiembre de 2026**.

---

## Qué incluye

- **Checklist por tipo de negocio** — tienda o minimercado, restaurante o comidas, taller o lavadero, droguería, y oficina o local. La lista se ajusta al negocio escogido y el avance queda guardado en el navegador del usuario.
- **Código de colores** de la Resolución 2184 de 2019 (verde, blanco, negro) usado como identidad visual del volumen.
- **Buscador de normas** — 28 fichas agrupadas en General, Separación, Plásticos, Peligrosos, Posconsumo, Agua y salud, y Sanciones. Cada ficha dice qué exige y qué autoridad vigila.
- **Línea de tiempo de la Ley 2232 de 2022** sobre plásticos de un solo uso.
- **Sección de residuos peligrosos** actualizada con el Decreto 766 de 2026.
- **Envío del resultado por WhatsApp** — genera un texto con los puntos pendientes del negocio.
- Aviso de Habeas Data (Ley 1581 de 2012) y aviso de alcance educativo.

## Archivos

| Archivo | Para qué |
|---|---|
| `index.html` | Toda la aplicación. Funciona sola si hace falta. |
| `manifest.json` | Instalación como app en el celular. |
| `sw.js` | Cache offline. La guía abre sin datos después de la primera visita. |
| `README.md` | Este documento. |

## Antes de publicar

1. **Imagen Open Graph.** Sube una imagen de 1200×630 px a `https://vibraspositivashm.com/og/residuos-negocio.png` o cambia la ruta en las etiquetas `og:image` de `index.html`. Sin esa imagen, el enlace en WhatsApp sale sin miniatura.
2. **URL canónica.** Ajusta `og:url` a la dirección real de publicación.
3. **Íconos PNG.** El manifest ya trae un ícono SVG embebido que funciona de inmediato. Para instalación completa en Android, agrega `icon-192.png`, `icon-512.png` e `icon-maskable-512.png` en la misma carpeta.
4. **Número de volumen.** Si quieres numerarlo dentro de la serie, edita la línea `<span class="serie">Biblioteca Legal Colombiana</span>` en el hero.

## Publicación en GitHub Pages

```bash
git init
git add index.html manifest.json sw.js README.md
git commit -m "Volumen: residuos en establecimientos comerciales"
git branch -M main
git remote add origin https://github.com/USUARIO/residuos-negocio.git
git push -u origin main
```

Luego en el repositorio: **Settings → Pages → Branch: main / (root)**.

El service worker requiere HTTPS. GitHub Pages, Netlify y cPanel con SSL lo cumplen. Abierto como archivo local (`file://`) el cache offline no se activa, pero el resto funciona igual.

## Nota técnica

Sin llamadas a API externas, salvo la hoja de fuentes de Google Fonts. Esto es intencional: GitHub Pages es hosting estático y bloquea llamadas a servicios que requieran clave. No hay módulo de chat con IA.

Actualizar el cache tras un cambio: subir la versión en `sw.js` (`residuos-legal-v1` → `v2`).

## Aviso

Documento de divulgación con fines educativos. No sustituye asesoría jurídica ni el concepto de la autoridad ambiental competente. En el Bajo Cauca antioqueño la autoridad ambiental es Corantioquia, territorial Panzenú; los horarios y frecuencias de recolección los fija el PGIRS de cada municipio.

---

**Desarrollada por Vibras Positivas HM — Derechos de Autor Reservados**
