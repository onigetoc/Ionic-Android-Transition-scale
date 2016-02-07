# Ionic Android Transition scale

Imitate the native Android page transition

I'm trying to imitate the Native Android transition in Ionic.

First i did put the transition to none in the app.js file ionic config

`$ionicConfigProvider.views.transition('none');`

* * *

I find out that when a page come in view it add `nav-bar-direction="back"` or `forward` to `ion-nav-view` 

To make the view Scale up the Android way i did this css.

`.platform-android ion-nav-view [nav-view-direction="forward"] {  
    left: 0;  
    z-index: 2;  
    -webkit-animation: scaleUp .2s ease both;  
    -moz-animation: scaleUp .2s ease both;  
    animation: scaleUp .2s ease both;  
    -webkit-transform: translate3d(0, 0, 0);  
}`

But since i put $ionicConfigProvider.views.transition('none'); to none

the old page is not hidded but removed without a timeout and i can't scale down the Android way.

`.platform-android ion-nav-view [nav-view-direction="back"] {  
    left: 0;  
    z-index: 2;  
    -webkit-animation: scaleDown .2s ease both;  
    -moz-animation: scaleDown .2s ease both;  
    animation: scaleDown .2s ease both;  
}`

* * *

You can fork and help for this project. We may need to hack it with some javascript somewhere to make the scale down work but i down want to touch the core of ionic js file.

At the end of the css code, there's some hidded code to make some test and help to create this Scale down transition.
