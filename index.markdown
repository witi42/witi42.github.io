---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
---
# Robin Wiethüchter
Hi 👋, I’m Robin Wiethüchter, software engineer and co-founder of [Clipmate AI](https://clipmate.ai/).

## Projects

{% for post in site.posts %}
### [{{ post.title }}]({{ post.url }})
_{{ post.date | date: "%B %d, %Y" }}_

{{ post.excerpt }}

[Read more]({{ post.url }})
{% endfor %}
