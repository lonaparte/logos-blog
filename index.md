---
layout: default
---
# Articles Lists

<ul>
　　{% for post in site.posts %}
　　　　<li>{{ post.date | date_to_string }} <a href="{{ site.baseurl }}{{ post.url }}"><h3>{{ post.title }}</h3></a></li>
　　{% endfor %}
</ul>