**Deployment instructions:**

1.  Add, edit, remove content.
2.  Run `quarto preview` in Terminal to preview and edit iteratively.
3.  When happy with changes, run `quarto render` in Terminal.
4.  Commit and push changes to GitHub in `main` branch for auto-publishing.
    -   Commit and push to branches to see [deploy previews](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#deploy-previews) without changing your live website.

What [Jadey Ryan](https://jadeyryan.com/) changed to get Netlify deployments working, see links to tutorial for more details:

-   **Repository**
    -   `_quarto.yml`
        -   [Freeze computations](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#freeze-computations): set `execute: freeze: auto`
        -   Remove `output-dir: docs`. Not in the tutorial, I think this was a remnant from your GitHub Pages.
    -   [`_publish.yml` file](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#new-_publish.yml-file)
        -   Change site name and ID
    -   [Configure Quarto Netlify plugin](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#configure-netlify-plugin): Add `netlify.toml` and `package.json`
    -   Remove `.github` folder with jekyll workflow
-   **Netlify site configuration**
    -   [Build settings](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#link-netlify-site-to-github-repository)
        -   Remove `jekyll build` from build command
    -   [Branches and deploy contexts](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#branch-deploys)
        -   Changed production branch from `new-dev-branch` to `main`
    -   [Domain](https://jadeyryan.com/blog/2023-11-19_publish-quarto-website/#site-domain-name)
        -   Custom domain wasn't working and had missing DNS records. Fixed by removing and re-adding yalemgelaw.com domain to populate the necessary Netlify DNS records, per this [support answer](https://answers.netlify.com/t/domain-purchased-from-netlify-stuck-on-awaiting-external-dns/97422/5).
