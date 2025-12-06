Hi my name is William and this is my personal website's codebase.

The site is built as a simple GitHub Pages + Jekyll site:

- `index.html`, `home.html`, `work.html`, and `blog.html` are Jekyll pages using the shared layout in `_layouts/default.html`.
- Shared header, footer, and styles live in `_includes/header.html`, `_includes/footer.html`, and `assets/css/base.css`.
- Long-form essays are individual HTML pages (for now) like `distribution.html`, `making.html`, `extropy.html`, and `thevision.html`.
- The blog index (`blog.html`) is generated from lightweight Jekyll posts in `_posts/` that currently link through to those essays.

To add a new essay:

1. Create an HTML page at the repo root (e.g. `my-new-essay.html`) using the same pattern as the other essay pages, or hook directly into the Jekyll layout if you prefer.
2. Add a new post file in `_posts/` named like `YYYY-MM-DD-my-new-essay.md` with front matter:

   ```yaml
   ---
   layout: post
   title: "My New Essay"
   description: "One-line summary for SEO and previews."
   ---
   ```

3. Inside that post file, either write the full content (Markdown/HTML) or link to the standalone HTML page.

You can preview the site locally with a simple static server (no Jekyll needed for a quick check), for example:

```bash
python -m http.server 4000
```

and then visit `http://localhost:4000` in your browser.
