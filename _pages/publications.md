---
layout: page
permalink: /publications/
title: Publications
description: Research publications from the Computational Gas Dynamics and Plasma Physics Lab.
nav: true
nav_order: 5
---

<div class="publications-intro">

<div class="publications-intro-label">RESEARCH OUTPUT</div>

<h2>Publications</h2>

<p>
Our publications span <strong>low-temperature plasma, hypersonic nonequilibrium
flow, kinetic theory, particle simulation, and GPU-accelerated
high-performance computing</strong>.
</p>

<p>
The bibliography below is maintained from the lab's publication database.
Use the search tools to explore publications by topic, author, or year.
</p>

</div>

{% include bib_search.liquid %}

<div class="publications">

{% bibliography %}

</div>
<script>
  window.addEventListener("load", () => {
    const publicationKey = new URLSearchParams(window.location.search).get("pub");
    if (!publicationKey) return;

    const publication = document.getElementById(publicationKey);
    const selectedEntry = publication?.closest(".bibliography > li");
    if (!selectedEntry) return;

    document.querySelectorAll(".bibliography > li").forEach((entry) => {
      entry.hidden = entry !== selectedEntry;
    });

    document.querySelectorAll("h2.bibliography").forEach((heading) => {
      const bibliography = heading.nextElementSibling;
      heading.hidden = bibliography !== selectedEntry.parentElement;
    });

    document.querySelectorAll("ol.bibliography").forEach((bibliography) => {
      bibliography.hidden = bibliography !== selectedEntry.parentElement;
    });

});
</script>
