# Field Notes

Personal blog at [phlnstr.in](https://phlnstr.in). Built with Jekyll, deployed via GitHub Pages.

---

## How to add a new post

1. Create a new file in `_posts/` named `YYYY-MM-DD-your-post-slug.md`
   - The date in the filename is **required** — Jekyll uses it.
   - The slug becomes part of the URL: `/posts/your-post-slug/`
2. Start the file with this header (called "front matter"):

   ```yaml
   ---
   title: "Your Post Title"
   date: 2026-06-15
   tags: [running, philosophy]
   description: A short description for SEO and link previews.
   ---
   ```

3. Write your post below the closing `---` using Markdown:

   ```markdown
   This is a paragraph. Leave a blank line between paragraphs.

   ## A heading

   **Bold** and *italic* work. So do [links](https://example.com).

   > Block quotes like this.

   - Bullet
   - List
   ```

4. Commit and push. GitHub builds and deploys automatically (takes ~1 min).

That's it. The post **automatically** shows up on the homepage (latest 5) and on the All Posts page (every post, filterable). You don't edit anything else.

---

## How to edit an existing page

| Page    | File                              |
| ------- | --------------------------------- |
| About   | `about.md`                        |
| Now     | `now.md` (update `subtitle:` too) |
| Contact | `contact.html`                    |

---

## How to change the nav, header, or footer

Edit one file, it updates everywhere:

| What                            | File                     |
| ------------------------------- | ------------------------ |
| Header + nav links              | `_includes/header.html`  |
| Footer text                     | `_includes/footer.html`  |
| Meta tags / fonts / favicon     | `_includes/head.html`    |
| Site title, URL, description    | `_config.yml`            |

---

## Available tag styles

The CSS has dedicated colors for these tags. Use them in post front matter:

- `running` (tan/khaki)
- `hiking` (mint green)
- `philosophy` (rust)
- `trail` (forest green)
- `thoughts` (ochre)

Any other tag works but uses default styling. To add a new colored tag, edit the CSS variables and `.tag-*` rules in `assets/css/style.css`.

---

## Preview locally (optional)

Only needed if you want to see changes before pushing. If you're fine waiting 1 minute for GitHub to build, skip this.

You need Ruby installed. Then:

```bash
bundle install     # first time only
bundle exec jekyll serve
```

Open http://localhost:4000

---

## Deploy

Just `git push` to the main branch. GitHub Pages rebuilds the site automatically.

Check the deploy status in your repo under **Actions** tab.

---

## File structure

```
.
├── _config.yml              # Site settings
├── _includes/               # Reusable HTML chunks
│   ├── head.html
│   ├── header.html
│   └── footer.html
├── _layouts/                # Page templates
│   ├── default.html
│   ├── page.html
│   └── post.html
├── _posts/                  # Blog posts (Markdown)
├── assets/
│   ├── css/style.css        # All styling
│   └── favicon/             # Favicon files
├── about.md
├── now.md
├── contact.html
├── index.html               # Homepage
├── all-posts.html           # All posts with filter/sort
├── 404.html
├── CNAME                    # Custom domain (phlnstr.in)
└── Gemfile                  # Ruby dependencies
```
