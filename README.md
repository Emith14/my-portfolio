
# Portfolio - Edson Emith González Algarate

Este repositorio contiene mi portafolio personal construido con Astro. Incluye secciones de héroe, proyectos, habilidades, y un sistema de temas (claro/oscuro) con iconos SVG integrados.

## Qué incluye
- Página estática creada con Astro y componentes en `src/components`.
- Iconos SVG centralizados en `TechIcon.astro` para usar en `Hero`, `Projects` y `Skills`.
- Tema claro/oscuro (persistente en localStorage) configurable desde el header.
- Estilos globales y variables en `src/styles/vars.css` y `src/styles/global.css`.
- Accesibilidad básica: `prefers-reduced-motion`, `focus-visible`, y contraste mejorado.

## Tecnologías
- Astro (componentes .astro)
- CSS con variables (no frameworks CSS añadidos)
- Node + pnpm (gestión de dependencias)

## Estructura principal
- `src/components/`
	- `Header.astro` – navegación + switch de tema
	- `Hero.astro` – sección principal con strip de tecnologías
	- `Projects.astro` – lista de proyectos con badges (usa `TechIcon`)
	- `Skills.astro` – tarjetas de habilidades (lenguajes)
	- `TechIcon.astro` – mapa de nombres a SVGs (fuente de verdad para iconos)
	- `Footer.astro` – pie de página
- `src/layouts/` – layouts (BaseLayout con script de tema)
- `src/styles/vars.css` – tokens / variables de tema
- `src/styles/global.css` – reglas globales y componentes visuales
- `public/` – assets estáticos

## Ejecutar en local
Requisitos: Node (>=16), pnpm

Instalar dependencias:
```bash
pnpm install
```

Modo desarrollo (dev server):
```bash
pnpm run dev
```

Construir para producción:
```bash
pnpm run build
```

Servir build localmente (preview):
```bash
pnpm run preview
```

> Si el servidor de desarrollo no arranca, revisa la salida en la consola para ver errores de sintaxis en componentes `.astro` o SVG mal formados.

## Cómo editar contenido rápido
- Texto del héroe: `src/components/Hero.astro`.
- Proyectos: editar el array dentro de `src/components/Projects.astro`.
- Habilidades / iconos: `src/components/Skills.astro` y `src/components/TechIcon.astro`.

### Añadir/editar un SVG en `TechIcon.astro`
1. Normaliza el nombre (minúsculas, sin espacios) y añade una entrada al mapa, por ejemplo:
```js
icons['mysql'] = `...svg markup...`;
```
2. Usa `<TechIcon name="MySQL" />` o `<TechIcon name={t} />` en la lista de tecnologías.
3. Evita comillas sin escapar dentro del template literal y comprueba que el SVG sea válido (atributos con comillas dobles ok dentro del literal), o usa comillas invertidas con cuidado.

## Temas y variables
- Las variables globales están en `src/styles/vars.css`. Para ajustar colores de modo claro, modifica el bloque `[data-theme="light"]`.
- El switch de tema guarda la preferencia en `localStorage` y aplica `data-theme` en el elemento `<html>`.

## Buenas prácticas / accesibilidad
- Respeta `prefers-reduced-motion` si añades animaciones nuevas.
- Usa `focus-visible` para estilos de teclado.
- Verifica contraste con herramientas (target WCAG AA para texto principal).

## Despliegue
Puedes desplegar el sitio en cualquier host estático (Netlify, Vercel, Cloudflare Pages, DigitalOcean Pages). Pasos generales:
1. Conecta el repo.
2. Comando de build: `pnpm run build`.
3. Directorio de publicación: `dist/`.

## Contribuciones
Este repo es personal, pero si quieres ayudar con mejoras (optimizaciones SVG, accesibilidad, o traducciones), abre un PR y describiré cómo lo reviso.

## Contacto
Edson Emith González — Fullstack Developer — Torreón, México
(pon aquí tu email o redes si quieres que sean públicas)

---

_Nota:_ Este `README.md` está personalizado para el portafolio y reemplaza el README por defecto de Astro. Si necesitas capturas, ejemplos de commits, o instrucciones para CI/CD concretas puedo añadirlos.
