---
layout: page
title: AI Notes
permalink: /ai-notes/
---

<div class="ai-notes-page">
  <h1>🤖 AI-Generated Notes</h1>
  <p class="lead">AI-enhanced summaries and explanations for better understanding of cloud computing concepts</p>

  <div class="ai-notes-grid">
    {% assign ai_notes = site.ai_notes | sort: 'lecture_number' %}
    {% for note in ai_notes %}
      <div class="ai-note-card">
        <div class="ai-note-header">
          <span class="ai-note-number">AI Lecture {{ note.lecture_number }}</span>
          <span class="ai-badge">🤖 AI</span>
          <span class="completion-status">✅</span>
        </div>
        <h3 class="ai-note-title">
          <a href="{{ note.url | relative_url }}">{{ note.title }}</a>
        </h3>
        <div class="ai-note-meta">
          <span class="ai-note-date">{{ note.date | date: "%B %d, %Y" }}</span>
        </div>
        <p class="ai-note-excerpt">{{ note.content | strip_html | truncatewords: 25 }}</p>
        <div class="note-actions">
          <a href="{{ note.url | relative_url }}" class="read-more">Read AI Summary →</a>
          {% assign original_lecture = site.lectures | where: 'lecture_number', note.lecture_number | first %}
          {% if original_lecture %}
            <a href="{{ original_lecture.url | relative_url }}" class="compare-link">Compare with Original</a>
          {% endif %}
        </div>
      </div>
    {% endfor %}
  </div>

  <div class="ai-features">
    <h2>Why AI Notes?</h2>
    <div class="features-grid">
      <div class="feature-card">
        <h3>📝 Summarized Content</h3>
        <p>Key concepts extracted and presented in a clear, concise format</p>
      </div>
      <div class="feature-card">
        <h3>🔍 Enhanced Explanations</h3>
        <p>Complex topics broken down with additional context and examples</p>
      </div>
      <div class="feature-card">
        <h3>⚡ Quick Review</h3>
        <p>Perfect for rapid revision and understanding core concepts</p>
      </div>
    </div>
  </div>
</div>

<style>
.ai-notes-page {
  max-width: 1200px;
  margin: 0 auto;
}

.lead {
  font-size: 1.2rem;
  color: #6c757d;
  margin-bottom: 3rem;
  text-align: center;
}

.ai-notes-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(350px, 1fr));
  gap: 2rem;
  margin-bottom: 4rem;
}

.ai-note-card {
  background: linear-gradient(135deg, #f8f9ff 0%, #e3f2fd 100%);
  border: 1px solid #e1e4e8;
  border-radius: 12px;
  padding: 1.5rem;
  transition: all 0.3s ease;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.ai-note-card:hover {
  transform: translateY(-4px);
  box-shadow: 0 8px 16px rgba(0,0,0,0.15);
  border-color: #2196f3;
}

.ai-note-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 1rem;
  flex-wrap: wrap;
  gap: 0.5rem;
}

.ai-note-number {
  background: linear-gradient(135deg, #2196f3 0%, #1976d2 100%);
  color: white;
  padding: 0.25rem 0.75rem;
  border-radius: 20px;
  font-size: 0.85rem;
  font-weight: 600;
}

.ai-badge {
  background: #4caf50;
  color: white;
  padding: 0.2rem 0.5rem;
  border-radius: 12px;
  font-size: 0.75rem;
  font-weight: 600;
}

.completion-status {
  font-size: 1.2rem;
}

.ai-note-title {
  margin-bottom: 0.5rem;
}

.ai-note-title a {
  color: #1565c0;
  text-decoration: none;
  font-size: 1.25rem;
  font-weight: 600;
}

.ai-note-title a:hover {
  color: #0d47a1;
}

.ai-note-meta {
  color: #6a737d;
  font-size: 0.9rem;
  margin-bottom: 1rem;
}

.ai-note-excerpt {
  color: #424242;
  line-height: 1.6;
  margin-bottom: 1.5rem;
}

.note-actions {
  display: flex;
  gap: 1rem;
  flex-wrap: wrap;
}

.read-more {
  color: #1976d2;
  text-decoration: none;
  font-weight: 600;
  display: inline-flex;
  align-items: center;
  transition: color 0.2s ease;
}

.read-more:hover {
  color: #0d47a1;
}

.compare-link {
  color: #757575;
  text-decoration: none;
  font-size: 0.9rem;
  transition: color 0.2s ease;
}

.compare-link:hover {
  color: #424242;
}

.ai-features {
  margin-top: 4rem;
  text-align: center;
}

.ai-features h2 {
  color: #1976d2;
  margin-bottom: 2rem;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
}

.feature-card {
  background: white;
  padding: 1.5rem;
  border-radius: 8px;
  border: 1px solid #e1e4e8;
  box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.feature-card h3 {
  color: #1976d2;
  margin-bottom: 0.5rem;
}

.feature-card p {
  color: #6c757d;
  margin: 0;
}

@media (max-width: 768px) {
  .ai-notes-grid {
    grid-template-columns: 1fr;
    gap: 1.5rem;
  }
  
  .ai-note-card {
    padding: 1.25rem;
  }
  
  .note-actions {
    flex-direction: column;
    gap: 0.5rem;
  }
}
</style>