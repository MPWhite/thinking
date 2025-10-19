---
title: "Writing Markdown Posts"
description: "A guide to creating blog posts in markdown"
date: 2024-01-20
---

# Writing Blog Posts

Creating a new blog post is simple:

1. Create a new `.md` file in `src/content/blog/`
2. Add frontmatter with title, description, and date
3. Write your content using Markdown

## Markdown Features

You can use all standard Markdown syntax:

### Lists
- Unordered lists
- Like this one

### Code
```typescript
const greeting: string = "Hello, World!";
console.log(greeting);
```

### Links
[Link to first post](/blog/first-post)

### Emphasis
**Bold text** and *italic text*

## Draft Posts

Add `draft: true` to the frontmatter to hide a post from the blog listing while you work on it.
