---
layout:       post
title:        "首个测试"
subtitle:     "First Test"
date:         2018-08-14 12:00:00
author:       "ShadowTuDark"
header-img:   "img/in-post/post-eleme-pwa/eleme-at-io.jpg"
header-mask:  0.3
catalog:      true
multilingual: true
tags:
    - test
    - test
    - test
---

<!-- Chinese Version -->
<div class="zh post-container">
    {% capture about_zh %}{% include posts/2017-07-12-upgrading-eleme-to-pwa/zh.md %}{% endcapture %}
    {{ about_zh | markdownify }}
</div>

<!-- English Version -->
<div class="en post-container">
    {% capture about_en %}{% include posts/2017-07-12-upgrading-eleme-to-pwa/en.md %}{% endcapture %}
    {{ about_en | markdownify }}
</div>
