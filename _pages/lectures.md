---
layout: page
title: Lectures
permalink: /lectures/
---

<div class="lectures-page">
  <h1>📚 Course Lectures</h1>
  <p class="lead">Comprehensive notes covering all aspects of cloud computing infrastructure</p>

  <div class="lectures-grid">
    {% assign lectures = site.lectures | sort: 'lecture_number' %}
    {% for lecture in lectures %}
      <div class="lecture-card">
        <div class="lecture-header">
          <span class="lecture-number">Lecture {{ lecture.lecture_number }}</span>
          <span class="completion-status">✅</span>
        </div>
        <h3 class="lecture-title">
          <a href="{{ lecture.url | relative_url }}">{{ lecture.title }}</a>
        </h3>
        <div class="lecture-meta">
          <span class="lecture-date">{{ lecture.date | date: "%B %d, %Y" }}</span>
        </div>
        <p class="lecture-excerpt">{{ lecture.content | strip_html | truncatewords: 30 }}</p>
        <a href="{{ lecture.url | relative_url }}" class="read-more">Read More →</a>
      </div>
    {% endfor %}
  </div>
</div>

<style>
.lectures-page {
  max-width: 1200px;
  margin: 0 auto;
}

.lead {
  font-size: 1.2rem;
  color: #6c757d;
  margin-bottom: 3rem;
  text-align: center;
}

.lectures-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-top: 2rem;
}

.lecture-card {
  background: white;
  border: 1px solid #e1e4e8;
  border-radius: 12px;
  padding: 1.5rem;
  transition: all 0.3s ease;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.lecture-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 16px rgba(0,0,0,0.15);
  border-color: #0366d6;
}

.lecture-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
}

.lecture-number {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 600;
}

.completion-status {
  font-size: 1.2rem;
}

.lecture-title {
  margin-bottom: 0.5rem;
}

.lecture-title a {
  color: #24292e;
  text-decoration: none;
  font-size: 1.25rem;
  font-weight: 600;
}

.lecture-title a:hover {
  color: #0366d6;
}

.lecture-meta {
  color: #6a737d;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.lecture-excerpt {
  color: #586069;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.read-more {
  color: #0366d6;
  text-decoration: none;
  font-weight: 600;
  display: inline-flex;
  align-items: center;
  transition: color 0.2s ease;
}

.read-more:hover {
  color: #0256cc;
}

@media (max-width: 768px) {
  .lectures-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .lecture-card {
    padding: 1.25rem;
  }
}
</style>