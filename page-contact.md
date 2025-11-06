---
layout: page
title: Contact
subtitle: Feel free to contact me
---

<!-- Include the Formspree form -->
<form
  id="contactForm"
  action="https://formspree.io/f/xjkpneae"
  class="fs-form"
  target="_top"
  method="POST"
  style="max-width:600px;margin:auto;"
>
  <div class="fs-field">
    <label class="fs-label" for="name">Your Name</label>
    <input class="fs-input" id="name" name="name" required />
  </div>

  <div class="fs-field">
    <label class="fs-label" for="email">Email</label>
    <input class="fs-input" id="email" name="_replyto" required />
    <p class="fs-description">
      This will help me respond to your query via an email.
    </p>
  </div>

  <div class="fs-field">
    <label class="fs-label" for="subject">Subject</label>
    <input class="fs-input" id="subject" name="subject" required />
    <!-- Hidden field for Formspree to set the email subject line -->
    <input type="hidden" name="_subject" id="hiddenSubject" />
  </div>

  <div class="fs-field">
    <label class="fs-label" for="message">Message</label>
    <textarea
      class="fs-textarea"
      id="message"
      name="message"
      required
    ></textarea>
    <p class="fs-description">What would you like to discuss?</p>
  </div>

  <div class="fs-button-group">
    <button class="fs-button" type="submit">Submit</button>
  </div>

  <p id="formMessage" style="text-align:center;color:green;font-weight:bold;margin-top:15px;display:none;">
    ✅ Your message was sent successfully!
  </p>
</form>

<!-- AJAX handling for submission + subject + confirmation message -->
<script>
  const form = document.getElementById('contactForm');
  const messageEl = document.getElementById('formMessage');

  form.addEventListener('submit', function(event) {
    event.preventDefault();

    // Copy subject into hidden field for Formspree
    const subjectValue = document.getElementById('subject').value;
    document.getElementById('hiddenSubject').value = subjectValue;

    const data = new FormData(form);

    fetch(form.action, {
      method: form.method,
      body: data,
      headers: {
        'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        messageEl.textContent = `✅ Your message about "${subjectValue}" was sent successfully!`;
        messageEl.style.display = 'block';
        form.reset();
      } else {
        response.json().then(data => {
          alert('Oops! There was a problem submitting your form.');
        })
      }
    }).catch(error => {
      alert('Oops! There was a problem submitting your form.');
    });
  });
</script>
