---
layout: default
title: Services
permalink: /services/
description: Full groom, deshed, express bath and add-on services with prices at The Beau Dog Grooming Salon in Cochrane, AB.
---

# Services &amp; Prices

All prices are dependent on behaviour, coat condition and length. Applicable taxes will apply.

## What's included

<div class="columns">
  <div class="card">
    <h3>Full Groom</h3>
    <div class="card-body">
      <ul class="checklist">
        {% for item in site.data.pricing.includes.full_groom %}<li>{{ item }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
  <div class="card">
    <h3>Deshed</h3>
    <div class="card-body">
      <ul class="checklist">
        {% for item in site.data.pricing.includes.deshed %}<li>{{ item }}</li>
        {% endfor %}
      </ul>
    </div>
  </div>
</div>

## Dog size guide

<div class="table-scroll">
  <table class="matrix">
    <thead>
      <tr>
        <th scope="col">Size</th>
        <th scope="col">Weight</th>
      </tr>
    </thead>
    <tbody>
      {% for size in site.data.pricing.sizes %}
      <tr>
        <th scope="row">{{ size.name }}</th>
        <td>{{ size.guide }}</td>
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

## Full Groom

<div class="columns">
  {% for cut in site.data.pricing.full_groom %}
  <div class="card">
    <h3>{{ cut.name }} <small>{{ cut.length }}</small></h3>
    <div class="card-body">
      <table class="price-table">
        {% for size in site.data.pricing.sizes %}
        <tr>
          <th scope="row">{{ size.name }}</th>
          <td>${{ cut.prices[forloop.index0] }}</td>
        </tr>
        {% endfor %}
      </table>
      <p class="note small">{{ cut.blurb }}</p>
    </div>
  </div>
  {% endfor %}
</div>

## Deshed

For the double coated dogs.

<div class="table-scroll">
  <table class="matrix">
    <thead>
      <tr>
        <th scope="col">Coat type</th>
        {% for size in site.data.pricing.sizes %}<th scope="col">{{ size.name }}</th>
        {% endfor %}
      </tr>
    </thead>
    <tbody>
      {% for coat in site.data.pricing.deshed.coats %}
      <tr>
        <th scope="row">{{ coat.name }}<span class="eg">e.g. {{ coat.examples }}</span></th>
        {% for price in coat.prices %}<td>${{ price }}</td>
        {% endfor %}
      </tr>
      {% endfor %}
    </tbody>
  </table>
</div>

<p class="note">Trimming of feathers can be added to any deshed for an additional fee:
{% for size in site.data.pricing.sizes %}{{ size.name }} +${{ site.data.pricing.deshed.feather_trim[forloop.index0] }}{% unless forloop.last %}, {% endunless %}{% endfor %}.</p>

## The Express

{{ site.data.pricing.express.note }}

<div class="card">
  <div class="card-body">
    <table class="price-table">
      {% for size in site.data.pricing.sizes %}
      <tr>
        <th scope="row">{{ size.name }}</th>
        <td>{{ site.data.pricing.express.prices[forloop.index0] }}</td>
      </tr>
      {% endfor %}
    </table>
  </div>
</div>

## Short services &amp; add ons

<div class="card">
  <div class="card-body">
    <table class="price-table">
      {% for item in site.data.pricing.addons %}
      <tr>
        <th scope="row">{{ item.name }}</th>
        <td>{{ item.price }}</td>
      </tr>
      {% endfor %}
    </table>
    {% for item in site.data.pricing.addons %}{% if item.note %}<p class="note small"><strong>{{ item.name }}:</strong> {{ item.note }}</p>{% endif %}{% endfor %}
  </div>
</div>

<div class="button-row">
  <a class="button" href="{{ '/contact/' | relative_url }}">Book an appointment</a>
</div>
