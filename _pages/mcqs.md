---
layout: page
title: MCQ Questions
permalink: /mcqs/
---

<div class="mcqs-page">
  <h1>❓ Multiple Choice Questions</h1>
  <p class="lead">Practice questions and potential exam materials to test your knowledge</p>

  <div class="mcq-sections">
    <div class="mcq-section">
      <h2>📝 Question Bank</h2>
      <div class="coming-soon">
        <div class="icon">🚧</div>
        <h3>Coming Soon!</h3>
        <p>MCQ questions are currently being prepared. Check back soon for comprehensive practice questions covering all lecture topics.</p>
        
        <div class="expected-topics">
          <h4>Expected Question Topics:</h4>
          <ul>
            <li>Cloud Computing Fundamentals</li>
            <li>Cloud Service Models (IaaS, PaaS, SaaS)</li>
            <li>Cloud Deployment Models</li>
            <li>Virtualization Technologies</li>
            <li>Physical Layer Components</li>
            <li>Virtual Layer Architecture</li>
            <li>Control Layer Functions</li>
            <li>Service Orchestration</li>
            <li>SLA and Business Continuity</li>
          </ul>
        </div>
      </div>
    </div>

    <div class="study-tips">
      <h2>📚 Study Tips</h2>
      <div class="tips-grid">
        <div class="tip-card">
          <h3>🎯 Focus Areas</h3>
          <p>Pay special attention to the 5 essential cloud characteristics and how to identify cloud vs non-cloud systems</p>
        </div>
        <div class="tip-card">
          <h3>📊 Service Models</h3>
          <p>Understand the differences between IaaS, PaaS, and SaaS - these are frequently tested</p>
        </div>
        <div class="tip-card">
          <h3>🏗️ Architecture</h3>
          <p>Know the cloud reference model layers and their functions</p>
        </div>
        <div class="tip-card">
          <h3>💼 Business Aspects</h3>
          <p>Study SLA components and business continuity measures</p>
        </div>
      </div>
    </div>

    <div class="quick-review">
      <h2>⚡ Quick Review</h2>
      <div class="review-section">
        <h3>Essential Cloud Characteristics (Remember all 5!):</h3>
        <ol class="characteristics-list">
          <li><strong>On-demand self-service</strong> - No human interaction needed</li>
          <li><strong>Broad network access</strong> - Available over network from any device</li>
          <li><strong>Resource pooling</strong> - Multi-tenant model with location independence</li>
          <li><strong>Rapid elasticity</strong> - Scale up/down automatically</li>
          <li><strong>Measured service</strong> - Usage monitoring and billing</li>
        </ol>
      </div>
      
      <div class="review-section">
        <h3>Cloud Reference Model Layers:</h3>
        <ol class="layers-list">
          <li><strong>Service Layer</strong> - Consumer interface</li>
          <li><strong>Service Orchestration Layer</strong> - Workflow automation</li>
          <li><strong>Control Layer</strong> - Resource provisioning</li>
          <li><strong>Virtual Layer</strong> - Virtualization software</li>
          <li><strong>Physical Layer</strong> - Hardware foundation</li>
        </ol>
      </div>
    </div>
  </div>
</div>

<style>
.mcqs-page {
  max-width: 1200px;
  margin: 0 auto;
}

.lead {
  font-size: 1.2rem;
  color: #6c757d;
  margin-bottom: 3rem;
  text-align: center;
}

.mcq-sections {
  display: grid;
  gap: 3rem;
}

.mcq-section {
  background: white;
  border: 1px solid #e1e4e8;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.coming-soon {
  text-align: center;
  padding: 3rem 2rem;
  background: linear-gradient(135deg, #f8f9fa 0%, #e9ecef 100%);
  border-radius: 8px;
}

.coming-soon .icon {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.coming-soon h3 {
  color: #495057;
  margin-bottom: 1rem;
}

.coming-soon p {
  color: #6c757d;
  margin-bottom: 2rem;
}

.expected-topics {
  max-width: 600px;
  margin: 0 auto;
  text-align: left;
}

.expected-topics h4 {
  color: #495057;
  margin-bottom: 1rem;
}

.expected-topics ul {
  color: #6c757d;
  line-height: 1.8;
}

.study-tips {
  background: white;
  border: 1px solid #e1e4e8;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.tips-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin-top: 1.5rem;
}

.tip-card {
  background: #f8f9fa;
  padding: 1.5rem;
  border-radius: 8px;
  border: 1px solid #e9ecef;
}

.tip-card h3 {
  color: #495057;
  margin-bottom: 0.5rem;
  font-size: 1.1rem;
}

.tip-card p {
  color: #6c757d;
  margin: 0;
  font-size: 0.95rem;
  line-height: 1.6;
}

.quick-review {
  background: white;
  border: 1px solid #e1e4e8;
  border-radius: 12px;
  padding: 2rem;
  box-shadow: 0 2px 4px rgba(0,0,0,0.1);
}

.review-section {
  margin-bottom: 2rem;
}

.review-section:last-child {
  margin-bottom: 0;
}

.review-section h3 {
  color: #495057;
  margin-bottom: 1rem;
}

.characteristics-list,
.layers-list {
  color: #495057;
  line-height: 1.8;
}

.characteristics-list li,
.layers-list li {
  margin-bottom: 0.5rem;
}

.characteristics-list strong,
.layers-list strong {
  color: #0366d6;
}

@media (max-width: 768px) {
  .mcqs-page {
    padding: 0 1rem;
  }
  
  .mcq-section,
  .study-tips,
  .quick-review {
    padding: 1.5rem;
  }
  
  .tips-grid {
    grid-template-columns: 1fr;
  }
  
  .coming-soon {
    padding: 2rem 1rem;
  }
}
</style>