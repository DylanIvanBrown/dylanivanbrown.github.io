---
layout: page
title: Search
permalink: /search/
---

<div id="search-container">
  <input type="text" id="search-input" placeholder="Search blog posts...">
  <ul id="results-container"></ul>
</div>

<script src="https://unpkg.com/simple-jekyll-search@latest/dest/simple-jekyll-search.min.js"></script>
<script>
  SimpleJekyllSearch({
    searchInput: document.getElementById('search-input'),
    resultsContainer: document.getElementById('results-container'),
    json: '/search.json',
    searchResultTemplate: '<li><a href="{url}">{title}</a> - {date}</li>',
    noResultsText: 'No results found',
    limit: 10,
    fuzzy: false
  })
</script>

<style>
  #search-input {
    width: 100%;
    padding: 10px;
    font-size: 16px;
    border: 1px solid #ddd;
    border-radius: 4px;
    margin-bottom: 20px;
  }

  #results-container {
    list-style: none;
    padding: 0;
  }

  #results-container li {
    padding: 10px;
    border-bottom: 1px solid #eee;
  }

  #results-container li a {
    font-weight: bold;
  }
</style>
