---
layout: page
title:  "Biscuit Restaurant 1"
date:   2024-03-08 09:55:38 -0600
location:
    latitude: 34.83
    longitude: -87.73
---

{% leaflet_map { "center": [{{page.location.latitude}}, {{page.location.longitude}}],
                 "zoom": 9 } %}

        {% leaflet_marker { "latitude" : {{page.location.latitude}},
                            "longitude" : {{page.location.longitude}} } %}

{% endleaflet_map %}

![Picture of the biscuits]({{site.baseurl}}/assets/biscuits1.png)

These biscuits were good. The gravy was okay.

Write more here.
