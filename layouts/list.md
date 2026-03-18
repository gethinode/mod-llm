{{ define "main" -}}
# {{ .Title }}
{{- with or .Params.llm.description .Description (.Summary | plainify) }}

{{ . }}
{{- end }}

{{ if .Params.content_blocks -}}
{{ partial "llm/render-blocks.html" . -}}
{{ end -}}
{{ range .Pages -}}
{{ if not .Params.llm.exclude -}}
- [{{ .Title }}]({{ .RelPermalink }}index.md): {{ or .Description (.Summary | plainify | truncate 100) }}
{{ end -}}
{{ end -}}
{{- end }}
