---
layout: default
title: Collage de Yumi
---

<style>
.collage {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(140px, 1fr));
    gap: 8px;
    max-width: 960px;
    margin: 1.2rem auto;
}
.collage img {
    width: 100%;
    height: 160px;
    object-fit: cover;
    border-radius: 8px;
    box-shadow: 0 2px 6px rgba(0,0,0,0.12);
}
.note {
    text-align: center;
    color: #555;
    margin-top: 1rem;
}
</style>

## Collage de Yumi

{% assign cat_images = site.static_files | where_exp: "f", "f.path contains '/src/yumi/'" %}
{% if cat_images.size > 0 %}
<div class="collage">
    {% for f in cat_images %}
        <img src="{{ f.path | relative_url }}" alt="Yumi foto {{ forloop.index }}">
    {% endfor %}
</div>
{% else %}
<p class="note">No se encontraron imágenes en <code>src/yumi</code>. Añade tus fotos y vuelve a cargar la página.</p>
{% endif %}