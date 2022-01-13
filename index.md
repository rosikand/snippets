{% for collection in site.collections %}
{% if collection.label != 'posts' %}
{% assign name = collection.label %}
<b>{{ name }}</b>
{% for post in site.[name] %}
{% if name == 'mathematics' %}
{% if post.exhibit %}
<ul>
<li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
</ul>
{% endif %}
{% else %}
<ul>
<li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
</ul>
{% endif %}
{% endfor %}
{% endif %}
{% endfor %}


www 

{% for tag in site.tags %}
  {% assign t = tag | first %}
  {% assign posts = tag | last %}

<b>{{ t }}</b>
<ul>
{% for post in posts %}
  {% if post.tags contains t %}
  <li>
    <a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a>
<!--     <span class="date">{{ post.date | date: "%B %-d, %Y"  }}</span> -->
  </li>
  {% endif %}
{% endfor %}
</ul>
{% endfor %}
