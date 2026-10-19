---
layout: default
title: Contact
permalink: /contact/
---
<div class="container">
  <header class="page-head">
    <h1 class="page-title">Get in Touch</h1>
    <p class="page-sub">Have a question, an opportunity, or just want to say hello? Fill out the form below and it will open in your email app, ready to send.</p>
  </header>
  <div class="contact-grid">
    <form class="form" id="contact-form">
      <div><label for="cf-name">Name *</label><input class="field" id="cf-name" name="name" placeholder="Your name" required></div>
      <div><label for="cf-email">Email *</label><input class="field" id="cf-email" name="email" type="email" placeholder="your@email.com" required></div>
      <div class="full"><label for="cf-subject">Subject</label><input class="field" id="cf-subject" name="subject" placeholder="What is this about?"></div>
      <div class="full"><label for="cf-message">Message *</label><textarea class="field" id="cf-message" name="message" placeholder="Your message..." required></textarea></div>
      <div class="full"><button class="btn btn-dark" type="submit">{% include icon.html name="send" %}Send Message</button></div>
    </form>
    <aside>
      <div class="card side-note">
        <h3>{% include icon.html name="chat" %}Reach me directly</h3>
        <p><a href="mailto:lihualan2025@gmail.com">lihualan2025@gmail.com</a></p>
        <p><a href="https://www.linkedin.com/in/lihualan">linkedin.com/in/lihualan</a></p>
        <p><a href="https://github.com/AliLan">github.com/AliLan</a></p>
      </div>
      <div class="card side-note">
        <h3>{% include icon.html name="pin" %}Location</h3>
        <p>Los Angeles, CA. Open to software engineering roles in AI, search, and backend systems.</p>
      </div>
    </aside>
  </div>
</div>
<script>
document.getElementById('contact-form').addEventListener('submit', function (e) {
  e.preventDefault();
  var f = e.target;
  var subject = f.subject.value || 'Hello from your website';
  var body = f.message.value + '\n\n' + f.name.value + ' <' + f.email.value + '>';
  window.location.href = 'mailto:lihualan2025@gmail.com?subject=' + encodeURIComponent(subject) + '&body=' + encodeURIComponent(body);
});
</script>
