---
layout: default
title: About
---
# fisika
It a project about fisika -- <i>physics in plain text</i> (id)

### Contributor
<ul>
  {% for author in site.authors %}
    <li>
      <b><a href="{{site.baseurl}}{{ author.url }}">{{ author.name }}</a></b>
			({{ author.position }})
    </li>
  {% endfor %}
</ul>