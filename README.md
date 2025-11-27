## Portfolio Site (Minimal Mistakes)

This repository hosts a personal portfolio built with Jekyll and the
[Minimal Mistakes](https://github.com/mmistakes/minimal-mistakes) theme.

### Prerequisites

- Ruby 3.x
- Bundler (`gem install bundler`)

### Setup

```bash
bundle install
```

### Run locally

```bash
bundle exec jekyll serve
```

Site will be available at `http://127.0.0.1:4000`.

### Customization checklist

1. Update `_config.yml` with your real `title`, `email`, `url`, and social links.
2. Replace placeholder images inside `assets/images/`.
3. Edit navigation links in `_data/navigation.yml`.
4. Add or remove pages in `_pages/` and posts in `_posts/`.
5. When ready to deploy, run `bundle exec jekyll build` to generate `_site/`.
