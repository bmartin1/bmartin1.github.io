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

<p align="justify"> We carried two types of retrieval experiments, one with and one without joint embeddings. We used a sound event dataset with 11,000 audio files from 41 classes. The training set represented the database and the test set the query set. Audio or text were first used to extract embeddings from the pre-trained networks. Then, they were processed in two ways: (1) direct retrieval to compute the baseline, and (2) used to compute joint embeddings with the trained twin network, followed by retrieval. Retrieval performance is measured in terms of MAP@3, which is the mean of average precision scores and measures whether any of the top 3 retrieved results corresponds to the query and if so in what position.</p>

<p align="justify">We first demonstrated that (1) direct retrieval is insufficient for cross-modal retrieval and that (2) using joint embeddings allows cross-modal retrieval with performance comparable to single-modality retrieval. Cross-modal retieval with opposite feature types yielded a random performance of 2.4% MAP@3, but with joint embeddings we obtained 71.3% MAP@3.
</p>

<p align="justify">We compared single-modal vs cross-modal retrieval results to show the.... We considered the text label "gunshot", computed text features, compared them against text features of the other 40 classes using cosine similarity, and retrieved the following top four labels: "gunshot", "tearing", "applause", "cough". Next, we extracted joint embeddings of "gunshot", compared them against the joint embeddings created from audio queries using cosine lexico-acoustic similarity , and retrieved audio corresponding to the following four labels: ``fireworks", ``gunshot", ``microwave oven", ``knock". Another example was ``meow", which retrieved with text similarity: ``meow", ``fart", ``cough" and with lexico-acoustic similarity: ``meow", ``bark", ``trumpet". From these results, the main conclusion is that although both approaches predicted the correct class, they retrieved different results, which suggests that the shared space includes knowledge that combines both modalities.</p>

<p align="justify">Our framework allows the use of OOV class labels for querying. For example, we considered the query ``house", which is not part of the training data and which has a more abstract meaning than any label in the training data. With text and lexico-acoustic similarity, the top five retrieved items were: ``drawer", ``telephone", ``writing", ``gunshot", ``double bass" and ``meow", ``cough", ``finger snapping", ``laughter", ``computer keyboard", respectively. It is interesting to note that both results are arguably relevant, but are not the same.

Another example of audio query was ``orchestra", which retrieved ``applause", ``cello", ``acoustic guitar", ``flute", ``fireworks", ``violin", ``clarinet" and ``violin", ``trumpet", ``saxophone", ``flute", ``double bass", ``clarinet", ``cello" with acoustic and lexico-acoustic similarities, respectively.</p>

<h3>Video</h3>
This project was developed during my 2018 internship at Microsoft Research in the Audio and Acoustics Group, and a video of my presentation is in the following <a href="https://www.microsoft.com/en-us/research/video/a-cross-modal-audio-search-engine-based-on-joint-audio-text-embeddings/">link</a>.

<h3>References</h3>
1. Manocha, Pranay, Rohan Badlani, Anurag Kumar, Ankit Shah, Benjamin Elizalde, and Bhiksha Raj. "Content-based representations of audio using siamese neural networks." In 2018 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), pp. 3136-3140. IEEE, 2018.
2. Fan, Jianyu, Eric Nichols, Daniel Tompkins, Ana Elisa Méndez Méndez, Benjamin Elizalde, and Philippe Pasquier. "Multi-Label Sound Event Retrieval Using A Deep Learning-Based Siamese Structure With A Pairwise Presence Matrix." In ICASSP 2020-2020 IEEE International Conference on Acoustics, Speech and Signal Processing (ICASSP), pp. 3482-3486. IEEE, 2020.
3. Elizalde, Benjamin, Ankit Shah, Siddharth Dalmia, Min Hun Lee, Rohan Badlani, Anurag Kumar, Bhiksha Raj, and Ian Lane. "An approach for self-training audio event detectors using web data." In 2017 25th European Signal Processing Conference (EUSIPCO). IEEE, 2017.




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
