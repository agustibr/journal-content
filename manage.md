---
title: Create a new Article
layout: manage
navbar: true
---

## Front matter 

<div id="form-article">
  <div class="mb-3">
    <input type="checkbox" id="checkbox" v-model="draft">
    
    <label for="checkbox">is a Draft</label>
  </div>

  <div class="mb-3">
    <label for="post[title]" class="form-label">Post title</label>

    <input v-model="title" type="text" class="form-control form-control-lg" id="post[title]" placeholder="">
  </div>

  <div class="mb-3">
    <label for="post[date]" class="form-label">Post date</label>

    <input v-model="date" type="text" class="form-control" id="post[date]" placeholder="">
  </div>

  <div class="mb-3">
    <label for="post[description]" class="form-label">Post description</label>
    
    <textarea v-model="description" class="form-control" id="post[description]" rows="3"></textarea>
  </div>

  <div class="mb-3">
    <label for="post[categories]" class="form-label">Post Category</label>

    <select v-model="category" class="form-select" aria-label="Select a category">
      <option disabled selected value="uncategorized">Select a category</option>

      {% for category in site.categories %}
      <option value="{{ category | first | slugify }}">{{ category | first }}</option>
      {% endfor %}
    </select>
  </div>


  <div class="mb-3">
    <label for="post[author]" class="form-label">Post author</label>

    <select v-model="author" class="form-select" aria-label="Select an author">
      <option disabled selected>Select an author</option>

      {% for author in site.authors %}
      <option value="{{ author.short_name }}">{{ author.name }}</option>
      {% endfor %}
    </select>
  </div>

  <div class="mb-3">
    <label for="post[journal-num]" class="form-label">Journal number</label>
    
    <select v-model="journal" class="form-select" aria-label="Select an author">
      <option disabled>Select a journal issue</option>

      <option value="journal-next">Next Journal issue</option>
      {% for journal in site.journals %}
        {% if journal.draft %}
          <option value="{{ journal.journal-num }}">{{ journal.title }}</option>
        {% endif %}
      {% endfor %}
    </select>

    <div class="form-text">To which Journal this article belongs to</div>
  </div>

  <div class="mb-3">
    <label for="post[lang]" class="form-label">Post language</label>
    
    <select class="form-select" aria-label="Select a language">
      <option selected>Select a language</option>

      {% for lang in site.languages %}
      <option value="{{ lang }}">{{ lang }}</option>
      {% endfor %}
    </select>
  </div>

  <div class="mb-3">
    <label for="post[article-order]" class="form-label">Post order</label>
    
    <input type="number" class="form-control form-control-sm" id="post[article-order]" placeholder="">

    <div class="form-text">To control the order of the article in relation to the Journal.</div>
  </div>

  <div class="mb-3">
    <label for="post[article-id]" class="form-label">Post identifier</label>
    
    <input type="text" class="form-control form-control-sm" id="post[article-id]" placeholder="">

    <div class="form-text">This is used to identify translations.</div>
  </div>

  ## Content blocks

  - cover image
  - related articles
  - numbers
  - cta
  - blockqoute

  <div class="mb-3">
    <label for="exampleFormControlTextarea1" class="form-label">Example textarea</label>
    <textarea class="form-control" id="exampleFormControlTextarea1" rows="3"></textarea>
  </div>


  <select class="form-select" aria-label="Default select example">
    <option selected>Open this select menu</option>
    <option value="1">One</option>
    <option value="2">Two</option>
    <option value="3">Three</option>
  </select>
</div>
