---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: page
title: Blog
seo_title: Vybhav Velamoor's Blog
permalink: /blog/
---

{% for post in site.posts %}
  ### <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
  *{{ post.date | date: "%b %d, %Y" }}*
  
  {{ post.excerpt }}
  ---
{% endfor %}