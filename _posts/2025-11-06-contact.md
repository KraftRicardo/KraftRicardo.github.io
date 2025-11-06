---
layout: page
title: Contact
subtitle: Feel free to contact me about my projects or job offers.
---

<form id="contactForm" action="https://formspree.io/f/xjkpneae" method="POST" style="max-width:600px;margin:auto;">

  <label for="name">Your Name</label><br>
  <input type="text" id="name" name="name" required style="width:100%;padding:10px;margin-bottom:10px;"><br>

  <label for="email">Your Email</label><br>
  <input type="email" id="email" name="_replyto" required style="width:100%;padding:10px;margin-bottom:10px;"><br>

  <label for="subject">Subject</label><br>
  <input type="text" id="subject" name="_subject" required style="width:100%;padding:10px;margin-bottom:10px;"><br>

  <label for="message">Your Message (optional)</label><br>
  <textarea id="message" name="message" rows="6" style="width:100%;padding:10px;margin-bottom:20px;"></textarea><br>

  <div style="text-align:center;">
    <button type="submit" style="
      padding:14px 40px;
      background-color:#007acc;
      color:white;
      border:none;
      border-radius:8px;
      cursor:pointer;
      font-size:1.1rem;
      font-weight:500;
      transition: background-color 0.2s ease;
    ">
      Submit
    </button>
  </div>

  <p id="formMessage" style="text-align:center;color:green;font-weight:bold;margin-top:15px;display:none;">
    ✅ Your message was sent successfully!
  </p>

</form>

<script>
  const form = document.getElementById('contactForm');
  const messageEl = document.getElementById('formMessage');

  form.addEventListener('submit', function(event) {
    event.preventDefault(); // prevent default form submission

    const data = new FormData(form);

    fetch(form.action, {
      method: form.method,
      body: data,
      headers: {
        'Accept': 'application/json'
      }
    }).then(response => {
      if (response.ok) {
        const subject = data.get('_subject'); // get subject field
        messageEl.textContent = `✅ Your message about "${subject}" was sent successfully!`;
        messageEl.style.display = 'block'; // show success message
        form.reset(); // clear the form
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
