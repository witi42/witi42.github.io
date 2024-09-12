---
layout: default
---
# Robin Wiethüchter
Hi 👋, I’m Robin Wiethüchter, software engineer and co-founder of [Clipmate AI](https://clipmate.ai/).

I've studied computer science at ETH Zürich (BSc, MSc) and previously worked at [urb-x AG](https://urb-x.ch/).

<!-- > [LinkedIn](https://www.linkedin.com/in/robin-wiethuchter/) [X](https://x.com/wiethix) -->

## Projects

{% for post in site.posts %}
- [{{ post.title }}]({{ post.url }})

    _{{ post.date | date: "%B %d, %Y" }}_

    {{ post.excerpt }}

    {% if post.image %}
    <img src="{{ site.url | default: rowi.dev }}{{ site.baseurl }}/assets/images/{{ post.image }}" alt="{{ post.image_alt }}" width="280" style="display: block; margin-left: 0;">
    {% endif %}

    {% if post.youtube %}
    <div class="video-container">
        <iframe width="280" height="157" src="https://www.youtube.com/embed/{{ post.youtube | split: '/' | last }}" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>
    </div>
    {% endif %}

    <!-- [Read more]({{ post.url }}) -->
{% endfor %}
