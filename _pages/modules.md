---
layout: page
permalink: /modules/
title: Modules
description: Academic modules and coursework from my Master's in AI
nav: true
nav_order: 1
---

<section class="modules-intro">
  <strong>Coursework Atlas:</strong> each module page brings together learning outcomes, unit notes, artefacts,
  and assessed project work in one place.
</section>

<div class="modules-grid">
  {% assign sorted_modules = site.modules | where: "name", "index.md" | sort: "importance" %}

  {% for module in sorted_modules %}
    {% if module.published != false %}
      <div class="module-card card mb-4">
        <div class="card-body">
          {% if module.category %}
            <span class="badge badge-{{ module.category | replace: 'completed', 'success' | replace: 'in-progress', 'primary' | replace: 'upcoming', 'secondary' }} float-right">
              {{ module.category | replace: '-', ' ' | capitalize }}
            </span>
          {% endif %}

          <h3 class="card-title">
            <a href="{{ module.url | relative_url }}">{{ module.title }}</a>
          </h3>

          {% if module.description %}
            <p class="card-text text-muted">{{ module.description }}</p>
          {% endif %}

          {% comment %} Count units in this module {% endcomment %}
          {% assign module_path = module.path | remove: 'index.md' %}
          {% assign module_items = site.modules | where_exp: "item", "item.path contains module_path" | where_exp: "item", "item.name != 'index.md'" %}
          {% assign unit_count = 0 %}
          {% for item in module_items %}
            {% if item.published != false %}
              {% unless item.path contains '/notes/' %}
                {% assign unit_count = unit_count | plus: 1 %}
              {% endunless %}
            {% endif %}
          {% endfor %}

          <p class="text-muted mb-2">
            <small>
              <i class="fas fa-book-open"></i>
              {% if unit_count > 0 %}
                {{ unit_count }} units
              {% else %}
                Unit map in progress
              {% endif %}
            </small>
          </p>

          <a href="{{ module.url | relative_url }}" class="btn btn-sm btn-outline-primary">
            View Module <i class="fas fa-arrow-right"></i>
          </a>
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>
