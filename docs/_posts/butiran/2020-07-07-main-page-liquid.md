---
layout: post
author: viridi
title: Liquid code for main page
mathjax: false
ptext: false
x3dom: false
threejs: false
category: butiran
tags: [liquid]
---
Archive of today main page of the blog

## index.md
```md
{% raw %}---
layout: default
title: butiran
---

# butiran-blog
<p style="font-family: monospace">
{% assign pad0 = '00' %}
{% assign n = pad0 | size %}
{% assign m = 0 | minus: n %}
{% assign i = site.posts.size %}
{% for post in site.posts %}
	{% assign d = post.date | split: ' ' %}
	{% assign i = i | minus: 1 | prepend: pad0 %}
	{% assign j = i | slice: m, n %}
	{% assign k = d.first | replace: "-", "" %}
	[{{ j }}]
	<a href="{{ site.baseurl }}{{ post.url }}">
		{{ post.date | date: "%d-%b" }} {{ post.title }}</a>,
{% endfor %}
</p>{% endraw %}
```

Meaning of each variable are 
- `pad0` is for zero padding,
- `n` is number of digit,
- `m` is simply `-n`,
- `d` is [`dd`, `mm`, `yy`],
- `i` is decreasing by `1` from number of the posts, and
- `k` is date in `day-Month` format.
