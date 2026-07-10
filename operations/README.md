# Website Operations

Internal runbook for building, testing, publishing, and transferring the
academic website of David Degras-Valabregue. These notes are for repository
maintainers and are not part of the public website.

## Local preview

The project uses Ruby 3.1.7 and the GitHub Pages dependency set.

```sh
bundle install
bundle exec jekyll serve --config _config.yml,_config.dev.yml
```

Open <http://localhost:4000/>. Before publishing, run the production build:

```sh
bundle exec jekyll build --config _config.yml
```

Do not commit `_site/`; GitHub Pages generates it during deployment.

## Test deployment

The website is currently tested under Yiming Shen's GitHub account. GitHub
Pages publishes the `main` branch from the repository root.

- Repository: <https://github.com/Yiming-S/ddegras.github.io>
- Website: <https://yiming-s.github.io/ddegras.github.io/>

The temporary deployment values are stored near the top of `_config.yml`.
Ownership has not yet been transferred to David Degras-Valabregue.

After each deployment, verify:

- the homepage and every header navigation link;
- the profile portrait and stylesheet;
- several publication pages and external links;
- the Presentations page and any uploaded slide files; and
- the layout on both desktop and mobile screen sizes.

## Ownership transfer checklist

After transferring the repository to the `ddegras` account:

1. Confirm the repository name is `ddegras.github.io`.
2. Update `_config.yml`:

   ```yaml
   url: "https://ddegras.github.io"
   baseurl: ""
   repository: "ddegras/ddegras.github.io"
   ```

3. In GitHub Pages settings, publish from `main` and the repository root.
4. Wait for the Pages deployment to complete, then repeat the deployment
   verification checks above.
5. Keep HTTPS enabled.
