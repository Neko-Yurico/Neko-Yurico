---
layout: page
title: "Tags"
description: "哈哈，你找到了我的文章标签库"  
header-img: "img/semantic.jpg"  
---

<p style="text-align: center;">#Tags列表#</p>
<div id='tag_cloud'>
<p style="text-align: center;">{% for tag in site.tags %}
<a href="#{{ tag[0] }}" title="{{ tag[0] }}" rel="{{ tag[1].size }}">{{ tag[0] }}</a>
{% endfor %}</p>
</div>

<p style="text-align: center;">=========================</p>

<ul class="listing">
{% for tag in site.tags %}
  <p style="text-align: center;"><li class="listing-seperator" id="{{ tag[0] }}">{{ tag[0] }}</li></p>
{% for post in tag[1] %}
  <li class="listing-item">
  <time datetime="{{ post.date | date:"%Y-%m-%d" }}">{{ post.date | date:"%Y-%m-%d" }}</time>
  <a href="{{ post.url }}" title="{{ post.title }}">{{ post.title }}</a>
  </li>
{% endfor %}
{% endfor %}
</ul>

<script src="/media/js/jquery.tagcloud.js" type="text/javascript" charset="utf-8"></script> 
<script language="javascript">
$.fn.tagcloud.defaults = {
    size: {start: 1, end: 1, unit: 'em'},
      color: {start: '#f8e0e6', end: '#ff3333'}
};

$(function () {
    $('#tag_cloud a').tagcloud();
});
</script>
