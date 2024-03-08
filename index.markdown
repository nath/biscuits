---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---

{% leaflet_map { "center": [34.8332627, -87.7315695],
                 "zoom": 7 } %}
    {%- for post in site.posts -%}
        {% if post.location.latitude and post.location.longitude %}
            {% comment %} We have to capture to be able to use the liquid filters {% endcomment %}
            {%- capture href -%}
            {{ post.url | relative_url }}
            {%- endcapture %}
            {% leaflet_marker { "latitude" : {{post.location.latitude}},
                                "longitude" : {{post.location.longitude}},
                                "popupContent": "{{post.title}}",
                                "href": "{{href}}" } %}
        {% endif %}
    {% endfor %}
{% endleaflet_map %}
