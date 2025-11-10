---
layout: default
title: Andy Daily SEO News
---

<div class="page-header">
  <h1>Andy Daily SEO News</h1>
  <p class="subtitle">每日追蹤最新 SEO、AI 搜尋、Google 更新與行銷趨勢</p>
</div>

<ul class="post-list">
  {% for post in site.posts %}
  <li class="post-card">

    <a href="{{ post.url | relative_url }}">

      <!-- 標題 -->
      <div class="post-card-title">{{ post.title }}</div>

      <!-- 日期 -->
      <div class="post-card-meta">
        {{ post.date | date: "%Y-%m-%d" }}
      </div>

      <!-- 如果有分類，就顯示 -->
      {% if post.categories %}
        <div class="post-card-meta">
          {% for cat in post.categories %}
            <span class="category-tag">{{ cat }}</span>
          {% endfor %}
        </div>
      {% endif %}

      <!-- 摘要（自動從文章前 160 字抓） -->
      <div class="post-card-excerpt">
        {{ post.excerpt | strip_html | truncate: 160 }}
      </div>

    </a>

  </li>
  {% endfor %}
</ul>
