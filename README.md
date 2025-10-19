# Simple Blog

A minimal blogging website built with Astro, TypeScript, and Markdown.

## Getting Started

```bash
npm install
npm run dev
```

Visit `http://localhost:4321` to see your blog.

## Writing Posts

1. Create a new `.md` file in `src/content/blog/`
2. Add frontmatter:
   ```markdown
   ---
   title: "Your Post Title"
   description: "A brief description"
   date: 2024-01-20
   draft: false  # optional, set to true to hide
   ---

   Your content here...
   ```

## Building for Production

```bash
npm run build
```

The static site will be in the `dist/` directory.

## Deployment

### Vercel (Recommended)
1. Push your code to GitHub
2. Import project in [Vercel](https://vercel.com)
3. Deploy (auto-detected as Astro project)

### Netlify
1. Push your code to GitHub
2. Import project in [Netlify](https://netlify.com)
3. Settings are in `netlify.toml` (auto-configured)

### GitHub Pages
1. Enable GitHub Pages in repository settings
2. Set source to "GitHub Actions"
3. Push code - workflow in `.github/workflows/deploy.yml` will run automatically

### Other Platforms
Build command: `npm run build`
Output directory: `dist`

## Project Structure

```
src/
├── content/
│   ├── blog/          # Your markdown blog posts
│   └── config.ts      # Content collection schema
├── layouts/
│   └── BlogPost.astro # Blog post layout
└── pages/
    ├── index.astro    # Home page (post listing)
    └── blog/
        └── [...slug].astro  # Dynamic blog post pages
```

## Commands

| Command | Action |
|---------|--------|
| `npm install` | Install dependencies |
| `npm run dev` | Start dev server at `localhost:4321` |
| `npm run build` | Build production site to `./dist/` |
| `npm run preview` | Preview build locally before deploying |
