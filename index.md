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

    [Read more]({{ post.url }})
{% endfor %}
