Hi my name is William and this is my personal website's codebase.

The site is built as a simple GitHub Pages + Jekyll site:

- `index.html`, `work.html`, and `blog.html` are top-level Jekyll pages using the shared layout in `_layouts/default.html`.
- `home.html` is a legacy redirect to `/`.
- Shared header, footer, and styles live in `_includes/header.html`, `_includes/footer.html`, and `assets/css/base.css`.
- Long-form essays like `distribution.html` and `learnt.html` are also Jekyll pages now, using `_layouts/essay.html`.
- The writing index (`blog.html`) is generated from `_posts/`, and each post can point at a standalone essay page via `essay_url`.
- Repeated site-wide links and contact data live in `_config.yml`.
- Footer navigation links live in `_data/navigation.yml`.
- Ruby/Jekyll dependencies are declared in `Gemfile`.

To add a new essay:

1. Create a page at the repo root (e.g. `my-new-essay.html`) with front matter like:

   ```yaml
   ---
   layout: essay
   title: "My New Essay"
   description: "One-line summary for SEO and previews."
   og_type: article
   date: 2025-01-01
   ---
   ```

2. Add the essay content below that front matter using Markdown or HTML.
3. Add a post file in `_posts/` named like `YYYY-MM-DD-my-new-essay.md` with front matter:

   ```yaml
   ---
   layout: post
   title: "My New Essay"
   description: "One-line summary for SEO and previews."
   essay_url: /my-new-essay.html
   ---
   ```

4. Inside that post file, add a short link paragraph or excerpt. The writing index will pick it up automatically.

GitHub Pages is built through the workflow in `.github/workflows/static.yml`, which runs a Jekyll build before deployment.

To preview the site locally with Jekyll, use:

```bash
bundle install
bundle exec jekyll build
bundle exec jekyll serve
```

and then visit `http://localhost:4000` in your browser.
