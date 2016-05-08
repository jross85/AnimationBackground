# Animation Background
demonstration of an animated background on a sign-up page/activity in Android


##Who Says iOS Gets to Have All the Fun? 
It's probably already common knowledge amongst experienced Android Developers, but for those somewhat new (<2 years experience like me), you may not know or not be aware that you can have a nice animated background on a sign up activity like demonstrated below.

![Animated background Android](http://i.imgur.com/5jOp7uo.gif "app")





**NOTE: This may make your apk size big, so be mindful of that.**

##How to Achieve This
*if you decide to try this on your own*

Step 1: Start a New Project in Android Studio, choose whichever Activity you prefer. I chose Empty Activity for this example

Step 2: In your *actvity_main.xml* (or if you're using the blank activty, it will be *content_main.xml), add an ImageView

Step 3: go ahead and give the ImageView these attributes:
```xml
       <ImageView
        android:id="@+id/imageView"
        android:layout_width="match_parent"
        android:scaleType="fitCenter"
        android:layout_height="match_parent" />
```
Step 4: Now this is going to be a little tedious, especially if you are completely new to Android Development, but we're going to have to go old school with animations, like Walt Disney old school. We are going to go grab a royalty free mp4 which you can go to the awesome folks at [Mazwai](http://mazwai.com/) or the community-driven [Videezy](http://www.videezy.com/). Whichever you choose is okay, long as its a video you like. 

Step 5: Take that awesome, royalty-free video you just downloaded and turn it into a gif. My favorite site for this is [Giphy](http://giphy.com/)

Step 6: Okay, now let's go ahead and upload that gif to [gif-maker.me exploder](http://gifmaker.me/exploder/)

Step 7: Dowload the folder with all the gif frames. 

Step 8: If you're still with me, go ahead and use a photo-editing software (for example photoshop or GIMP) to convert the frames you want into PNG files. For the unitiated you're just doing *save as... -> PNG* **Get rid of the dashes in the file name, no dashes and no capital letters as these are all going into the drawable folder** 

Step 9: put all of those *PNG* files in the drawable folder. These are the frames you're working with.

Step 10: create an xml file in your *res folder* (name it something like animatebackground or whichever you'd like) and all the following code: 

```xml 
    <animation-list android:id="@+id/selected"
    android:oneshot="false"
    xmlns:android="http://schemas.android.com/apk/res/android">
    <item android:drawable="@drawable/yourframe1" android:duration="150" />
    <item android:drawable="@drawable/yourframe2" android:duration="150" />
    ...
    
</animation-list>
```
If you look at my file, I've got about 20 frames in mine, you may have more or less

Also, ``` android:oneshot``` is set to false because we want the gif to loop. 

by the way, your frames and your xml file are both in drawable.

Step 11: Now add this logic to your *MainActivity.java* *inside* your ```onCreate``` method:

```java
    // Load the ImageView that will host the animation and
        // set its background to our AnimationDrawable XML resource.
        ImageView img = (ImageView)findViewById(R.id.magicKingdom);
        img.setBackgroundResource(R.drawable.magicplace);

        // Get the background, which has been compiled to an AnimationDrawable object.
        AnimationDrawable frameAnimation = (AnimationDrawable) img.getBackground();

        // Start the animation (looped playback by default).
        frameAnimation.start();
        
  ```
  
  Step 11: Run the application and see a beautiful animated background!
  
  Play around and experiment with this. Add an editText and/or a Textview to it. 
  
  That was a lot of steps for something that seems so simple right? But, that's the beauty of being a developer. If you're totally new, it can seem overwhelming, however, as a wise app developer said: many would-be developers stop at "Hello World". 
  
  All credit goes to [Android Developers Official Documentation](http://developer.android.com/guide/topics/resources/animation-resource.html#View). 
  
  I understand, that this tutorial is literally in the link posted above. However, some people just learn differently, and of course some folks may have never done any type of photo editing and splitting gifs into frames and such. Also, some folks just get intimidated by the official docs (even though they shouldn't).
  
  Anyway, I hope this is helpful to you. Happy coding guys and gals!
