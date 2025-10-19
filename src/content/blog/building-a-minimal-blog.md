---
title: "Building a Minimal Blog with Astro"
description: "My experience setting up a simple, fast blog using Astro, TypeScript, and Markdown"
date: 2024-10-19
---

# Building a Minimal Blog with Astro

After years of using heavyweight CMSs and blogging platforms, I decided to build something simple. Here's why I chose Astro and how it's working out.

## Why Astro?

I had a few requirements:
- **Write in Markdown** - No database, no admin panel, just files
- **Type-safe** - TypeScript validation for frontmatter
- **Fast** - Static site generation, zero JavaScript by default
- **Simple** - Minimal dependencies and configuration

Astro checked all these boxes.

## The Setup

The entire blog is just a few files:

```typescript
src/
├── content/
│   ├── blog/          // Markdown posts go here
│   └── config.ts      // Content schema
├── layouts/
│   └── BlogPost.astro // Post template
└── pages/
    ├── index.astro    // Home page
    └── blog/[...slug].astro  // Dynamic routes
```

### Content Collections

Astro's content collections give you type-safe frontmatter validation:

```typescript
const blog = defineCollection({
  type: 'content',
  schema: z.object({
    title: z.string(),
    description: z.string(),
    date: z.date(),
    draft: z.boolean().optional(),
  }),
});
```

This means TypeScript will catch errors if I forget a title or use the wrong date format.

## Writing Posts

Creating a new post is as simple as:

1. Create `src/content/blog/my-post.md`
2. Add frontmatter and content
3. Build and deploy

No database migrations, no API calls, no complications.

## Performance

The entire site is pre-rendered at build time. Each page is just HTML and CSS - no JavaScript unless you explicitly need it. This means:

- **Instant page loads** - No framework bootstrap
- **Perfect Lighthouse scores** - Static HTML is fast
- **Works everywhere** - Even on slow connections

## What's Next?

Some features I might add:
- RSS feed for subscribers
- Syntax highlighting for code blocks
- Dark mode toggle
- Related posts section

But for now, this minimal setup does exactly what I need: let me focus on writing.

## Conclusion

Sometimes the best tool is the simplest one. Astro let me build exactly what I needed without the overhead of a full CMS or the complexity of a modern JavaScript framework.

If you're looking for a simple blogging setup, give Astro a try. You might be surprised how far you can get with just Markdown and a few templates.

---

*Want to see the code? Check out the [GitHub repository](https://github.com/MPWhite/thinking).*
