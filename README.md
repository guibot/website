# Experimental Portfolio — Hugo Site

Portfolio minimalista e experimental construído com Hugo. Design focado em sistemas e processos, não em obras individuais.

## Estrutura

```
portfolio-experimental/
├── content/
│   ├── systems/          # Sistemas ongoing e archived
│   ├── journal/          # Entradas do processo log
│   ├── about.md          # Página sobre
│   └── contact.md        # Contacto
├── layouts/              # Templates HTML
├── static/
│   ├── css/              # Estilos
│   └── images/           # Imagens e media
└── hugo.toml             # Configuração
```

## Como usar

### 1. Instalar Hugo
```bash
# macOS
brew install hugo

# Windows (com Chocolatey)
choco install hugo-extended

# Linux
snap install hugo
```

### 2. Correr o site localmente
```bash
cd portfolio-experimental
hugo server -D
```

Abre: `http://localhost:1313`

### 3. Adicionar novo System

Cria ficheiro em `content/systems/nome-do-sistema.md`:

```markdown
+++
title = "Nome do Sistema"
date = 2026-01-27
status = "ongoing"    # ou "archived"
tags = ["sound", "visual", "interaction"]
featured = true
cover = "/images/sistema.jpg"
+++

## Concept
Descrição do conceito...

## Process
Como foi desenvolvido...

## Current Status
Estado atual...
```

### 4. Adicionar nova entrada no Journal

Cria ficheiro em `content/journal/YYYY-MM-DD-titulo.md`:

```markdown
+++
title = "Título do Experimento"
date = 2026-01-27
tags = ["tag1", "tag2"]
media = ["/images/foto.jpg", "/video/teste.mp4"]
+++

Texto breve sobre o experimento ou reflexão.
Foca nos artifacts, não em explicações longas.
```

### 5. Adicionar imagens/vídeos

Coloca ficheiros em `static/images/` ou `static/video/`

Referencia assim no markdown:
- `cover = "/images/minha-imagem.jpg"`
- `media = ["/images/img1.jpg", "/video/clip.mp4"]`

## Deploy

### Netlify (recomendado)
1. Push para GitHub
2. Conecta repositório no Netlify
3. Build command: `hugo`
4. Publish directory: `public`

### Vercel
1. Push para GitHub
2. Import no Vercel
3. Framework: Hugo
4. Done

### Build manual
```bash
hugo
# Ficheiros gerados em /public
```

## Personalização

### Cores
Edita variáveis CSS em `static/css/style.css`:

```css
:root {
    --bg: #0a0a0a;      /* Background */
    --fg: #e8e8e8;      /* Foreground */
    --accent: #00ff88;  /* Accent color */
    --muted: #666;      /* Texto secundário */
}
```

### Navegação
Edita `hugo.toml` na secção `[menu]`

### Conteúdo das páginas fixas
- About: `content/about.md`
- Contact: `content/contact.md`

## Tips

- **Systems**: Foca em sistemas ongoing vs archived, não em projectos individuais
- **Journal**: Mantém entries curtas, deixa os artifacts falarem
- **Images**: Usa aspect ratios consistentes (16:9 para systems, 4:3 para journal)
- **Tags**: Usa tags consistentes para facilitar navegação

## Estrutura recomendada de ficheiros

```
static/
├── images/
│   ├── systems/
│   │   ├── system-01.jpg
│   │   └── system-02.jpg
│   └── journal/
│       ├── 2026-01-15-test.jpg
│       └── 2026-01-20-sketch.jpg
└── video/
    └── journal/
        └── feedback-test.mp4
```

## Performance

- Hugo gera HTML estático = super rápido
- Zero JavaScript no site base
- Otimiza imagens antes de fazer upload (WebP recomendado)
- Vídeos: usa formatos comprimidos (H.264/WebM)

## Ajuda

- Docs Hugo: https://gohugo.io/documentation/
- Markdown guide: https://www.markdownguide.org/
- Deploy: Netlify/Vercel têm docs excelentes

---

**Nota**: Este site é intencionalmente minimalista. Se precisas de features mais complexas (search, filtros avançados, etc), considera adicionar JavaScript ou mudar para Next.js/Astro.
