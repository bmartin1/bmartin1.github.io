---
layout: page
title: 6 NELS
description: NELS draws domain knowledge from Psychology to enhance the quality of expression of acoustic phenomena.
img: /assets/img/dishwashing.jpg
importance: 6
---

<p align="justify"> To enhance the quality of expression of acoustic phenomena, I studied an interdisciplinary solution that combines Machine Learning and Psychology. Psychology has numerous human studies to determine what are the acoustic properties that listeners consider to perceive and describe sounds. Acoustic properties are mainly derived from three areas, Cognition, Psychomechanics and Psychoacoustics. Inspired by the acoustic properties that were the most successful in listening experiments, we selected categories that could result in Machine Learning models with reliable performance. The new models expand the expressive capabilities of the three NELS modules, crawling audio from the Web, indexing audio content, and searching for audio content. This was the first focused study, to the best of our knowledge, on training Machine Learning models based on acoustic properties. </p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/lim_knowledge.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>    
<div class="caption">
    If we have the above three objects a sponge, a plate and a faucet, what sound do each of them produce in isolation and what sounds do they produce in combination?   
</div>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/dishwashing.jpg' | relative_url }}" alt="" title="example image"/>
    </div>
</div>    
<div class="caption">
    NELS should account for different possible attributes, relations and interactions between the objects by providing different concurrent categorization strategies.    
</div>

<p align="justify">In the previous <a href="https://bmartin1.github.io/projects/5_project/"> project post #5</a> we presented examples of how Machine Learning models in NELS modules have exposed that current categorization limits performance and quality of expression of acoustic phenomena. One example is in the figure above, were we need to define different attributes, interactions, and relations between objects that express the different type o acoustics in isolation and in combination. From the perspective of NELS, categorization and search, is fundamentally a question of human interpretation -- how do people refer to acoustic phenomena and what do people find to be meaningfully similar? The way that people name and refer to sounds is unbounded and signal level similarity can be measured in many ways, at the end of the day these are tasks inherently subjective. <b>Understanding how humans hear is the primary strategy in designing acoustic intelligence [1]. Hence, we need to investigate human perception of sounds from the perspective of Psychology.</b> </p>

<p align="justify">Research in Psychology has established that humans are cognitively flexible enough to compare and categorize sounds in multiple ways within three major areas: Cognition, Psychoacoustics, and Psychomechanics. Different types of acoustic properties are derived from these three areas. Psychology defines a sound as a complex stimulus that encompasses a vast range of acoustic properties [2,3,4]. <b>Listeners perceive acoustic properties and combine them in a holistic manner to recognize sounds.</b> </p>

<p align="justify"> Cognition studies the perception through experience, knowledge and language [2,4]. Psychological experiments have shown that listeners group everyday sounds based more on individual experiences rather than shared "common" knowledge. For example, the loudness or quietness of a city's soundscape is not the same for someone in New York City, USA or in Oaxaca, Mexico; the sound of a car engine can be perceived differently by a regular driver than by a car mechanic; Tokyo inhabitants can recognize the sound of the bullet train, as opposed to people outside Japan. Authors in [5] carried on experiments to evaluate free-categorization of sounds. When participants were provided with audio clips and were asked to classify sounds without any restrictions, non-expert listeners categorize sounds based on source-objects, but expert listeners could identify sources at different levels of abstraction, for example, "electric" vs. "mechanical sources", or "engines" vs. "doors" vs. "alarms".  Machine Learning models inspired by Cognition should look into what acoustic properties can capture experience, context and different levels of abstraction.</p>

<p align="justify">Psychomechanics study the perception of physical characteristics of sound-sources [2]. In the auditory domain, categories are primarily structured based on the sources - object or agents - producing sound - car sounds, baby crying. As mentioned in the last paragraph, authors in [5] shown that non-expert listeners categorize sounds based on source-objects. Gaver argued that listening to everyday sounds focuses more on the physical aspects producing the sound (e.g. actions, interactions, materials) and what they mean in a given context. Machine Learning models inspired by Psychomechanics should look into what acoustic properties can capture the source's physical aspects producing the sound.</p>

<p align="justify"> <b>Authors [1] mentioned that users of automatic systems, for recognition and retrieval, usually complain about not experiencing proper or sufficient categories.</b> An explanation is because there are many possible categorization processes, and the most appropriate categorization depends on the sound, the user, and the context. So, often we need multiple terms to elaborate a description. Elaborated descriptions are essential for search and retrieval of acoustic phenomena, especially when they could not identify the source [2]. The future of such systems lies therefore in accounting for different possible similarities between the sounds, thus being capable of providing different concurrent categorization strategies. Therefore, we need to be able to train Machine Learning models not only on classes defined by source-objects and scenes, but also based on other category types such as sequences, actions, materials, shapes, sizes, cities, attributes and sentiments.</p>

<p align="justify">Psychoacoustics study the perception of sound qualities [2]. Sounds are associated to a subjective perception and adjectives can elicit a subjective meaning to the listener [5,6,7]. Adjectives referring to emotional factors and spectro-temporal components unfolding over time are among the most common wording to categorize sounds after constructions using a noun referring to the source and suffixed nouns derived from verbs referring to the action generation - car passing by [2]. Machine Learning models inspired by Psychoacoustics should look into what acoustic properties can capture the subjective perception of sound attributes.</p>

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/interdisciplinary.png' | relative_url }}" alt="" title="example image"/>
    </div>
</div>    
<div class="caption">
    Psychology defines a sound event as a complex stimulus that encompasses different acoustic properties derived from fields such as Cognition, Psychomechanics and Psychoacoustics.
</div>

<p align="justify">To exemplify the three main areas we use the sounds of a dish washing event illustrated in the figure above. Let's say we are in our house, close to the kitchen, but without the visuals of the kitchen. We can hear the water flow, impact sounds of glass and metal, and scrubbing sounds, thus, from the context and our experience we can infer the event of someone washing something, likely to be dish washing (Cognition). Then, we can recognize the materials involved-- water, glass, metal, and the action of scrubbing (Psychomechanics). Lastly, We can tell if the sounds were loud or quiet, and if the water was flowing continuously or intermittently (Psychoacoustics). The listener's perceive, organize, and combine all these acoustic properties in a holistic manner to determine a dish washing event. We aim to develop a similar approach for NELS, where we can automatically recognize, organize and combine Machine Learning models built on properties for sound event recognition and sound description. The future of systems with Sound Understanding lie in accounting for different possible relations and similarities between sounds, thus being capable of providing models with different concurrent categorization strategies.</p>

<p align="justify">Training Machine Learning models using acoustic properties poses many challenges. There are many, many acoustic properties, so what set of properties should we select for each area, how to collect audio with such labels, and how would Machine Learning models perform. In contrast to Psychology, Sound Analysis has scarce studies on the feasibility and benefits of training Machine Learning models on acoustic properties, and thus, there are no available guidelines. To select acoustic properties inspired by Psychology, we looked into each area and select the types that were the most common and successful for human listeners. We expected that such success will translate into training Machine Learning models with reliable performance. To collect audio labeled with our selection of acoustic properties, we had to define guidelines for different types of collections, such as scraping Web archives, crowd-sourcing, and human experiments. Lastly, once the datasets were available, we needed to test different acoustic features and Machine Learning algorithms to build models that will reliably recognize acoustic properties automatically. I will discuss the studies in each area in the following posts.</p>

<h3>References</h3>
1. Lyon, Richard F. "Machine hearing: An emerging field [exploratory dsp]." IEEE signal processing magazine 27.5 (2010): 131-139.
2. Lemaitre, G., Grimault, N. and Suied, C., 2018. Acoustics and psychoacoustics of sound scenes and events. In Computational Analysis of Sound Scenes and Events (pp. 41-67). Springer, Cham.
3. Lemaitre, G. and Heller, L.M., 2013. Evidence for a basic level in a taxonomy of everyday action sounds. Experimental brain research, 226(2), pp.253-264.
4. Guastavino, C., 2018. Everyday sound categorization. Computational Analysis of Sound Scenes and Events, pp.183-213.
5. Dubois, Danièle. "Categories as acts of meaning: The case of categories in olfaction and audition." Cognitive science quarterly 1, no. 1 (2000): 35-68.
6. Frühholz, S., Trost, W. and Kotz, S.A., 2016. The sound of emotions—Towards a unifying neural network perspective of affective sound processing. Neuroscience & Biobehavioral Reviews, 68, pp.96-110.
7. Ntalampiras, S., 2017. A transfer learning framework for predicting the emotional content of generalized sound events. The Journal of the Acoustical Society of America, 141(3), pp.1694-1701.

Date: Published on June 2021 from work done during my PhD between 2015-2020.


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
