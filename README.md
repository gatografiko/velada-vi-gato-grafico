# Idea de Sección Luchadores - La Velada VI — 2026

Fan-made website del evento de boxeo/streaming **La Velada del Año VI** de Ibai Llanos.
El diseño y desarrollo solo contempla una idea para la sección de Luchadores de la Velada VI.
Fecha: **Sábado 11 de julio de 2026 · Santiago Bernabéu, Madrid**.

## Stack

| Tecnología | Versión |
| :--------- | :------ |
| [Astro](https://astro.build) | ^6.1.3 |
| [Tailwind CSS](https://tailwindcss.com) | ^4.2.2 (via `@tailwindcss/vite`) |
| [@astrojs/vercel](https://docs.astro.build/en/guides/deploy/vercel/) | ^10.0.4 (SSR adapter) |
| Fuente | Bebas Neue (Google Fonts) |

## Estructura del proyecto

```text
/
├── public/
│   ├── background.avif        # Fondo global
│   ├── fighters/              # Imágenes de luchadores (PNG)
│   └── favicon.svg / .ico
├── src/
│   ├── layouts/
│   │   └── Layout.astro       # Layout base (meta, fuente, estilos globales)
│   ├── components/
│   │   ├── SectionTitle.astro
│   │   ├── header.astro
│   │   ├── footer.astro
│   │   ├── FighterAnimation.astro
│   │   └── BoxerBigImages.astro
│   ├── pages/
│   │   ├── index.astro        # Página principal (arena + bracket hexagonal)
│   │   ├── about.astro
│   │   └── registro.astro
│   ├── types/                 # Interfaces TypeScript (Fighters, Artists, Combat…)
│   │   ├── fighters.ts
│   │   ├── artists.ts
│   │   ├── Combat.ts
│   │   ├── sponsors.ts
│   │   ├── social.ts
│   │   └── bannerType.ts
│   └── styles/
│       └── global.css
├── astro.config.mjs
└── package.json
```

## Características implementadas

- **Bracket hexagonal** — hexágonos con gradiente dorado → rojo al hacer hover + glow animado.
- **Hover interactivo en luchadores** — al pasar el cursor sobre un hexágono se vuelve rojo con glow del mismo color y aparece el luchador seleccionado. A la derecha aparece un luchador aleatorio.
- **Responsive completo** — diseño diferenciado para escritorio (≥ 1024 px) y móvil (< 1024 px) con bracket 2×2 y fighter a pantalla completa.
- **Tipos TypeScript** — interfaces definidas para fighters.
- **Despliegue en Vercel** — adaptador SSR configurado.

## Comandos

Ejecutar desde la raíz del proyecto:

| Comando | Acción |
| :------ | :----- |
| `npm install` | Instala las dependencias |
| `npm run dev` | Servidor de desarrollo en `localhost:4321` |
| `npm run build` | Genera el sitio en `./dist/` |
| `npm run preview` | Vista previa de la build antes de desplegar |
| `npm run astro ...` | Comandos CLI de Astro |

## Despliegue

El proyecto incluye el adaptador `@astrojs/vercel` para SSR. Para desplegar en Vercel basta con conectar el repositorio; la configuración ya está lista en `astro.config.mjs`.

## Roadmap

- [ ] Content Collections para fighters, artistas y combates
- [ ] React islands para componentes interactivos avanzados
- [ ] Sección de artistas musicales
- [ ] Página de registro/newsletter
- [ ] Optimización para 100/100 Lighthouse
