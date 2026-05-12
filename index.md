---
layout: default
title: Home
---

## My Latest Works

<div class="project-list">
  {% for post in site.posts %}
    <div class="project-card">
      <div class="project-image">
        {% if post.image %}
          <img src="{{ post.image }}" alt="Gambar {{ post.title }}">
        {% endif %}
      </div>
      
      <div class="project-content">
        <h3>
          {% if post.external_url and post.external_url != "" %}
            <a href="{{ post.external_url }}" target="_blank">{{ post.title }}</a>
          {% else %}
            <a href="{{ post.url }}">{{ post.title }}</a>
          {% endif %}
        </h3>
        
        <span class="post-date">{{ post.date | date: "%d %B %Y" }}</span>
        <p class="project-desc">{{ post.description }}</p>

        <div class="project-links">
          {% if post.github_url and post.github_url != "" %}
            <a href="{{ post.github_url }}" target="_blank" class="link-btn"><i class="fab fa-github"></i> Source Code</a>
          {% endif %}
          
          {% if post.demo_url and post.demo_url != "" %}
            <a href="{{ post.demo_url }}" target="_blank" class="link-btn"><i class="fas fa-external-link-alt"></i> Live Demo</a>
          {% endif %}
          
          {% if post.paper_url and post.paper_url != "" %}
            <a href="{{ post.paper_url }}" target="_blank" class="link-btn"><i class="fas fa-file-pdf"></i> Publikasi/Paper</a>
          {% endif %}
          
          {% if post.external_url and post.external_url != "" %}
            <a href="{{ post.external_url }}" target="_blank" class="link-btn btn-primary"><i class="fas fa-arrow-right"></i> Selengkapnya</a>
          {% else %}
            <a href="{{ post.url }}" class="link-btn btn-primary"><i class="fas fa-arrow-right"></i> Selengkapnya</a>
          {% endif %}
        </div>
      </div>
    </div>
  {% endfor %}
</div>