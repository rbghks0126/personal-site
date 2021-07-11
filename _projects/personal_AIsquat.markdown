---
layout: page
title: ai fitness trainer
description: AI fitness trainer that counts your reps (squat only for now) real-time from your webcam.
img: /assets/img/personal_aifitness.jpg
# redirect: https://github.com/rbghks0126/Melbourne-house-price
importance: 0.9
category: personal
---

<a href="https://mystifying-shannon-a5735f.netlify.app/">Here's a link to my fitness trainer!</a> You just need to click the 'start' button and allow your camera to turn on.

This AI Fitness Trainer processes real-time video input from your web-cam and counts the number of squats (planning to add other moves too) you do. 

Google's low-code web-based machine learning platform <a href="https://teachablemachine.withgoogle.com/">Teachable Machine</a> was used to train the model. In the back-end of Teachable Machine is their light-weight mobile-first  pretrained neural network 'MobileNet'. Transfer learning is used so that providing class definitions and video examples of each class completes the training.


For squat, I defined 3 classes for 'stand', 'squat', and 'bent'. See some example snapshots below.

<div class="row">
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/personal_AIsquat_stand2.PNG' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/personal_AIsquat_squat2.PNG' | relative_url }}" alt="" title="example image"/>
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <img class="img-fluid rounded z-depth-1" src="{{ '/assets/img/personal_AIsquat_bent2.PNG' | relative_url }}" alt="" title="example image"/>
    </div>
</div>
<div class="caption">
    From left to right, examples of classes Stand, Squat and Bent.
</div>

And that's it, such video examples of different classes is all you really need to train the model using Teachable Machine. After waiting 5 minutes or so for training, you are provided with the code snippet that allows you to easily export the model to Javascript via Tensorflow.js. At this point, the program is already able to give probability values for the different actions from web-cam video input by connecting to localhost.

To breathe some life into our fitness trainer, I decided to give it a voice so that it can correct you when your pose is wrong (i.e. 'Bent') and also counts out loud the number of squats you make. I used <a href="https://developers.kakao.com">KaKao's speech synthesis API</a> to synthesize the necessary voice recordings. Then, I used Javascript to make the fitness trainer play out certain voice recordings in certain situations. 

Finally, I deployed my fitness trainer on the web using <a href="https://app.netlify.com/">Netlify</a>. 

