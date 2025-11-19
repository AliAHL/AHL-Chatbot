---
title: Chatbot
---

# 🤖 My Chatbot

A simple, clean, modern page that works correctly on desktop and mobile.

<div class="chat-container">
  <iframe  
    src="https://udify.app/chatbot/sI7tIcJbUKYk9pHy"
    allow="microphone"
    frameborder="0"
    style="
      width: 100%;
      height: 700px;
      border: 0;
      border-radius: 14px;
      background: transparent;
    ">
  </iframe>
</div>

<footer class="foot">Made with ❤️ · GitHub Pages</footer>

<style>
:root {
  --bg: #0f172a;
  --card: #1e293b;
  --text: #e2e8f0;
  --muted: #94a3b8;
  --accent: #60a5fa;
}

[data-theme="light"] {
  --bg: #f7f9fc;
  --card: #ffffff;
  --text: #0f172a;
  --muted: #475569;
  --accent: #2563eb;
}

body {
  margin: 0;
  padding: 20px;
  font-family: Inter, system-ui, -apple-system, "Segoe UI", Roboto, Arial;
  background: var(--bg);
  color: var(--text);
}

/* Main chatbot card */
.chat-container {
  max-width: 900px;
  margin: 0 auto;
  padding: 16px;
  border-radius: 16px;
  background: var(--card);
  box-shadow: 0 10px 30px rgba(0,0,0,0.3);
}

/* Footer */
.foot {
  text-align: center;
  margin-top: 20px;
  font-size: 14px;
  color: var(--muted);
}

/* Responsive – original correct behavior */
@media(max-width: 900px) {
  .chat-container {
    padding: 12px;
  }
  
  iframe {
    height: 650px !important; /* same look as original */
  }
}
</style>
