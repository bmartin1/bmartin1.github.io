---
layout: page
title: 1 NELS
description: A Never-Ending Learner of Sounds to hear and understand the Web.
img: /assets/img/NELS_diagram.png
importance: 1
---

Hearing machines that understand sounds like humans do require computational programs that can learn from years of accumulated diverse acoustics. They must use associated knowledge to guide subsequent learning and organize what they hear, learn names for recognizable events, scenes, objects, actions, materials, places, and retrieve sounds by reference to those names. These machines must also continuously improve their hearing competence to encompass all the diversity and scale of the acoustics in the world. The ultimate goals of hearing machines inspired my PhD project called Never-Ending Learner of Sounds (NELS) [1].
<br><br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/NELS_diagram.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    A Never-Ending Learner of Sounds (NELS) to hear and understand the Web.
</div>

NELS aims to continuously hear and understand the Web, automatically learn new knowledge about sounds, organize and index audio content, and make the content available for people to query and recover all kinds of information. In doing this, we must address many challenges, for example, the Web has an unbounded number of sounds, training and evaluating Machine Learning models must deal with recordings that are noisy, unstructured, and unlabeled, we must define what knowledge to learn for sounds, and we must understand how to search for sounds, because describing acoustic phenomena in words is hard. For example, the sound of water is one of the most distinguishable sounds, but how to describe it without using the word water?
<br><br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/NELS_overview.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    A Never-Ending Learner of Sounds (NELS) to hear and understand the Web.
</div>

Broadly speaking, NELS crawls audio from YouTube and indexes it with Sound Event Recognition. I chose YouTube because it’s the largest archive of sounds and it resembles the diverse acoustics of the world. The downloaded audio is segmented and passed to a SER system that,  depending on its posterior probabilities, will either discard the segment or index the segment with one of the pre-defined categories. The indexed segments are made available for search and retrieval through a website ([nels.cs.cmu.edu](nels.cs.cmu.edu)).

In the next project posts I will present research done in the different modules to advance the state of NELS. NELS is inspired by and aimed to emulate two similar and more mature projects at Carnegie Mellon University, the Never-ending Language learner led by Tom Mitchel and the Never-ending Image learner led by Abhinav Gupta [3].

Since its inception in 2016, NELS research has been reported in publications in top venues, has motivated multiple international collaborations, and has been awarded multiple honors. After finishing my PhD in 2020 I left the project.  

<h3>References</h3>
1. Elizalde, Benjamin Martinez. "Never-Ending Learning of Sounds." Diss. Carnegie Mellon University, 2020.
2. Mitchell, Tom, et al. "Never-ending learning." Communications of the ACM 61.5 (2018): 103-115.

<h3>Honors</h3>
1. Won the 2017 Gandhian Young Technological Innovation Award (39/2915 winners).
2. Finalist of the 2018 Qualcomm Innovation Fellowship Competition (30/174 finalists).
3. Third place in 2018 IEEE DCASE’s Making Sense of Sounds Data Challenge (12 teams).
4. Received financial support from Bosch Research in Pittsburgh 2019.
4. Partially supported by funding from the Sense of Wonder Group, and CONACyT.


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
