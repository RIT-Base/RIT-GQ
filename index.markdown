---
layout: default
---

<div class="mission-board">
  <h1>Papan Misi RIT</h1>
  <p>Temukan proyek yang kamu minati dan mari berkolaborasi!</p>

  <div class="card-container">
    {% for post in site.posts %}
      <a href="{{ post.url | relative_url }}" class="mission-card-link">
        <div class="mission-card">

          {% if post.image and post.image != "#" %}
            <img src="{{ post.image }}" alt="Gambar Proyek {{ post.title }}" class="card-image">
          {% endif %}

  
          <div class="card-content">
            <div class="card-header">
              <h2 class="card-title">{{ post.title }}</h2>
                <div class="card-tags-wrapper">
                {% for tag in post.tags %}
                    <span class="card-tag tag-{{ tag | downcase | replace: ' ', '-' }}">{{ tag }}</span>
                {% endfor %}
                </div>
            </div>
            <p class="card-contact"><strong>Kontak:</strong> {{ post.narahubung | join: ', ' }}</p>
            <p class="card-excerpt">{{ post.excerpt }}</p>
          </div>

   
        </div>
      </a>
    {% endfor %}
  </div>

</div>