---
layout: default
title: About
---
# physics
It a project about physics in plain text

### Contributor
<ul>
  {% for author in site.authors %}
    <li>
      <b><a href="{{site.baseurl}}{{ author.url }}">{{ author.name }}</a></b>
			({{ author.position }})
    </li>
  {% endfor %}
</ul>