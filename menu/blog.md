---
layout: page
title: Blog
---
<ul class="posts">
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li itemscope>
      <a href="{{ site.github.url }}{{ post.url }}">{{ post.title }}</a>
      <p class="post-date">
        <span>
          <i class="fa fa-calendar" aria-hidden="true"></i>
          {{ post.date | date: "%B %-d" }} - <i class="fa fa-clock-o" aria-hidden="true"></i> {% include read-time.html %}
        </span>
      </p>
    </li>

    <script>
  (function(w, d, t, s, n) {
    w.FlodeskObject = n;
    var fn = function() {
      (w[n].q = w[n].q || []).push(arguments);
    };
    w[n] = w[n] || fn;
    var f = d.getElementsByTagName(t)[0];
    var e = d.createElement(t);
    var h = '?v=' + new Date().getTime();
    e.async = true;
    e.src = s + h;
    f.parentNode.insertBefore(e, f);
  })(window, document, 'script', 'https://assets.flodesk.com/universal.js', 'fd');
</script>

  {% endfor %}
</ul>
