{{ define "main" -}}
# {{ .Title }}
{{- with or .Params.llm.description .Description (.Summary | plainify) }}

{{ . }}
{{- end }}

{{ if .Params.content_blocks -}}
{{ partial "llm/render-blocks.html" . }}
{{- else -}}
{{ partial "llm/safe-content.html" . }}
{{- end }}
{{- end }}
