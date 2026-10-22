<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/fiscusproject/brandbook/master/banner/fiscus-readme-tagline-1280x320-dark.png">
    <img src="https://raw.githubusercontent.com/fiscusproject/brandbook/master/banner/fiscus-readme-tagline-1280x320-light.png" alt="Fiscus — free and open-source fiscalization" width="640">
  </picture>
</p>

# website

Source of [fiscusproject.eu](https://fiscusproject.eu) — the website of **Fiscus**, the
free and open-source, self-hosted fiscalization service for European businesses. Built with
[Hugo](https://gohugo.io) and the [Hextra](https://github.com/imfing/hextra) theme.

## Local development

### In a dev container

`.devcontainer/` defines a [DevPod](https://devpod.sh) that
installs the pinned toolchain automatically.

```sh
devpod up . --ide vscode
hugo server
```

### On your machine

Alternatively, [mise](https://mise.jdx.dev) is required, which pins Hugo and Go:

```sh
mise install
hugo server
```

Either way, open <http://localhost:1313> afterwards.

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

On October 22, 2026, we decided to fully align with the NLnet Foundation's AI policy requirements. From this date forward, AI will not be used to produce, edit, or manage code in this
repository.

[NLNet Foundation AI Policy Version 2.0](https://nlnet.nl/foundation/policies/generativeAI/2.0/)

### AI Policy Disclaimer

The code in this repository prior to October 22 was produced with AI assistance. All decisions were made by the project maintainers, every line of code was human-reviewed, and the maintainers remain accountable for the accuracy and originality of the work.
