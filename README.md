# mohamedmhafify.github.io

Personal portfolio — Mohamed Mostafa Hassan Afify, Data Analyst & AI Engineer.

Static single-page site. No build step, no dependencies.

```
├── index.html          the whole site (HTML + CSS + JS inline)
└── assets/
    ├── img/            project screenshots
    └── cv/             downloadable CVs
```

## Publishing

1. Create a **public** repo named exactly `mohamedmhafify.github.io`
2. Push these files to the `main` branch
3. Settings → Pages → Source: `Deploy from a branch` → `main` / `root`
4. Live in a minute or two at **https://mohamedmhafify.github.io**

## Updating

- **Add a project** — copy a `<tr>` block inside the relevant `.idx` table in `index.html`
- **Swap the featured case** — edit the `<article class="case">` block
- **Replace a CV** — drop the new PDF into `assets/cv/` using the same filename
