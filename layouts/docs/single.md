{{ define "main" -}}
# {{ .Title }}

{{ or .Params.llm.description .Description (.Summary | plainify) }}

{{ partial "llm/safe-content.html" . }}
{{- end }}
