---
layout: default_post
title: Cracking Google's Creative Lab 5 Application
tags: creative5
summary: "So the other day my boss forwards me this link, saying 'Google wants you to play with their home page as part of a job application.' I open the link and I'm greeted with a doodled Google page, plus some instructions..."
image: /assets/2016-04-14/hero.jpg
---

> By now, I'm pretty sure others have already published their solutions, so I'm not worried about spoiling anything anymore. If you found this but haven't found any of the easter eggs below, this is your last chance to go there and dig a little deeper on your own.

So the other day my boss forwards me this link, saying "Google wants you to play with their home page as part of a job application." I open the link and I'm greeted with a doodled Google page, plus some instructions:

![Creative Lab 5 Home Screen](/assets/2016-04-14/creativelab5-start-screen.jpg)

>... we want to see what you can do with some shapes, a text bar, and a plain white page. Write it, design it, code it, break it.

Sounds interesting! So what exactly can I do with these shapes? Basic controls like move, duplicate and resize are there. I can also move the anchor points and play with their handles to make them round/cornered. I can animate each shape and I have 10 frames to work with, but that feels more like transitions than animations (they're all ease-in & ease-out and I can't adjust the speed). The colors are Google's brand, so it (kind of) makes sense that I can't change any of them.

Or can I?

They're vector shapes on a page. That's probably a `<canvas>`. If that's a canvas, there's a .js file writing to it. Maybe I can work something through the terminal window. Let's check their .js files...


## My Mona Lisa Smile

![Creative Lab 5 js files](/assets/2016-04-14/js-files.jpg)

Oh, what do we have here? `hidden.js`. And inside it we have........:

![Creative Lab 5 Mona Lisa Easter Egg](/assets/2016-04-14/mona-lisa-easter-egg.jpg)

[grining] Oh, OH! What is that? There's a message there. I think I can read it, but let's just regex it and separate the spaces to make sure I don't miss anything:

>YOU NEED TO ADD A CLASS TO THE DOM GET THE SECOND CLASS OF THE ELEMENT WITH THE ID CL5 AND ADD IT TO THE DIV WITH ID=RABBIT

Sure thing! Just have to find the id="cl5" and check the classes therHOLYSHITIT'SHARRYPOTTER!

`<div id="cl5" class="moony turtle wormtail padfood prongs"></div>`

Ok, makes sense. None of the Marauders was a turtle. Actually, I can't recall any important turtle from the HP books. And it makes even more sense to pair the turtle with the rabbit. Should I just copy it? Nah, let's do it through the command prompt...


## Down The Rabbit Hole I Go
This is where the fun actually begins. Worry not: the Marauder intruder will be sent away, but that's further down the road. This is what I found at the prompt:

`helloWorld()!`

`Welcome to the application console.`

`From here you can do a couple of things like change the fill() of specific objects or ALL the objects. Your alterations will be saved as long as you use the functions provided.`

`Click on objects to find out their name and try something like this:
Hilla.fill('Fuchsia')`

Oh, so I CAN change the colors of the shapes. That's a nice first step. And if I'm not mistaken, `helloWorld()` is a function. Maybe if I run it?

`>helloWorld();`

`Thank you, it's polite to say hi back! Because of that I'm going to give you a hint().`

`Try strokeWidth() and strokeColor() to add strokes to shapes.`

Well, thank you for the 3 new functions. Let's see where this leads us:

`>hint();`

`Hints are useful when it comes to solving a puzzle(). Try all.break() or itemName.break() to break shapes into line segments. To rejoin broken shapes use all.join() or itemName.join().`

`>puzzle();`

`You never know what you'll find hidden in a js file.`

Oh, but I do know! Let's do this:

`>document.getElementById('rabbit').className += 'turtle';`

`Gradients make things look weird(), but in a good way.`

`>weird();`

`decode() this: Y3JlYXRpdmVsYWI1LmNvbS9yYWJiaXRob2xl`

`>decode('Y3JlYXRpdmVsYWI1LmNvbS9yYWJiaXRob2xl');`

`Like N64 but better.`

Hmm..... First thing that pops to mind is the actual N64. You know, from Nintendo. So like that, but better... Hmmmm.... PS1...? Nah, Crash can't be better than Goldeneye or Perfect Dark. It's still something to do with that code. Maybe I should decode it again? Maybe I should look into Base64...? Worth the shot!

`Y3JlYXRpdmVsYWI1LmNvbS9yYWJiaXRob2xl = creativelab5.com/rabbithole`

Oh boy, oh boy! 

![Creative Lab 5 Prime Numbers Challenge](/assets/2016-04-14/prime-numbers.jpg)

A quick search lands on <a href="https://projecteuler.net/" target="_blank">project Euler</a>. Question 7 is exactly the one presented by the CL5 team. This is not a tricky question. If anything, it's about computational power for going through the iterations if your code is badly designed. In any case, someone already solved it: 104743. Which returns:

`Nice. Now get back to the website and call activatePen() with your answer.`

`>activatePen(104743);`

`Ok, one last challenge.`

`Call finalTest() with a function of your own that returns the closest Google logo color hex for any hex given.`

`For example, for #FF7BAC, it should return #EA4235. Make sure to accept and return uppercase hex.`

Well, that's an interesting challenge. Let's think about it.


## ♫ R, G, B... Easy as 1, 2, 3... ♫
If we're talking about colors, we're talking about 3 bytes of data (assuming 24-bit colors, as the problem statement suggested), where each byte is used for storing one of 3 channels' (RGB) values (0-255). So it's a 3D array of values. If I want the difference between two colors, I want nothing more than the difference between 2 points in a 3D Euclidean space. The formula for that is a simple expansion of the Pythagoras' theorem:

![Distance in 3D Euclidean Space. Credit: http://www.cosmosportal.org/](/assets/2016-04-14/3d-distance.jpg)

Instead of x, y and z, I'd have (colorGoogleR - inputColorR), (colorGoogleG - inputColorG) and (colorGoogleB - inputColorB). The Google colors can be found on <a href="https://design.google.com/articles/evolving-the-google-identity/" target="_blank">Google's official branding guide</a> from when they redesigned their logo and other major assets. The algorithm is pretty straightforward (Yoda approved it):


![Correct, your line of thought is.](/assets/2016-04-14/color-difference-whiteboard.jpg)

1. store the Google colors R,G and B components into an array, where each row is a color and each column is a channel (`colorsGoogle`);
2. make sure to `upperCase` the input and remove the '#' if it's there;
3. break the input HEX color into 3 separate HEX components, `parseInt` each one and store the results in a vector (`colorWanted`);
4. calculate the difference between `colorWanted` and `colorsGoogle`, storing the result in a vector, with each row relating to a Google color (`diff`);
5. grab the vector's `indexOf` for the `Math.min` value (`indexClosestColor`);
6. `return colorsGoogle[indexClosestColor`].

I built a <a href="http://htmlpreview.github.io/?https://github.com/clapinton/CreativeLab5/blob/master/finalTest/index.html" target="_blank">small testing page</a> and threw some colors at it:

![Testing the color difference script](/assets/2016-04-14/color-difference-tester.jpg)

Looking good, time to go to production!

`Not quite what we're looking for. Try again!`

Hmm.... Something's wrong with my code. But even after testing with even more colors, I couldn't find the issue. I spent some 2 hours thinking about it, drinking some coffee, walking around, listening to music, clearing my mind... and nothing. I decided to go home and take another stab at it after dinner. But as I was showing my wife, I noticed something really stupid:

Google's guide says their red is #EA4335. CL5 says the red is #EA4235. "You have got to be fucking kidding me", I shouted, as my wife proudly demanded a kiss for helping me solve, in 2 minutes, a problem I couldn't solve in 2 hours...

Lo and behold, I finally got it:

`Very impressive. Because you were able to complete all the tasks we've thrown at you, we added the honorary Techno Crab stamp to your cover letter. Now everyone knows you mastered the application console.`

`Well, that’s all we have for you. Let’s see what you can do with those hacks.`

![Look, mom! I'm a Techno Crab!](/assets/2016-04-14/crab-badge.jpg)

"Well, I can write in pretty big letters: MAKE UP YOUR MIND ON THE FREAKING RED HEX CODE."

Anyway.

Now that I'm a crab, let's design something.

<div class="tsuzuku"></div>