---
layout: default
title: Home
---

<div class="hero-section">
  <h1>Cloud Computing Infrastructure</h1>
  <p class="lead">Comprehensive notes for COE505 - Cloud Computing Infrastructure</p>
  <p class="subtitle">MSc. Machine Learning Program @ American University of Sharjah</p>
</div>

<div class="content-sections">
  <div class="section-grid">
    
    <div class="section-card">
      <h2>📚 Lecture Notes</h2>
      <p>Original comprehensive notes covering all aspects of cloud computing infrastructure.</p>
      <div class="lecture-links">
        <a href="{{ '/lectures/lecture-1/' | relative_url }}" class="lecture-link">Lecture 1: Introduction to Cloud Computing ✅</a>
        <a href="{{ '/lectures/lecture-2/' | relative_url }}" class="lecture-link">Lecture 2: Cloud Computing Models ✅</a>
        <a href="{{ '/lectures/lecture-3/' | relative_url }}" class="lecture-link">Lecture 3: Virtualization Technologies ✅</a>
        <a href="{{ '/lectures/lecture-4/' | relative_url }}" class="lecture-link">Lecture 4: Storage and Networking ✅</a>
        <a href="{{ '/lectures/lecture-5/' | relative_url }}" class="lecture-link">Lecture 5: Advanced Topics ✅</a>
      </div>
      <a href="{{ '/lectures/' | relative_url }}" class="section-button">View All Lectures →</a>
    </div>

    <div class="section-card">
      <h2>🤖 AI-Generated Notes</h2>
      <p>AI-enhanced summaries and explanations for better understanding.</p>
      <div class="lecture-links">
        <a href="{{ '/ai-notes/lecture1/' | relative_url }}" class="lecture-link">AI Lecture 1 ✅</a>
        <a href="{{ '/ai-notes/lecture2/' | relative_url }}" class="lecture-link">AI Lecture 2 ✅</a>
        <a href="{{ '/ai-notes/lecture3/' | relative_url }}" class="lecture-link">AI Lecture 3 ✅</a>
        <a href="{{ '/ai-notes/lecture4/' | relative_url }}" class="lecture-link">AI Lecture 4 ✅</a>
        <a href="{{ '/ai-notes/lecture5/' | relative_url }}" class="lecture-link">AI Lecture 5 ✅</a>
      </div>
      <a href="{{ '/ai-notes/' | relative_url }}" class="section-button">Explore AI Notes →</a>
    </div>

    <div class="section-card">
      <h2>❓ MCQ Questions</h2>
      <p>Practice questions and potential exam materials to test your knowledge.</p>
      <a href="{{ '/mcqs/' | relative_url }}" class="section-button">Practice MCQs →</a>
    </div>

  </div>
</div>

<div class="about-section">
  <h2>About This Course</h2>
  <p>This website contains comprehensive study materials for COE505 - Cloud Computing Infrastructure, covering everything from basic cloud concepts to advanced virtualization technologies and distributed systems.</p>
</div>

<style>
.hero-section {
  text-align: center;
  padding: 4rem 0;
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  margin: -2rem -2rem 3rem -2rem;
  border-radius: 0 0 20px 20px;
}

.hero-section h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
  font-weight: 700;
}

.lead {
  font-size: 1.3rem;
  margin-bottom: 0.5rem;
  opacity: 0.9;
}

.subtitle {
  font-size: 1.1rem;
  opacity: 0.8;
}

.content-sections {
  margin: 3rem 0;
}

.section-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 2rem;
  margin-bottom: 3rem;
}

.section-card {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 12px;
  border: 1px solid #e9ecef;
  transition: transform 0.2s ease, box-shadow 0.2s ease;
}

.section-card:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}

.section-card h2 {
  color: #495057;
  margin-bottom: 1rem;
}

.section-card p {
  color: #6c757d;
  margin-bottom: 1.5rem;
}

.lecture-links {
  display: flex;
  flex-direction: column;
  gap: 0.5rem;
  margin-bottom: 1.5rem;
}

.lecture-link {
  color: #0366d6;
  text-decoration: none;
  padding: 0.5rem;
  background: white;
  border-radius: 6px;
  border: 1px solid #e1e4e8;
  transition: all 0.2s ease;
  font-size: 0.9rem;
}

.lecture-link:hover {
  background: #f6f8fa;
  border-color: #0366d6;
}

.section-button {
  display: inline-block;
  background: #0366d6;
  color: white;
  padding: 0.75rem 1.5rem;
  text-decoration: none;
  border-radius: 6px;
  font-weight: 600;
  transition: background-color 0.2s ease;
}

.section-button:hover {
  background: #0256cc;
  color: white;
}

.about-section {
  background: #f8f9fa;
  padding: 2rem;
  border-radius: 12px;
  border: 1px solid #e9ecef;
  text-align: center;
}

.about-section h2 {
  color: #495057;
  margin-bottom: 1rem;
}

.about-section p {
  color: #6c757d;
  max-width: 800px;
  margin: 0 auto;
  line-height: 1.6;
}

@media (max-width: 768px) {
  .hero-section h1 {
    font-size: 2rem;
  }
  
  .section-grid {
    grid-template-columns: 1fr;
  }
  
  .hero-section {
    margin: -1rem -1rem 2rem -1rem;
    padding: 2rem 1rem;
  }
}
</style>