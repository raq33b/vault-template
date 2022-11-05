---
title: {{ title | replace("[^A-Za-z0-9]", "") }}
tags:
  - hypothesis
  - sources
---
{% if is_new_article %}
{% if author %}Author:: [{{author}}]({{authorUrl}}){% endif %}
Title:: {{title}}
{% if url %}Link:: {{url}}{% endif %}
{% endif %}
---

{%- if is_new_article %}
{% for highlight in page_notes -%}
{{highlight.annotation}}
{%- if highlight.tags | length %}
Tags: {% for tag in highlight.tags -%} #{{tag | replace(" ", "-")+" "}}{%- endfor %}
{% endif %}
{% endfor %}
{%- endif -%}

{%- if is_new_article -%}
## Highlights
{% for highlight in highlights -%}
- {{highlight.text}} — [Updated on {{highlight.updated}}]({{highlight.incontext}})
{%- if 'Private' != highlight.group %} — Group: #{{highlight.group | replace(" ", "-")}}{% endif %}
{% if highlight.tags | length %}    - Tags: {% for tag in highlight.tags %} #{{tag | replace(" ", "-")+" "}}{% endfor %}
{% endif -%}
{% if highlight.annotation %}    - Annotation: {{highlight.annotation}}{% endif %}
{% endfor %}
{% endif %}
