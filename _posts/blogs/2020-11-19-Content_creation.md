---
layout: posts
categories: quick_notes
# toc: true
# toc_label: "My Table of Contents"
# toc_icon: "cog"
---

an example of "all posts"

<ul>
  {% for post in site.posts %}
    <li>
      <a href="{{ post.url }}">{{ post.title }}</a>
    </li>
  {% endfor %}
</ul>

## trying auto-toc also