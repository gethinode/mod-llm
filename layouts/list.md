{{ define "main" -}}
# {{ .Title }}

{{ or .Params.llm.description .Description (.Summary | plainify) }}

{{ range .Pages -}}
{{ if not .Params.llm.exclude -}}
- [{{ .Title }}]({{ .RelPermalink }}index.md): {{ or .Description (.Summary | plainify | truncate 100) }}
{{ end -}}
{{ end -}}
{{- end }}
