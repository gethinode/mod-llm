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

A shortcode inside a list item is indented to the item as a whole.

1. **Install**

    {{< command shell="bash" >}}
    brew install example
    example --version
    {{< /command >}}

2. **Verify**

    Run the check.

A nav-item that indents its tag but not its body keeps the body as written.

{{< nav tab-type="tabs" >}}
  {{< nav-item title="Steps" show="true" >}}

1. **Install**

    {{</* command shell="bash" */>}}
    brew install example
    example --version
    {{</* /command */>}}
  {{< /nav-item >}}
{{< /nav >}}
