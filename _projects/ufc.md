---
layout: page
title: UFC Predictor
description: Sports Betting AI for the UFC
img: assets/img/ufc/ufc-logo.webp
importance: 1
---

As of this last update, the UFC Predictor project querying pre-trained XGBoost and PyTorch models
for MMA fight classification (i.e. predict the moneyline winner of a matchup).

The models are served through Docker + FastAPI. Users can make queries to this ML service which access
data from a PostgreSQL instance and builds a vectorized input to submit to the model. SQL access
is made through a custom library built on top of SQLAlchemy.

Project Repo: <a href="https://github.com/arniekanwal/ufc-predictor">link</a>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/ufc/ufc-arch.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

