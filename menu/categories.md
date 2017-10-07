---
layout: page
title: Categories
---

<ul class="posts">
    {% for category in site.categories %}
        {% capture category_name %}{{ category | first }}{% endcapture %}

        <h3>{{ category_name }}</h3>
        <div id="#{{ category_name | slugize | url_encode }}"></div>

        {% for post in site.categories[category_name] %}
            <li>
                <a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a>
            </li>
        {% endfor %}
    {% endfor %}
</ul>