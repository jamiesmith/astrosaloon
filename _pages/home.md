---
layout: splash
permalink: /
header:
  overlay_color_off: "#5e616c"
  overlay_image: /assets/images/homepage/Horizontal-mw-banner.jpg
  caption:
excerpt: 'Join us as we photograph the stars, listen to music, and drink booze.<br/>'

feature_row:
  - image_path: /assets/images/homepage/horizontal-mw-teaser.jpg
    alt: "Astrophotography"
    title: "Astrophotography"
    excerpt: "Whether from my yard or our club's dark-sky site in Taxahaw, SC, here's where they go.  I'll get better."
    url: "/tags/astrophotography"
    btn_class: "btn--primary"
    btn_label: "Astrophotography"
  - image_path: /assets/images/homepage/elephants-trunk-thumb.jpg
    alt: "Music & More"
    title: "Music & More"
    excerpt: "A night under the stars goes well with some music.  Here you will find some of our favorites, including links when possible."
    url: "/tags/music"
    btn_class: "btn--primary"
    btn_label: "Music"
  - image_path: /assets/images/homepage/vertical_mw_clone_thumb.jpg
    alt: "Booze"
    title: "Booze"
    excerpt: "Here in the Astro Saloon we take our booze seriously.  Quality liquor, hand-carved clear ice, and generous pours."
    url: "/tags/booze"
    btn_class: "btn--primary"
    btn_label: "Booze"

intro:
  - excerpt: 'Get notified when we add new stuff &nbsp; [<i class="fab fa-twitter"></i> @AstroSaloon](https://twitter.com/AstroSaloon){: .btn .btn--twitter}'

outro:
  - excerpt: '[<i class="fab fa-paypal"></i> Tip Me](https://paypal.me/jamiesmithnc){: .btn .btn--primary}'
---

{% include feature_row id="intro" type="center" %}

{%- for post in site.posts limit:7 -%}
  {% include archive-single.html %}
{%- endfor -%}

