---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---

{% assign latest = site.posts.first %}
<article>
  <h1>{{ latest.title }}</h1>
  <p>{{ latest.date | date: "%-d %B %Y" }}</p>
  {{ latest.content }}
</article>
{% if site.posts.size > 1 %}
<h2>Older posts</h2>
<ul>
  {% for post in site.posts offset:1 %}
  <li>
    <a href="{{ post.url | relative_url }}">{{ post.title }}</a>
    <small>{{ post.date | date: "%-d %B %Y" }}</small>
  </li>
  {% endfor %}
</ul>
{% endif %}
