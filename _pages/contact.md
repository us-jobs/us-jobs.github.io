---
title: "Contact"
layout: page
permalink: "/contact-us"
---

We’d love to hear from you! Whether you have questions, suggestions, or partnership inquiries, feel free to reach out.  

### 📧 Email Us  
For general inquiries and support, email us at:  
**[codingrhodes@gmail.com](mailto:codingrhodes@gmail.com)**  

### 📝 Submit a Message  
Fill out the form below to send us a message:  

  <form class="form" action="{% if site.contact.email %}https://formspree.io/{{site.contact.email}}{% else %}https://formspree.io/f/mvgzqzzn{% endif %}" method="POST">
    <div class="form__group">
      <label class="form__label screen-reader-text" for="form-name">Your Name</label>
      <input class="form__input" id="form-name" type="text" name="name" placeholder="Name" required>
    </div>
    <div class="form__group">
      <label class="form__label screen-reader-text" for="form-email">Your Email</label>
      <input class="form__input" id="form-email" type="email" name="_replyto" placeholder="Email" required>
    </div>
    <div class="form__group">
      <label class="form__label screen-reader-text" for="form-text">Your Message</label>
      <textarea class="form__input" id="form-text" name="text" rows="10" placeholder="Message" required></textarea>
    </div>
    <div class="form__group">
      <button class="button button--dark" type="submit">Send Message</button>
    </div>
  </form>
---

### 📍 Follow Us  
Stay connected for the latest job updates and career tips:  
- **Twitter**: [@CODINGRHODES](https://twitter.com/CODINGRHODES)  

📌 **Looking for a job?** Browse the latest listings at **[us-jobs.github.io](https://us-jobs.github.io/)**  

---