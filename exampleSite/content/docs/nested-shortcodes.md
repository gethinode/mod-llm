---
title: Nested Shortcodes
description: Fixture for escaped shortcodes in the markdown output.
---

An escaped shortcode inside an enclosing shortcode reaches it in its escaped form, so a
nav-item renders the command it holds.

{{< nav tab-type="tabs" >}}
{{< nav-item title="macOS" show="true" >}}
In a terminal:

{{</* command shell="bash" */>}}
brew install example
{{</* /command */>}}
{{< /nav-item >}}
{{< /nav >}}

An example keeps the escaped shortcode as literal text.

{{< example lang="hugo" >}}
{{</* abbr HTML */>}}
{{< /example >}}

An escaped shortcode outside any shortcode is literal text: `{{</* abbr HTML */>}}`.
