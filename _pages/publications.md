---
layout: archive
title: "Publications"
permalink: /publications/
author_profile: true
---
{% include base_path %}

{% if site.author.googlescholar %}
  <div class="wordwrap">The full publication list can be found on <a href="{{site.author.googlescholar}}">my Google Scholar profile</a>.</div>
{% endif %}

 (\* indicates equal contribution)

## Peer-reviewed
<p>
  {% assign current_year = '' %}
    {% for post in site.publications reversed %}
    {% if post.preprint != true %}
      {% assign pub_year = post.date | date: "%Y" %}
      {% if pub_year != current_year %}
        <h2>{{ pub_year }}</h2>
        {% assign current_year = pub_year %}
      {% endif %}
      {% include archive-single.html %}
    {% endif %}
  {% endfor %}
</p>

## Pre-prints
{% for post in site.publications reversed %}
  {% if post.preprint %}
    {% include archive-single.html %}
  {% endif %}
{% endfor %}