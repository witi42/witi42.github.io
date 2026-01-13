---
layout: default
---
# Robin Wiethüchter
Hi 👋, I’m Robin

For work and project opportunities, hit me up on [LinkedIn](https://www.linkedin.com/in/robin-wiethuchter/) or reach out to <img src="{{ site.url | default: rowi.dev }}{{ site.baseurl }}/assets/images/hi.jpeg" aria-hidden="true" style="height: 1.8em; vertical-align: text-bottom; margin: 0 0.2em; display: inline-block;">

<!-- > [LinkedIn](https://www.linkedin.com/in/robin-wiethuchter/) [X](https://x.com/wiethix) -->


## Projects

{% for post in site.posts %}
<!-- - [{{ post.title }} >>]({{ post.url }}) _{{ post.date | date: "%B %d, %Y" }}_ -->
- **{{ post.title }}** - _{{ post.date | date: "%B %d, %Y" }}_

    {{ post.excerpt }}

    {% if post.image %}
    <img src="{{ site.url | default: rowi.dev }}{{ site.baseurl }}/assets/images/{{ post.image }}" alt="{{ post.image_alt }}" width="280" style="display: block; margin-left: 0;">
    {% endif %}

    {% if post.youtube %}
    <div class="video-container">
        <iframe width="280" height="157" src="https://www.youtube.com/embed/{{ post.youtube | split: '/' | last }}" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
    {% endif %}

    [more ...]({{ post.url }})
{% endfor %}


