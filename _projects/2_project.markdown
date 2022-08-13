---
layout: page
title: NELS
description: NELS hears audio from YouTube in DCASE.
img: /assets/img/DCASE_website.jpg
importance: 3
---

<p align="justify">To build NELS, we faced the lack of a standard and public dataset of sound events in Web videos and the lack of state-of-the-art performance on this setup. Hence, I organized the first public large-scale evaluation of Sound Event Recognition on audio from YouTube. The <a href="http://dcase.community/challenge2017/task-large-scale-sound-event-detection">task</a> was part of the 2017 IEEE DCASE challenge, the main event of the field. Three more tasks (unrelated to Web audio) were organized by the audio group at Tampere University. All 4 tasks are detailed in [1], one of the five most cited papers in the field.
</p>
<br>
<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/DCASE_website.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    The <a href="http://dcase.community/challenge2017/task-large-scale-sound-event-detection">DCASE website</a> has the task description, database and participants' performance. The task was co-organized with Dr. Emmanuel Vincent leader of the audio group at INRIA. Ankit Shah was a contributor and maintains the <a href="https://github.com/ankitshah009/Task-4-Large-scale-weakly-supervised-sound-event-detection-for-smart-cars">Github repo</a>.
</div>

<p align="justify">The main task was divided into two sub tasks, tagging and detecting sound events. Subtask A - Tagging consists of assigning a class label to a clip, and Subtask B - Detection consists of also including the timestamps. The metrics were F1 score and segment-based Error Rate respectively. As the baseline system, we provided our NELS Machine Learning algorithm. We chose the topic of smart cars due to its industry relevance and under use of audio in this and other applications in the urban context. For the dataset, we teamed up with Google’s Sound Understanding group to gather 10-second clips from YouTube videos. We selected 17 categories of warning sounds and vehicles and a total of 57,000 clips, which was an order of magnitude larger than the largest dataset of sound events at that time. Examples of sounds include "Train horn", "Air horn Truck horn", "Car alarm", "Car", "Car passing by", "Bus", "Truck", "Motorcycle", "Train".</p>
<br>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/DCASE_pipeline.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
  DCASE 2017 Task 4: Large-scale weakly supervised sound event detection for smart cars. The Recognition task was divided into two subtasks, tagging and detecting sound events.
</div>

<p align="justify">The clips had weakly labeled categories, for example, a 10-second clip containing "Car horn”, will not include its start and end time, nor if it is a single honk, multiple honks or a continuous honking for 10 seconds, other competing sounds may be overlapping like the sound of car braking.</p>

<p align="justify">An analysis of the results from our task (and the three other tasks) is detailed in a journal [2]. The average duration of a sound event based on the strong labels is five seconds, which is 50% of the provided 10-second clips. Hence, the importance of designing methods that address how to use weak labels. We received 34 systems from 9 teams and 25 authors. Most of the systems were based on log-mel spectrogram features and Convolutional Neural Networks and considered the temporal information. Warning sounds reported higher performance than vehicle sounds, this could be explained because the former type is designed to convey an alert message. Examples of best and worst performing Warning sounds and their F1 scores are "Screaming" 91.2% and "Ambulance (siren)" - not recognized by 7 systems and confused with "Emergency vehicle (siren)"; Vehicle sounds are "Train" 85.2%  and "Car passing by" - not recognized by 12 systems and confused with "Car".

<p align="justify">The task we organized included a key element of NELS, large-scale audio analysis of weakly-labeled audio from Web videos, thereby engaging the research community into the challenges of the NELS project. In the process, we collected a dataset to train our recognition systems and compare against the state of the art. </p>


<h3>References</h3>
1. Mesaros, Annamaria, Toni Heittola, Aleksandr Diment, Benjamin Elizalde, Ankit Shah, Emmanuel Vincent, Bhiksha Raj, and Tuomas Virtanen. "DCASE 2017 challenge setup: Tasks, datasets and baseline system." DCASE 2017-Workshop on Detection and Classification of Acoustic Scenes and Events. 2017.
<br>
2. Mesaros, Annamaria, Aleksandr Diment, Benjamin Elizalde, Toni Heittola, Emmanuel Vincent, Bhiksha Raj, and Tuomas Virtanen. "Sound event detection in the DCASE 2017 challenge." IEEE/ACM Transactions on Audio, Speech, and Language Processing 27.6 (2019): 992-1006.
<br>
<br>
Date: Published on Feb 2021 from work done during my PhD between 2015-2020.

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
