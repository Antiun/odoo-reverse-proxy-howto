---
title: Odoo - Reverse Proxy HowTo
author: Antonio Espinosa
layout: default
---

{% for post in site.posts reversed %}
<section class="slide" id="{{ post.label }}">
{{ post.content }}
</section>
{% endfor %}
