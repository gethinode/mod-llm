# Hinode Module - LLM

<!-- Tagline -->
<p align="center">
    <b>A Hugo module to expose your Hinode site in machine-readable form for AI agents</b>
    <br />
</p>

<!-- Badges -->
<p align="center">
    <a href="https://gohugo.io" alt="Hugo website">
        <img src="https://img.shields.io/badge/generator-hugo-brightgreen">
    </a>
    <a href="https://gethinode.com" alt="Hinode theme">
        <img src="https://img.shields.io/badge/theme-hinode-blue">
    </a>
    <a href="https://github.com/gethinode/mod-llm/commits/main" alt="Last commit">
        <img src="https://img.shields.io/github/last-commit/gethinode/mod-llm.svg">
    </a>
    <a href="https://github.com/gethinode/mod-llm/issues" alt="Issues">
        <img src="https://img.shields.io/github/issues/gethinode/mod-llm.svg">
    </a>
    <a href="https://github.com/gethinode/mod-llm/pulls" alt="Pulls">
        <img src="https://img.shields.io/github/issues-pr-raw/gethinode/mod-llm.svg">
    </a>
    <a href="https://github.com/gethinode/mod-llm/blob/main/LICENSE" alt="License">
        <img src="https://img.shields.io/github/license/gethinode/mod-llm">
    </a>
</p>

## About

![Logo](https://raw.githubusercontent.com/gethinode/hinode/main/static/img/logo.png)

Hinode is a clean blog theme for [Hugo][hugo], an open-source static site generator. Hinode is available as a [template][repository_template], and a [main theme][repository]. This repository implements the emerging [llms.txt convention](https://llmstxt.org/) to expose your Hinode in machine-readable form for AI agents. In addition, it creates a clean Markdown equivalent for each page. Finally, `mod-llm` optionally generates `/llms-components.json`, a machine-readable JSON schema of every Hinode shortcode and content block. Visit the Hinode documentation site for [installation instructions][hinode_docs].

## Configuration

`mod-llm` is a standard Hugo module. Add it as an import to your site's module configuration in `hugo.toml`.

```toml
[[module.imports]]
  path = "github.com/gethinode/mod-llm"
```

Hugo generates output for each page based on the configured output formats. `mod-llm` requires two custom formats and supports one optional format. Add the following definitions to your site configuration.

```toml
[outputFormats]
  [outputFormats.llmstxt]
    mediaType = "text/plain"
    baseName = "llms"
    isPlainText = true
    notAlternative = true
    rel = "alternate"
    root = true

  [outputFormats.markdown]
    mediaType = "text/markdown"
    baseName = "index"
    isPlainText = true
    isHTML = false
    noUgly = false
    rel = "alternate"

  # Optional: add llmscomponents for Hinode documentation sites
  [outputFormats.llmscomponents]
    mediaType = "application/json"
    baseName = "llms-components"
    isPlainText = true
    notAlternative = true
    root = true
```

Activate the formats in the `[outputs]` section of your `hugo.toml`. Include `llmscomponents` only if your site is a Hinode documentation site.

```toml
[outputs]
  home = ["HTML", "llmstxt", "markdown"]   # add "llmscomponents" for documentation sites
  page = ["HTML", "markdown"]
  section = ["HTML", "markdown"]
```

> [!NOTE]
> If your site already defines `[outputs]`, extend the existing lists rather than replacing them. The `HTML` output must remain to keep the regular site building correctly. The `section` key ensures section index pages (`_index.md`) get a Markdown equivalent and are linked from `llms.txt`.

## Contributing

This module uses [semantic-release][semantic-release] to automate the release of new versions. The package uses `husky` and `commitlint` to ensure commit messages adhere to the [Conventional Commits][conventionalcommits] specification.

<!-- MARKDOWN LINKS -->
[hugo]: https://gohugo.io
[hinode_docs]: https://gethinode.com
[repository]: https://github.com/gethinode/hinode.git
[repository_template]: https://github.com/gethinode/template.git
[conventionalcommits]: https://www.conventionalcommits.org
[husky]: https://typicode.github.io/husky/
[semantic-release]: https://semantic-release.gitbook.io/
