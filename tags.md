---
layout: page
title: Tags
permalink: /tags/
---

<div id="archives">
{% assign sorted_tags = site.tags | sort %}
{% for tag in sorted_tags %}
  <div class="archive-group">
    {% capture tag_name %}{{ tag | first }}{% endcapture %}
    <h2 id="#{{ tag_name | slugize }}">{{ tag_name }}</h2>
    {% for post in site.tags[tag_name] %}
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
