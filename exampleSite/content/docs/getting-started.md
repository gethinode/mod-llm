---
title: "Getting Started"
description: "How to install and use mod-llm."
date: 2026-01-10
---

## Installation

Add mod-llm to your Hugo module imports:

```toml
[[module.imports]]
  path = "github.com/gethinode/mod-llm"
```

## Configuration

The module is enabled by default. To disable it, set:

```toml
[params.modules.llm]
  enabled = false
```

## Output Formats

The module provides three output formats:

| Format | File | Description |
| --- | --- | --- |
| llmstxt | /llms.txt | Site index for AI crawlers |
| markdown | index.md | Clean markdown per page |
| llmscomponents | /llms-components.json | Schema for all shortcodes |
