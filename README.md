# Library

> A curated library of UI/UX, product design and web design resources.

Personal resource library mantenida por Jose. Inspirada en [lib.danielsalomonm.com](https://lib.danielsalomonm.com).

🔗 **Live:** _pendiente de deploy_

---

## Stack

- HTML + CSS + JS vanilla (single file)
- No build step, no dependencies
- Fonts vía Google Fonts CDN (Instrument Serif, Geist, JetBrains Mono)
- Hosting: GitHub Pages

---

## Estructura

```
.
├── index.html      ← Todo el sitio (markup, estilos, lógica y data)
├── README.md
└── .gitignore
```

Toda la data de recursos vive en el array `DATA` dentro del `<script>` de `index.html`. Cada categoría tiene esta forma:

```js
{
  id: "icons",                    // slug interno, no se muestra
  title: "Iconos",                // título visible en sidebar y header
  desc: "Descripción corta...",   // subtítulo de la sección
  resources: [
    {
      name: "Lucide",                            // nombre del recurso
      url: "https://lucide.dev",                 // link externo
      desc: "Set de iconos open-source...",      // 1 línea
      tag: "open-source"                         // free | paid | freemium | open-source
    }
  ]
}
```

---

## Cómo agregar recursos

1. Abrir `index.html`
2. Localizar el array `DATA`
3. Encontrar la categoría por `id` o `title`
4. Añadir el objeto al array `resources` de esa categoría
5. Guardar y refrescar el browser

El sidebar, los contadores y la búsqueda se actualizan solos.

---

## Development workflow

Cambios al diseño/contenido se iteran en chat con Claude y se mergean vía PR.

```bash
# 1. Nueva branch para el cambio
git checkout -b feat/nombre-del-cambio

# 2. Reemplazar index.html con la nueva versión

# 3. Commit
git add index.html
git commit -m "feat: descripción del cambio"

# 4. Push
git push -u origin feat/nombre-del-cambio

# 5. Abrir PR en GitHub, revisar diff, aprobar y mergear
```

### Convención de nombres de branch

- `feat/` → nuevas features o secciones
- `content/` → solo agregar/editar recursos
- `fix/` → arreglos de bugs o tipos
- `design/` → cambios de diseño visual

### Convención de commits

Formato corto, presente, en inglés o español según prefieras:

```
feat: add 8 resources to Inspiración category
design: switch accent color to deep indigo
fix: search no funciona en categorías vacías
```

---

## Deploy

GitHub Pages, deploy automático desde la branch `main`.

```
Settings → Pages → Source: main / root → Save
```

URL pública: `https://<username>.github.io/<repo-name>/`

---

## Roadmap

- [ ] Primer batch de recursos en todas las categorías base
- [ ] Custom domain
- [ ] Filtro por tag (free / paid / freemium / open-source)
- [ ] Modo "vista lista compacta" vs. "vista expandida"
- [ ] Marcar recursos como favoritos (localStorage)
- [ ] Importar/exportar JSON

---

## Licencia

Personal use.
