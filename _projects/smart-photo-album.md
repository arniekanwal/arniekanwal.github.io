---
layout: page
title: Smart Photo Album
description: Fullstack AI photo album built on AWS
img: assets/img/smartphoto/smart-album.jpg
importance: 2
---

A machine learning based approach to photo album storage and retrieval built on event-driven architecture with AWS infrastructure...

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/smartphoto/smartphoto-arch.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

### Photo Indexing
The first lambda function implemented faciliates verifying and uploading images. It'll pass it seamlessly to an S3 bucket for storage and
forward the image to Rekognition (an AWS managed ML image labeler) for label/token generation. These labels are parsed, cleaned, and indexed
in an AWS OpenSearch instance (ElasticSearch) for future querying.

### Photo Search
Voice-to-text or search embedded directly on client-side javascript and sent in a payload to the second lambda function. This is disambiguated
by a ChatBot and sent to ElasticSearch which retrieves photo_ids (and photos) for all images grouped into the detected label categories. 

### Cloud Formation and Code Pipelines
Configuration files in `.yml` format paired with these two AWS services allowed for automatic code deployment via git webhooks
as well as the ability to respin services across the entire stack in case of failure.

### Examples

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/smartphoto/smart-album.jpg" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/smartphoto/smart-album1.png" title="example image" class="img-fluid rounded z-depth-1" %}
    </div>
</div>
<div class="caption">
    Example queries demonstrating the smart photo retrieval...
</div>