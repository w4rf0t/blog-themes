---
layout: page
title: About
description: Tiểu sử của thằng thường dân yêu hack
keywords: Kim Phu, mzlogin
comments: true
menu: About
permalink: /about/
---

Tôi là Kim Phú, tôi sống bằng mã và đứng bằng mã.

Chiêm ngưỡng "nghệ thuật mã hóa tao nhã".

Hãy tin rằng thực hành tạo nên sự hoàn hảo và cố gắng thay đổi cuộc sống của bạn.

## Link

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mzlogin.github.io' %}
<li>
Wechat：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ site.url }}/assets/images/qrcode.jpg" alt="maqr" />
</li>
{% endif %}
</ul>

## Skill Keywords

{% for skill in site.data.skills %}

### {{ skill.name }}

<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
