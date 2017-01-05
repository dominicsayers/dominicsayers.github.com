---
layout: portfolio
title: Developer portfolio
---
<div class="buttons">
  <a href="/about/" class="btn btn-info">About me</a>
  <a href="/cv/" class="btn btn-info">CV</a>
</div>

<div class="portfolio-items">
  {% for portfolio_data in site.portfolio %}
  <div class="portfolio-item">
    <h3>{{ portfolio_data.name }}</h3>
    <div class="thumbnail" itemprop="image" itemscope itemtype="https://schema.org/ImageObject">
      <a href="{{ portfolio_data.url }}" target="portfolio">
        <img itemprop="url" src="/assets/article_images{{ page.url }}{{ portfolio_data.thumbnail }}">
      </a>
    </div>
    <ul>
      {% for technology in portfolio_data.technology %}
        <li>{{ technology }}</li>
      {% endfor %}
    </ul>
  </div>
  {% endfor %}

  <div class="portfolio-item">
    <h3>Github</h3>
    <div class="thumbnail" itemprop="image" itemscope itemtype="https://schema.org/ImageObject">
      <a href="{{ site.social.github.url }}" target="portfolio">
        <iframe src="https://githubbadge.appspot.com/dominicsayers?a=0" style="border: 0;height: 146px;width: 240px;overflow: hidden;" frameBorder="0"></iframe>
      </a>
    </div>
    <ul>
      <li>Open source maintainer</li>
      <li>Open source contributor</li>
      <li>Ruby gem author</li>
    </ul>
  </div>

  <div class="portfolio-item">
    <h3>Stack Overflow</h3>
    <div class="thumbnail" itemprop="image" itemscope itemtype="https://schema.org/ImageObject">
      <a href="{{ site.social.stack-overflow.url }}" target="portfolio">
        <img src="https://stackoverflow.com/users/flair/63349.png" width="208" height="58" />
      </a>
    </div>
    <ul>
      <li>Subject matter expert</li>
      <li>Community contributor</li>
    </ul>
  </div>
</div>
