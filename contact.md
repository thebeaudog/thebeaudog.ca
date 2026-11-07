---
layout: default
title: Contact
permalink: /contact/
description: Book by email, text or call. The Beau Dog Grooming Salon, Fireside, Cochrane, AB.
---

# Contact

To book, please email, text or call.

<div class="card">
  <h3>Get in touch</h3>
  <div class="card-body">
    <table class="price-table">
      <tr>
        <th scope="row">Email</th>
        <td><a href="mailto:{{ site.email }}">{{ site.email }}</a></td>
      </tr>
      <tr>
        <th scope="row">Text or call</th>
        <td><a href="tel:+1{{ site.phone_digits }}">{{ site.phone_display }}</a></td>
      </tr>
      <tr>
        <th scope="row">Location</th>
        <td>Fireside, Cochrane, AB</td>
      </tr>
    </table>
  </div>
</div>

<div class="button-row">
  <a class="button" href="tel:+1{{ site.phone_digits }}">Call</a>
  <a class="button secondary" href="sms:+1{{ site.phone_digits }}">Text</a>
  <a class="button secondary" href="mailto:{{ site.email }}">Email</a>
</div>

<p class="social">
  Follow along on <a href="{{ site.facebook }}">Facebook</a> and <a href="{{ site.instagram }}">Instagram</a>.
</p>
