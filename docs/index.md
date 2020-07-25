---
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
</p>