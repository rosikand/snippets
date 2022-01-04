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
