{{ define "main" -}}
# {{ .Title }}

{{ or .Params.llm.description .Description (.Summary | plainify) }}

{{ if .Params.content_blocks -}}
{{ partial "llm/render-blocks.html" . }}
{{- else -}}
{{ partial "llm/safe-content.html" . }}
{{- end }}
{{- end }}
