---
layout: page
title: 4 NELS
description: NELS allows searching indexed audio using audio or text queries.
img: /assets/img/NELS_crossdiagram.png
importance: 4
---

<p align="justify">NELS crawls audio from YouTube and indexes it with Sound Event Recognition. The indexed audio content is made available for search and retrieval through a website. NELS takes a text query and used linguistic similarity to compare against the class labels of the indexed audio content. We also studied audio queries and acoustic similarity for retrieval [1,2]. The problem with simply linking language to acoustics is that similarity in language semantics does not imply similarity of acoustic semantics. For example, we may query using the text “car brakes” and the most similar text in our database could be “car engine”, however the acoustics are very different. On the other hand, we might query with an audio recording containing a low-frequency rumble sound, and the most similar audio in our database could be from the class “heart murmur", however the original sound was "engine", which is totally different in linguistic semantics.</p>
<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/NELS_cross.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
The problem with simply linking language to acoustics is that similarity in language semantics does not imply similarity of acoustic semantics.
</div>

<p align="justify">In 2018, my paper [3] introduced a cross-modal search and retrieval framework to create a joint representation that retains the same patterns of semantic closeness for both, audio and text. The same representation regardless of whether we give the model the word “car brakes”, or an acoustic example of a "car brakes". This is enabled by a shared latent space that combines lexical similarity with acoustic similarity. The shared space is learned in a data-driven way via a twin neural network. </p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/NELS_crossdiagram.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    The framework enables cross-modal search and direct comparison of audio and text modalities for retrieval. The shared latent space combines lexical similarity with acoustic similarity.
</div>

<p align="justify">The twin network has two heads, each takes an input vector of any one modality --audio or text. For training, the network takes pairs that come from the same class or different classes, and then computes a similarity metric for each pair. This metric is utilized by a contrastive loss function to enforce constraints that cause similar pairs to come together and different pairs to go apart. The trained twin network is used to extract the joint representations for either an audio or a text input query.</p>

<p align="justify"> We carried two types of retrieval experiments, one with and one without joint embeddings. We used a sound event dataset with 11,000 audio files from 41 classes. The training set represented the database and the test set the query set. Audio or text were first used to extract embeddings from the single-modal pre-trained networks. Then, they were processed in two ways: (1) direct retrieval to compute the baseline, and (2) used to compute joint embeddings with the trained twin network, followed by retrieval. Retrieval performance was measured in terms of MAP@3 or mean average precision of the top 3 retrieved results.</p>

<p align="justify">We first demonstrated that (1) direct retrieval is insufficient for cross-modal retrieval and that (2) using joint embeddings allows cross-modal retrieval with performance comparable to single-modal retrieval. Cross-modal retrieval with opposite feature types yielded a random performance of 2.4% MAP@3, but with joint embeddings we obtained 71.3% MAP@3.</p>

<p align="justify">Our framework allows the use of out of vocabulary audio or text querying. For example, we considered the query "house", which is not part of the 41 classes and has a more abstract meaning. With text similarity, the top five retrieved items were: "drawer", "telephone", "writing", "gunshot", and "double bass". With lexico-acoustic similarity the items were: "meow", "cough", "finger snapping", "laughter", and "computer keyboard". On the other hand we have an example using the audio query "orchestra", also not included in the 41 classes. With acoustic similarity we retrieved: "applause", "cello", "acoustic guitar", "flute", "fireworks", "violin", and "clarinet". With lexico-acoustic similarity we retrieved "violin", "trumpet", "saxophone", "flute", "double bass", "clarinet", and "cello". It is interesting to note that both single and cross modal results are arguably relevant, but are not the same. </p>

<h3>Video</h3>
This project was developed during my 2018 internship at Microsoft Research in the Audio and Acoustics Group, and a video of my presentation is in the following <a href="https://www.microsoft.com/en-us/research/video/a-cross-modal-audio-search-engine-based-on-joint-audio-text-embeddings/">link</a>.

<h3>References</h3>
1. Manocha, Pranay, Rohan Badlani, Anurag Kumar, Ankit Shah, Benjamin Elizalde, and Bhiksha Raj. "Content-based representations of audio using siamese neural networks." In 2018 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), pp. 3136-3140. IEEE, 2018.
2. Fan, Jianyu, Eric Nichols, Daniel Tompkins, Ana Elisa Méndez Méndez, Benjamin Elizalde, and Philippe Pasquier. "Multi-Label Sound Event Retrieval Using A Deep Learning-Based Siamese Structure With A Pairwise Presence Matrix." In ICASSP 2020-2020 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), pp. 3482-3486. IEEE, 2020.
3. Elizalde, Benjamin, Shuayb Zarar, and Bhiksha Raj. "Cross modal audio search and retrieval with joint embeddings based on text and audio." In ICASSP 2019-2019 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), pp. 4095-4099. IEEE, 2019.

Date: Published on Abr 2021 from work done during my PhD between 2015-2020.


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
