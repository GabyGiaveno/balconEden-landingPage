# Balcón Edén — landing

Landing de una sola página para promocionar el alquiler **Balcón Edén Apart**
(La Falda, Sierras de Córdoba). Es una vidriera publicitaria: no gestiona
reservas ni pagos, todo botón de acción lleva a la publicación real de
Airbnb.

Construido con [Astro](https://astro.build) + CSS propio (sin frameworks de
UI). Las imágenes se optimizan automáticamente en el build con
`astro:assets` (se generan versiones responsive en WebP).

## Desarrollo local

```bash
npm install
npm run dev
```

Abre `http://localhost:4321`.

## Build de producción

```bash
npm run build
npm run preview
```

## Deploy en Vercel

1. Subí este proyecto a un repo de GitHub/GitLab/Bitbucket (o corré
   `vercel` desde la carpeta con la [Vercel CLI](https://vercel.com/cli)).
2. En [vercel.com](https://vercel.com), **Add New → Project**, importá el
   repo.
3. Vercel detecta Astro automáticamente (Build Command: `astro build`,
   Output Directory: `dist`). No hace falta configurar nada más.
4. Deploy.

## Estructura

- `src/pages/index.astro` — arma la página con todos los componentes.
- `src/components/` — Header, Hero, Story, Gallery, Amenities,
  Testimonials, HostLocation, FinalCta, Footer.
- `src/assets/gallery/` — fotos originales (se optimizan en el build).
- `src/styles/global.css` — tokens de diseño (colores, tipografías,
  el motivo de "baranda" que se repite entre secciones).

## Contenido

El texto y las reseñas de la sección "Opiniones" están tomados de la
publicación real en Airbnb:
https://www.airbnb.com.sv/rooms/1466095984266019111

Si cambia el precio, la disponibilidad o algún dato del alojamiento, no
hace falta tocar nada acá: la página no muestra precios ni calendario,
siempre deriva a Airbnb como fuente de verdad. Sí conviene actualizar a
mano las reseñas de `src/components/Testimonials.astro` de tanto en tanto
para reflejar las más recientes.
