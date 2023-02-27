---
layout: page
title: About
description: 这不操作一下？
keywords: Yuhua Situ, 司徒宇骅
comments: true
menu: 关于
permalink: /about/
---

他们都叫我司徒。

我遇到什么都想操作一下——希望多操作几下之后，周围的世界会有一点不一样。

## 联系

<ul>
{% for website in site.data.social %}
<li>{{website.sitename }}：<a href="{{ website.url }}" target="_blank">@{{ website.name }}</a></li>
{% endfor %}
{% if site.url contains 'mazhuang.org' %}
<li>
微信公众号：<br />
<img style="height:192px;width:192px;border:1px solid lightgrey;" src="{{ assets_base_url }}/assets/images/qrcode.jpg" alt="咩" />
</li>
{% endif %}
</ul>


## Skill Keywords

下面的东西我都在项目里或多或少的专门用过，有兴趣的话可以一起讨论，交流经验。

{% for skill in site.data.skills %}
### {{ skill.name }}
<div class="btn-inline">
{% for keyword in skill.keywords %}
<button class="btn btn-outline" type="button">{{ keyword }}</button>
{% endfor %}
</div>
{% endfor %}
