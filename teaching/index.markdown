---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: default
title: Home
css: "/static/css/home.css"
---
<marquee>Lessons Spots Open!</marquee>

<article style="margin-top: 40px;">
My lessons are this this and this. I teach bass, drums, guitar, etc....
Rates are $60 per half hour, $100 per hour.
</article><br>

  <div class="form-container">
    <h2>Inquire About Music Lessons</h2>
    <form action="/submit-inquiry" method="POST">
      <label for="name">Your Name:</label>
      <input type="text" id="name" name="name" required>

      <label for="email">Email Address:</label>
      <input type="email" id="email" name="email" required>

      <label for="instrument">Instrument of Interest:</label>
      <select id="instrument" name="instrument" required>
        <option value="">Select an Instrument</option>
        <option value="guitar">Guitar</option>
        <option value="piano">Piano</option>
        <option value="violin">Violin</option>
        <option value="voice">Voice</option>
      </select>

      <label for="message">Your Message:</label>
      <textarea id="message" name="message" rows="4" placeholder="Tell us about your experience, goals, and availability" required></textarea>

      <button type="submit">Submit Inquiry</button>
    </form>
  </div>