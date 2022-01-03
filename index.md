{% for collection in site.collections %}
  {% assign name = collection.label %}
  <b>{{ name }}</b>
  {% for post in site.[name] %}
    <ul>
        <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
    </ul>
  {% endfor %}
{% endfor %}

yo 



{% for collection in site.collections %}
  {% if collection.label != 'posts' %}
    {% assign name = collection.label %}
    <b>{{ name }}</b>
    {% for post in site.[name] %}
    <ul>
        <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
    </ul>
    {% endfor %}
  {% endif %}
{% endfor %} 
