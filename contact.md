---
layout: page
permalink: /contact/
title: Contact me
---

<style>
.contact-form {
  max-width: 500px;
  margin: 0 auto;
  font-size: 16px;
}

.form-group {
  margin-bottom: 20px;
}

label {
  display: block;
  margin-bottom: 5px;
}

input,
textarea {
  display: block;
  width: 100%;
  padding: 10px;
  border: 1px solid #ccc;
  border-radius: 4px;
  box-sizing: border-box;
  font-size: 16px;
  font-family: inherit;
}

button {
  display: inline-block;
  padding: 10px 20px;
  background-color: #4CAF50;
  color: #fff;
  border: none;
  border-radius: 4px;
  cursor: pointer;
  font-size: 16px;
  font-family: inherit;
  transition: background-color 0.3s;
}

button:hover {
  background-color: #3e8e41;
}

</style>

<div class="contact-form">
  <form action="https://formspree.io/f/xdovjazk" method="post">
    <div class="form-group">
      <label for="name">Name</label>
      <input type="text" id="name" name="name" placeholder="Your name" required>
    </div>
    <div class="form-group">
      <label for="email">Email</label>
      <input type="email" id="email" name="email" placeholder="Your email" required>
    </div>
    <div class="form-group">
      <label for="message">Message</label>
      <textarea id="message" name="message" placeholder="Write your message here" required></textarea>
    </div>
    <button type="submit" class="btn">Send</button>
  </form>
</div>
