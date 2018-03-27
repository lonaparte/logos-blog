---
layout: default
---
# 文章列表

<ul>
　　{% for post in site.posts %}
　　　　<li>{{ post.date | date_to_string }} <a href="{{ site.baseurl }}{{ post.url }}"><font color="black">{{ post.title }}</font></a></li>
　　{% endfor %}
</ul>