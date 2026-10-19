---
layout: default
title: 欢迎来到我的博客
subtitle: 记录我的学习与成长
permalink: /zh/
lang: zh-CN
---

<div class="lang-switch" style="text-align:right; margin-top:1rem;">
  <a href="{{ '/' | relative_url }}" lang="en">Switch to English</a>
</div>

<div class="nature-bg">
  <div class="main-columns">
    <div class="main-left">
      <h1>👋 Hi, 我是丽华</h1>
      <p class="lead">欢迎来到我的个人博客！这里记录了我的学习成长、技术探索与生活灵感。</p>
      <div class="colorful-section gradient-pinkblue">
        <h2>🚀 精选主题</h2>
        <ul class="post-highlights">
          <li>🤖 <b>AI/机器学习</b>：最新技术与实战经验</li>
          <li>💻 <b>Web开发</b>：前端、后端与全栈成长</li>
          <li>🧠 <b>算法</b>：刷题与竞赛心得</li>
          <li>🌈 <b>生活</b>：灵感、随笔与成长故事</li>
        </ul>
      </div>
    </div>
    <div class="main-right">
      <div class="colorful-section gradient-bluegreen posts-list-section">
        <h2>📝 最新文章</h2>
        <ul class="posts-list">
          {% for post in site.posts limit:8 %}
          <li class="post-card">
            <a href="{{ post.url | relative_url }}" class="post-title">{{ post.title }}</a>
            <span class="post-date">{{ post.date | date: '%Y-%m-%d' }}</span>
            <p class="post-excerpt">{{ post.excerpt | strip_html | truncate: 60 }}</p>
          </li>
          {% endfor %}
        </ul>
      </div>
    </div>
  </div>

  <div class="bottom-sections">
    <div class="colorful-section gradient-bluegreen about-section">
      <h2>🌟 关于我</h2>
      <p>计算机专业研究生，热爱技术、设计与分享。目标是用代码和创意让世界更美好。</p>
      <div class="about-icons">
        <span title="AI Enthusiast">🤖</span>
        <span title="Web Developer">💻</span>
        <span title="Designer">🎨</span>
        <span title="Lifelong Learner">📚</span>
      </div>
    </div>
    <div class="colorful-section gradient-yellowpink contact-section">
      <h2>📬 联系我</h2>
      <div class="social-links">
        <a href="https://github.com/AliLan" class="social-link">GitHub</a>
        <a href="mailto:your-email@example.com" class="social-link">Email</a>
      </div>
    </div>
  </div>
</div>

<style>
.nature-bg {
  min-height: 100vh;
  background: linear-gradient(180deg, #8fd6ff 0%, #eaf6ff 70%, #eaf6ff 100%);
  position: relative;
  overflow: hidden;
  max-width: 1500px;
  margin: 0 auto;
}
.main-columns {
  display: flex;
  flex-direction: row;
  justify-content: center;
  align-items: flex-start;
  gap: 2.5rem;
  max-width: 1500px;
  margin: 0 auto;
  padding-top: 90px;
  padding-bottom: 30px;
}
.main-left, .main-right {
  flex: 1 1 0;
  min-width: 320px;
  max-width: 520px;
}
.main-left {
  margin-right: 0.5rem;
}
.main-right {
  margin-left: 0.5rem;
}
.posts-list-section {
  min-height: 420px;
}
.posts-list {
  list-style: none;
  padding: 0;
  margin: 0;
}
.post-card {
  background: rgba(255,255,255,0.13);
  border-radius: 1.1rem;
  margin-bottom: 1.2rem;
  padding: 1.1rem 1.2rem 0.7rem 1.2rem;
  box-shadow: 0 2px 12px rgba(0,0,0,0.07);
  transition: box-shadow 0.2s, background 0.2s;
  position: relative;
}
.post-card:hover {
  background: rgba(255,255,255,0.22);
  box-shadow: 0 4px 24px rgba(90,200,250,0.13);
}
.post-title {
  font-size: 1.18rem;
  font-weight: 700;
  color: #fff;
  text-decoration: none;
  background: linear-gradient(90deg, #ff6b9d 30%, #5ac8fa 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
  background-clip: text;
}
.post-date {
  font-size: 0.98rem;
  color: #eaf6ff;
  margin-left: 0.7rem;
}
.post-excerpt {
  font-size: 1.02rem;
  color: #f5f5f7;
  margin: 0.3rem 0 0.1rem 0;
}
.bottom-sections {
  display: flex;
  flex-direction: column;
  gap: 1.5rem;
  max-width: 1500px;
  width: 100%;
  margin: 0 auto 40px auto;
}
.about-section, .contact-section {
  width: 100%;
  max-width: 1500px;
  min-width: 0;
  box-sizing: border-box;
  text-align: center;
}
.colorful-section {
  border-radius: 1.5rem;
  box-shadow: 0 4px 24px rgba(0,0,0,0.08);
  margin: 2.5rem auto;
  padding: 2.2rem 1.5rem 1.5rem 1.5rem;
  width: 100%;
  max-width: 1500px;
  color: #fff;
  position: relative;
  overflow: hidden;
  box-sizing: border-box;
}
.gradient-pinkblue {
  background: linear-gradient(120deg, #ff6b9d 0%, #5ac8fa 100%);
}
.gradient-bluegreen {
  background: linear-gradient(120deg, #5ac8fa 0%, #00c9a7 100%);
}
.gradient-yellowpink {
  background: linear-gradient(120deg, #ffe066 0%, #ff6b9d 100%);
}
.colorful-section h2 {
  font-size: 1.7rem;
  font-weight: 700;
  margin-bottom: 1rem;
  letter-spacing: -0.5px;
  color: #fff;
}
.colorful-section p {
  font-size: 1.1rem;
  margin-bottom: 1.2rem;
  color: #f5f5f7;
}
.post-highlights {
  list-style: none;
  padding: 0;
  margin: 0 0 0.5rem 0;
}
.post-highlights li {
  font-size: 1.08rem;
  margin: 0.5rem 0;
  padding-left: 0.5rem;
  color: #fff;
}
.about-icons {
  font-size: 2rem;
  margin-top: 1rem;
  display: flex;
  gap: 1.2rem;
  justify-content: center;
}
.social-links {
  display: flex;
  justify-content: center;
  gap: 1.2rem;
  margin-top: 1rem;
}
.social-link {
  display: inline-block;
  padding: 0.7rem 1.5rem;
  background: rgba(255,255,255,0.18);
  color: #fff;
  border-radius: 1.2rem;
  font-weight: 600;
  text-decoration: none;
  transition: background 0.2s, color 0.2s, box-shadow 0.2s;
  box-shadow: 0 2px 8px rgba(0,0,0,0.08);
}
.social-link:hover {
  background: #fff;
  color: #ff6b9d;
}

@media (max-width: 900px) {
  .main-columns, .bottom-sections {
    flex-direction: column;
    gap: 1.2rem;
    padding-top: 40px;
  }
  .main-left, .main-right, .about-section, .contact-section {
    max-width: 100%;
    min-width: 0;
  }
}

@media (max-width: 600px) {
  .home h1 { font-size: 2.1rem; }
  .colorful-section { padding: 1.2rem 0.5rem; }
  .nature-content { padding-top: 40px; }
  .cloud1 { width: 120px; }
  .cloud2 { width: 80px; }
  .tree1 { width: 40px; }
  .tree2 { width: 32px; }
}
</style>

