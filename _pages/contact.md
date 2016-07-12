---
permalink: "/contact"
layout: single
author_profile: false

title: "Contact"

---

{% include base_path %}

If you would like to get ahold of us, please fill out the form and hit submit and someone will reply as soon as possible.

<script>
  function FormSubmit() {
    var interestval = document.getElementById("interest").value;
    var meh = document.getElementById("contactForm");
    if (interestval == "") {
      meh.action = "https://getsimpleform.com/messages?form_api_token=935cf1c8889ced426eccce7fcc4ed9e3";
    } else {
      meh.action = "/contact";
    }
    meh.submit();
  }
</script>

<style> #interest { display: none; } </style>

<form id="contactForm" action="/contact" method="post">

  {% if jekyll.environment == "production" %}
    <input type='hidden' name='redirect_to' value='{{site.environments.production.url}}/thank_you.html' />
  {% else %}
    <input type='hidden' name='redirect_to' value='{{site.environments.development.url}}/thank_you.html' />
  {% endif %}

  <input id='interest' type='text' name='interest' />

  <!-- all your input fields here.... -->
  <div style="margin-bottom: 1em;">
    <label for='name'>Name</label>
    <input type='text' name='name' />
  </div>

  <div style="margin-bottom: 1em;">
    <label for='subject'>Subject</label>
    <input type='text' name='subject' />
  </div>

  <div style="margin-bottom: 1em;">
    <label for='content'>How can we help you?</label>
    <textarea name='content' rows='10'></textarea>
  </div>

  <div style="margin-bottom: 1em;">
    <input class='btn btn--large btn--info' value="Submit" onclick="FormSubmit()" />
  </div>
</form>

{% include paginator.html %}

