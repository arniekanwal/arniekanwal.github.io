---
layout: page
title: Patent Search 
description: Search engine for U.S. patents built on classic NLP techniques
img: assets/img/nlp/patentsearch-scores.png
importance: 3
paper: NLP_paper.pdf
---
Collaborated with a team of undergraduate students to develop a patent retrieval search engine. We experimented with 
latent dirichlet allocation (LDA) and query expansion, creating a TF-IDF model. Evaluating this system
provided roughly ~61.6% mean accuracy precision (MAP) in terms of giving the user what they asked for, and an average normalized
discounted cumulative gain (nDCG) of 87.4%, measured across a wide distribution of fields and against manually annotated data.


<header class="post-header">
    <div class="post-title">
        Read the paper: {% if page.paper %}
            <a href="{{ page.paper | prepend: 'assets/pdf/' | relative_url}}" target="_blank" rel="noopener noreferrer"><i class="fas fa-file-pdf"></i></a>
        {% endif %}
    </div>
</header>

<p></p>

Example search query with relative ranking:
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/nlp/patentsearch-query.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>