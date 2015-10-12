---
layout: page
---

{% for post in site.categories.technical %}

<div class="row">

  <div class="panel panel-default">
    <div class="panel-body">

      <div class="col-md-2">
          {% if post.thumbnail %}
            <img src="{{ site.baseurl}}/{{ post.thumbnail }}" style="width: 280px"/>
          {% else %}
            <img src="{{ site.baseurl}}/img/ads_logo.png" style="width: 280px"/>
          {% endif %}
      </div>

      <div class="col-md-2"></div>

      <div class="col-md-8">
        <h2><a href="{{ site.baseurl }}{{ post.url }}">{{post.title}}</a><br><small>{{ post.date | date_to_string }}</small></h2>
        <p>
          {{ post.content | strip_html | truncatewords:40 }}
        </p>
      </div>
    </div>

    <div class="panel-footer">
          <span class="label label-success">author: {{ post.author }}</span>
          <span class="label label-primary">category: {{ post.category }}</span>
    </div>

  </div>
</div>
{% endfor %}