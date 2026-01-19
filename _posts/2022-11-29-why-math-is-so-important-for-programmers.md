---
layout: post
title: "Why Math Is So Important For Programmers"
description: I created Arabesques in my free time. Arabesques is a generative art project inspired by scientific principles.
summary: The story behind Arabesques.
tags: Generative Art, NFT
---

<i>"If you want to find the secrets of the universe, think in terms of energy, frequency and vibration." Nikola Tesla.</i>

## Physics

Patterns emerge in sand on a metal plate vibrating at resonant frequencies. These exquisite patterns are a result of resonant modes created by standing acoustic waves on the metal plates. In other words, when the plate vibrates at just the right frequency, there are certain areas of the plate that actually "stand still", collecting the tiny bits of sand originally sprinkled onto the plate.

<div class="graphic-container">
    <video width="640" height="320" controls class="centered">
        <source src="https://arabesques.s3.us-east-2.amazonaws.com/IMG_5598.mp4" type="video/mp4" >
    </video>
</div>

In the late 18th century, Ernst Chladni, known as the father of acoustics, discovered this phenomenon, by stroking a metal plate with a violin bow. These plates are now known as <i>Chladni plates</i>. This intersection of physics and art is the inspiration for <i>Arabesques</i>.

Each plate in an Arabesque is a real metal plate, with real sand, photographed while in vibration. In some plates, the grains of sand are still visible. The captured image of the plate undergoes OpenCV transformation, using filters and color manipulation to produce a refined black square containing sand. An example of the original and transformed image are shown below.

<div class="images">
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Original photo</p>
</div>
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Transformed plate</p>
</div>
</div>


## Stitching Algorithms

While these plates are beautiful themselves, there is not much that is generative about them. In order to create the final product, the plates are stitched together using either a random grid algorithm or a quadtree algorithm and then recolored to the appropriate color scheme, dictated by the first two characters in the transaction hash passed into the art generation.

The random grid algorithm first selects <i>m</i> to dictate the mxm grid size, where 1 &#8804; m &#8804; 25. Then, as the grid is traversed, the number of grid spaces that a single Chladni plate covers is allocated via a pseudorandom generator, bounded by the mxm grid size or any existing plates already placed on the grid. Here are some examples of the random grid output:

<div class="images">
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
</div>
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
</div>
</div>

The quadtree algorithm utilizes a <a class="link" href="https://jimkang.com/quadtreevis/" target="_blank">quadtree</a> to partition the grid. Imagine a large square containing <i>n</i> points (these do not move during the subdividing process). The large square subdivides into four equally-sized, smaller squares, which each now contain a portion of the original <i>n</i> points. This process continues until each square contains at most <i>k</i> points laying within the square. The parameters, <i>n</i> and <i>k</i>, are pseudorandomly assigned.

The distribution of the <i>n</i> points in the grid allows for interesting patterns to occur. The algorithm selects from 6 different types of distributions: uniform, Gaussian, inverse Gaussian, triangle, inverse triangle, and a custom-crafted distribution of superimposed distributions that I can't really put into words. Here are some examples:

<div class="images">
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Custom distribution</p>
</div>
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Inverse triangle distribution</p>
</div>
</div>
<div class="images">
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Uniform distribution</p>
</div>
<div class="center-image-div">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Gaussian distribution</p>
</div>
</div>

## Color Schemes

After quite a bit of soul-searching, I found some colorings that I thought would be interesting combinations. All color schemes are shown below:

<div class="images">
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Original</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Dark</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Snow</p>
</div>
</div>
<div class="images">
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Sunday Morning</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Harley Q</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Ocean</p>
</div>
</div>

<div class="images">
<div class="center-image-div-mini">
    <img class="blog-img" src="/img/abqs-blog/pistachio.jpg">
    <p>Pistachio</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Crayons</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Desert Oasis</p>
</div>
</div>
<div class="images">
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Discotheque</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Violet Trees</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Elsa</p>
</div>
</div>
<div class="images">
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Yacht Week</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Neon</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Flamingo</p>
</div>
</div>

<div class="images">
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Forest Lights</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Inferno</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Whalewatching</p>
</div>
</div>
<div class="images">
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Chocolate</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Grape</p>
</div>
<div class="center-image-div-mini">
    <img src="{{ site.baseurl }}/img/99-blog/1.jpg" width="50%">
    <p>Navy</p>
</div>
</div>

## In Conclusion

Thanks for taking the time to read through this post. Arabesques is a reflection of myself, merging my passions in physics, programming, and art. Hope you enjoy this project as much as I do.
