---
layout: post
title:  "Code Example"
date:   2016-12-08 16:40:46 +1300
categories: coding
sources: 
  - "snippet.cpp"
  - "htmlexample.html"
---

{% for script in site.scripts %}
<hr/>

{{ script.path }}

id: {{ script.id }}

name: {{ script.name }}

scriptname: {{ script.scriptname }}

codetype: {{ script.codetype }}

{{ script.content }}
{% endfor %}

{% for fileid in page.sources %}
{% assign scripts = site.scripts | where: 'id', {{fileid}}%}
{% for script in scripts %}

<hr/>

id: {{ script.id }}

codetype: {{ script.codetype }}

path: {{ script.path }}

[Download: {{ file.id }}]({{ site.baseurl }}/_code_snippets/{{ script.id }})

```{{ script.codetype }}
{{ script.content }}
```

{% endfor %}
{% endfor %}
<hr/>