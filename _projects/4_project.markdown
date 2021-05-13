d---
layout: page
title: 4 NELS
description: NELS allows searching indexed audio using audio or text queries.
img: /assets/img/NELS_semi.png
importance: 4
---

<p align="justify">NELS crawls audio from YouTube and indexes it with Sound Event Recognition. The indexed audio content is made available for search and retrieval through a website. NELS takes a text query and used linguistic similarity to compare against the class labels of the indexed audio content. We also studied audio queries and acoustic similarity for retrieval [1,2,3]. The problem with simply linking language to acoustics is that similarity in language semantics does not imply similarity of acoustic semantics. For example, we may query using the text “car brakes” and the most similar text in our database could be “car engine”, however the acoustics are very different. On the other hand, we might query with an audio recording containing a low-frequency rumble sound, and the most similar audio in our database could be from the class “heart murmur", however the original sound was "engine", which is totally different in linguistic semantics.</p>
<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/NELS_cross.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
The problem with simply linking language to acoustics is that similarity in language semantics does not imply similarity of acoustic semantics.
</div>

<p align="justify">My paper [4] introduced a cross-modal search and retrieval framework to create a joint representation that retains the same patterns of semantic closeness for both, audio and text. The same representation regardless of whether we give the model the word “car brakes”, or an acoustic example of a "car brakes". This is enabled by a shared latent space that combines lexical similarity with acoustic similarity. The shared space is learned in a data-driven way via a siamese neural network. </p>

<p align="justify">The siamese network consists of twin networks, each takes an input vector of any one modality --audio or text. For training, the network takes pairs that come from the same class or different classes, and then computes a similarity metric for each pair. This metric is utilized by a contrastive loss function to enforce constraints that cause similar pairs to come together and different pairs to go apart. The trained siamese network is used to extract the joint representations for either an audio or a text input query.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/NELS_crossdiagram.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    The framework enables cross-modal search and direct comparison of audio and text modalities for retrieval. The shared latent space combines lexical similarity with acoustic similarity.
</div>

<p align="justify">The overall performance after re-training did not improve dramatically, we achieved 1.4% average precision overall the sound events after five iterations based on Clarity Index selection. We found an interesting insight to explain the learning plateau. The notion of classes in audio can be inconsistent, and so any semi-supervised method may have a ceiling because an audio clip can be categorized into multiple acoustically similar, but semantically different categories, confounding the training of the classifier. For example, "gunshot" was often re-trained with audio corresponding to objects banging. Another example in later experiments was with "clapping", which mostly included audio of crowd clapping. The performance of the "clapping" recognizer was improving using crawled audio. However, few of the crawled recordings labeled as "clapping" were used for retraining, after a close inspection, these recordings had the sound of a single clap. The crawled audio that was used for retraining corresponded to the sound of "rain (falling)", which was acoustically similar to crowd clapping. The problem is that we do not know a priori which classes will have this issue. <b>Therefore, should we re-train classifiers based on acoustic similarity only or based on both acoustic and semantic similarity?</b>
</p>

<h3>References</h3>
1. Elizalde, Benjamin, Ankit Shah, Siddharth Dalmia, Min Hun Lee, Rohan Badlani, Anurag Kumar, Bhiksha Raj, and Ian Lane. "An approach for self-training audio event detectors using web data." In 2017 25th European Signal Processing Conference (EUSIPCO). IEEE, 2017.



<!--
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/1.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/3.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    Caption photos easily. On the left, a road goes through a tunnel. Middle, leaves artistically fall in a hipster photoshoot. Right, in another hipster photoshoot, a lumberjack grasps a handful of pine needles.
</div>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/5.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    This image can also have a caption. It's like magic.
</div>

You can also put regular text between your rows of images.
Say you wanted to write a little bit about your project before you posted the rest of the images.
You describe how you toiled, sweated, *bled* for your project, and then... you reveal it's glory in the next row of images.


<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    You can also have artistically styled 2/3 + 1/3 images, like these.
</div>


The code is simple.
Just wrap your images with `<div class="col-sm">` and place them inside `<div class="row">` (read more about the <a href="https://getbootstrap.com/docs/4.4/layout/grid/" target="_blank">Bootstrap Grid</a> system).
To make images responsive, add `img-fluid` class to each; for rounded corners and shadows use `rounded` and `z-depth-1` classes.
Here's the code for the last row of images above:

```html
<div class="row justify-content-sm-center">
    <div class="col-sm-8 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/6.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm-4 mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/11.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
```
-->
