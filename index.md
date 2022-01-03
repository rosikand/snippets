<!-- Source for the following: https://www.jokecamp.com/blog/listing-jekyll-posts-by-tag/ -->

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

Collections: 

{% for collection in site.collections %}
  {% assign name = collection.label %}
  <b>{{ name }}</b>
  {% for post in site.[name] %}
  <ul>
      <li><a href="{{ post.url | prepend: site.baseurl }}">{{ post.title }}</a></li>
  </ul>
  {% endfor %}
{% endfor %}


We define collections here: 

{% for collection in site.collections %}

  {% assign name = collection.label %}
  
    <h1>{{ name }}</h1>

    {% for post in site.[name] %}
    <ul>
      <li><a href="{{ post.url }}">{{ post.title }}</a></li>
    </ul>
    {% endfor %}

{% endfor %}
