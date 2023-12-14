# Final Project
## Project Name: 3D Website
## About My Project
My original plan was to create a 3-minute music video using A-Frame. However, I changed my mind and decided to develop a website in a virtual reality environment instead. On this website, you can access my five different social media accounts or just explore the virtual environment.
## Inspirations
One of the reasons why I changed my plan was that I found it too complex to create an animation timeline in A-frame. I thought it's not the best platform for making a video. A-frame is great for making interactive VR experiences. I found an example work (https://aframe.io/aframe/examples/showcase/link-traversal/) that had three objects linked to other html files. When you click on one, you can access the another VR experiment. I came up that I could use this future to create my website.
## Week1
I started from learning about A-frame in A-Frame School (https://aframe.io/aframe-school/#/). A-Frame is based on top of HTML, so I began by learning the basic structure of HTML. After I acquired the skills to create 3D objects, I learned how to add textures to them. You can use any JPG image files as texturs and add them to any objects. A-Frame also has a visual editor called A-Frame Inspector. It is useful because it allows for a more intuitive approach than coding. However, I usually prefer not to use it because when I tried it, I couldn't get the same results after editing the code as I've seen on the inspector for some reasons. I also learned how to add animation to objects. There are more possibilities if you use JavaScript, DOM APIs, and three,js, but I didn't explore them this time because it seemed like too much work for one month.
## Week2
I continued explore A-Frame School. A-Frame provides the registry (https://aframe.io/aframe-registry/) where you can grab cool components that the community has added to A-Frame. I discovered many useful components there, and some of them are easy to use. However, most of these were posted about 5 years ago, so they only work with old version of A-Frame. I also realized that most information on A-Frame website, including A-Frame School, is for the old 0.5.0 version of A-Frame. I needed to use current 1.5.0 version for my project because old version didn't have the link primitive that is neccesary for linking URLs to objects. I leraned A-Frame based on od version, so I was struggled with the differences between old and new versions.
## Week3
I started creating website this week. I began by collecting assets, useing Poly Haven (https://polyhaven.com/) for free images can be use as textures, and Flickr (https://www.flickr.com/search/?group_id=44671723%40N00&view_all=1&text=) for 360° images. I also used free image editor website PhotoMosh (https://photomosh.com/). I spent a lot of time browsing the A-Frame website a lot to learn more details about material components and animation. 
## Week4
I had a problem building a Website with github, so I went Rachel's office hour, and she fixed the problem foe me. The issue was that I saved my files in wrong place. I added more objects and animation. I used this website (https://htmlcolorcodes.com/) to get HTML color cods. I used to think that only one animation could be applied to a single object. However, I found codes on the A_Frame website that allowed applying two animations to one object. I figured out that putting a number after animation allowed to multiple animations on one object. I used to use entity-component to add more animation, but this was quicker and easier.
## Description
I used cureent 1.5.0 version of A-Frame.
```
<script src="https://aframe.io/releases/1.5.0/aframe.min.js"></script>
```
```
<script>
      AFRAME.registerComponent('navigate-on-click', {
        schema: {
          url: {default: ''}
        },
    
        init: function () {
          var data = this.data;
          var el = this.el;
    
          el.addEventListener('click', function () {
            window.location.href = data.url;
          });
        }
      });        
    </script>
```
I found this code on https://stackoverflow.com/questions/49018866/need-help-creating-links-to-other-web-pages-in-aframe. It allows to go different website when the specific object is clicked.
```
<a-entity animation="property: scale; dir: alternate; dur: 5000; to: 2 2 2; loop: true">
        <!-- Center -->
        <a-torus-knot src="Assets/MOSHED-2023-12-10-18-13-55.jpg" color="#ff8f00" radius="0.8" radius-tubular="0.145" p="2" q="3" position="0 1 -7" handle-events="" material="" geometry=""
                      animation="easing: linear; property: rotation; dur: 30000; to: 0 360 1080; repeat: indefinite; loop: true"
                      navigate-on-click="url: https://soundcloud.com/fumiyakawase?utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing">
        </a-torus-knot>
        <!-- Right 1 -->
        <a-torus-knot src="Assets/MOSHED-2023-12-10-18-13-55.jpg" color="#8bff00" radius="0.8" radius-tubular="0.145" p="2" q="3" position="4 1 -7" handle-events="" material="" geometry=""
                      animation="easing: linear; property: rotation; dur: 30000; to: -1080 0 360; repeat: indefinite; loop: true" 
                      navigate-on-click="url: https://bandcamp.com/kawase">
        </a-torus-knot>
        <!-- Left 1 -->
        <a-torus-knot src="Assets/MOSHED-2023-12-10-18-13-55.jpg" color="#00ffd8" radius="0.8" radius-tubular="0.145" p="2" q="3" position="-4 1 -7" handle-events="" material="" geometry=""
                      animation="easing: linear; property: rotation; dur: 30000; to: 360 -1080 0; repeat: indefinite; loop: true" 
                      navigate-on-click="url: https://www.instagram.com/fumiya_kawase/">
        </a-torus-knot>
         <!-- Left 2 -->
        <a-torus-knot src="Assets/MOSHED-2023-12-10-18-13-55.jpg" color="#ff00d8" radius="0.8" radius-tubular="0.145" p="2" q="3" position="-8 1 -7" handle-events="" material="" geometry=""
                      animation="easing: linear; property: rotation; dur: 30000; to: 360 0 -1080; repeat: indefinite; loop: true"
                      navigate-on-click="url: https://www.mixcloud.com/fumiyakawase/">
        </a-torus-knot>
        <!-- Right 2 -->
        <a-torus-knot src="Assets/MOSHED-2023-12-10-18-13-55.jpg" color="#f7ff00" radius="0.8" radius-tubular="0.145" p="2" q="3" position="8 1 -7" handle-events="" material="" geometry=""
                      animation="easing: linear; property: rotation; dur: 30000; to: 360 0 1080; repeat: indefinite; loop: true"
                      navigate-on-click="url: https://youtube.com/@alcedo7256?si=kYPFNeiatGECPEKy">
        </a-torus-knot>
      </a-entity>
```
I used five torus-knots for five different websites. I applied rotation animation with different values for each, and a small scale animation with same amount on all of them.
```
<!-- Center -->
      <a-entity animation="easing: linear; property: rotation; dur: 5000; to: 3 -2 3; repeat: indefinite; loop: true; dir: alternate">
        <a-text position="0 2.3 -6.5" text="value: SoundCloud; align: center; font: monoid" scale="1.5 1.5 1.5" side="double"
                animation="easing: linear; property: color; dur: 800; from: #00fff7; to: #e1ff00; repeat: indefinite; loop: true; dir: alternate">
          <!-- Box -->
          <a-box position="0 0.1 0" scale="1.6 0.013 0.01"
                 animation="easing: linear; property: scale; dur: 2000; to: -1.5 0 0; repeat: indefinite; loop: true; dir: alternate; delay: 900"
                 animation__2="easing: linear; property: color; dur: 2000; from: #fffd6f; to: #ff7e29; repeat: indefinite; loop: true; dir: alternate"></a-box>
           <!-- Bottom -->
          <a-box position="0 -0.13 0" scale="1.6 0.013 0.01"
                 animation="easing: linear; property: scale; dur: 2000; to: -1.5 0 0; repeat: indefinite; loop: true; dir: alternate; delay: 600"
                 animation__2="easing: linear; property: color; dur: 2000; from: #fffd6f; to: #ff7e29; repeat: indefinite; loop: true; dir: alternate"></a-box>
          <!-- Right -->
          <a-box position="0.8 -0.02 0" scale="0.013 0.23 0.01"
                 animation="easing: linear; property: scale; dur: 2000; to: 0 -1.5 0; repeat: indefinite; loop: true; dir: alternate; delay: 1100"
                 animation__2="easing: linear; property: color; dur: 2000; from: #fffd6f; to: #ff7e29; repeat: indefinite; loop: true; dir: alternate"></a-box>
           <!-- Left -->
          <a-box position="-0.8 -0.02 0" scale="0.013 0.23 0.01"
                 animation="easing: linear; property: scale; dur: 2000; to: 0 -1.5 0; repeat: indefinite; loop: true; dir: alternate; delay: 400"
                 animation__2="easing: linear; property: color; dur: 2000; from: #fffd6f; to: #ff7e29; repeat: indefinite; loop: true; dir: alternate"></a-box>
       </a-text>
      </a-entity>
```
I edited text using A-Frame Inspector and copied the code from it. I used box primitives to put a framed box around text. I added color animation to both.

I made eyeballs by using two sphere primitives like below.
```
<a-sphere position="2 0 0" radius="0.105" color="#f0ff00" side="double">
          <a-sphere position="0 0 0.038" radius="0.075" color="#000000" side="double"></a-sphere> 
</a-sphere>
```
I multiplied it and added rotation animation on both individual eyeballs and entity.
For the boxes around the viewer, I applied three different animations; color, rotation, and scale.
```
<a-box src="Assets/MOSHED-2023-12-10-18-13-55.jpg" position="0 0 0" color="black" 
               animation="property: rotation; to: 0 360 0; repeat: indefinite; dur:5000; easing: linear; loop: true"
               animation__2="easing: linear; property: scale; dur: 2000; to: 1.1 1.1 1.1; repeat: indefinite; loop: true; dir: alternate; delay: 1000"
               animation__3="easing: linear; property: color; dur: 20; from: black; to: #ffffff; repeat: indefinite; loop: true; dir: alternate">
 </a-box>
```

