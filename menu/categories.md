---
layout: page
title: Categories
---

{% capture allcategories %}
    {% for c in site.categories %}
        {{ c[0] | camelcase | replace: ' ', '_' }}
    {% endfor %}
{% endcapture %}
{% assign sortedcategories = allcategories | split: ' ' | sort %}

<ul class="posts">
    {% for category in sortedcategories %}
    {% capture category_name %}{{ category | replace: '_', ' ' | camelcase }}{% endcapture %}
        <h3>{{ category_name }}</h3>
        <div id="#{{ category_name | slugize | url_encode }}"></div>
        {% for post in site.categories[category_name] %}
            <li>
                <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a>
            </li>
        {% endfor %}
    {% endfor %}
</ul>