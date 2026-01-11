---
layout: page
title: Categories
permalink: /categories/
---

<div id="archives">
{% for category in site.categories %}
  <div class="archive-group">
    {% capture category_name %}{{ category | first }}{% endcapture %}
    <h2 id="#{{ category_name | slugize }}">{{ category_name }}</h2>
    {% for post in site.categories[category_name] %}
      <article class="archive-item">
        <h4><a href="{{ site.baseurl }}{{ post.url }}">{{ post.title }}</a></h4>
        <p class="post-meta">
          <time datetime="{{ post.date | date_to_xmlschema }}">{{ post.date | date: "%B %d, %Y" }}</time>
        </p>
      </article>
    {% endfor %}
  </div>
{% endfor %}
</div>
