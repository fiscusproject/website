<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/fiscusproject/brandbook/master/banner/fiscus-readme-tagline-1280x320-dark.png">
  <img src="https://raw.githubusercontent.com/fiscusproject/brandbook/master/banner/fiscus-readme-tagline-1280x320-light.png" alt="Fiscus — free and open-source fiscalization" width="640">
</picture>

# website

Source of [fiscusproject.eu](https://fiscusproject.eu) — the website of **Fiscus**, the
free and open-source, self-hosted fiscalization service for Europe. Built with
[Hugo](https://gohugo.io) and the [Hextra](https://github.com/imfing/hextra) theme.

## Local development

Requires [mise](https://mise.jdx.dev), which pins Hugo and Go:

```sh
mise install
hugo server
```

Then open <http://localhost:1313>. Content lives in `content/`; site configuration in
`hugo.toml`.

## Deployment

Every push to `master` triggers a GitHub Actions workflow that builds the site and
publishes it to AWS (S3 + CloudFront). Infrastructure is managed separately in the
`website-infrastructure` repository.

## License

Code (templates, configuration, build tooling) is licensed under the
[MIT License](LICENSE). Site content (`content/` — pages and documentation) is licensed
under [CC BY-SA 4.0](LICENSE-content).

The Fiscus name and logo are **not** covered by these licenses; their use is governed by
the [trademark policy](https://github.com/fiscusproject/brandbook/blob/master/TRADEMARK.md).

## AI Policy

The code in this repository was produced with AI assistance. All decisions were made by the project maintainers, every line of code was human-reviewed, and the maintainers remain accountable for the accuracy and originality of the work.
