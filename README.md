CSS Filters
===========

Presenting CSS Filters for Create the Web

Prep Work
---------
If you don't want to be dependent on having an Internet connection during your presentation, I'd recommend you install FilterLab locally.

Head on over to https://github.com/adobe/cssfilterlab and follow the instructions in the README for installing, building and running FilterLab locally. I highly recommend this avenue.

Regardless, even if you decide not to run FilterLab locally, you'll need to be running Google Chrome Canary or WebKit nightly to be able to see the custom filters in action.

Presenting Filters
------------------
Open up the Reveal.js presentation associated with this project (index.html) in Canary or WebKit.

Slide Notes:

HTML5, WebKit & W3C - We are using our expertise, taking features from the likes of Photoshop & Illustrator to add advanced design features to HTML5. To achieve this we are implementing and submitting these features to WebKit.  Then we work with the W3C so that these features can be implemented cross-browser.

Filter Effect Spec constantly being worked on.  Primary contributions in this spec from Adobe, Apple & Opera.

Custom Filters - Filters include standard built-in types such as sepia, drop shadow, color hue, etc.  Or you can use custom shaders, written in the same open laguage as WebGL shaders.

This is just CSS - Click the Burn link and future slide transitions will use the Burn custom shader.  If that's bugging you, you can always go back to default by clicking default on this page.

Vertex Shaders - A 3D mesh is placed over your content.  You specify the resolution of that mesh.  The custom vertex shader is called to transform each vertex mesh point in 3D. Calculations made in the vertex shader can also be passed to the fragment shader.

Vertex Shader Animation - This is just a 2D transformation, but still looks pretty nice.  The image is pushed to the left and right more and more the higher we are on the Y axis.

Fragment Shader - Plasma colors are merged (multiplied) with the existing image using features from the blending & compositing spec.

Page Curl - Mouse over the image to get it to curl.  Lighting is calculated in the vertex shader based on the current transformation, then passed to the fragment shader to apply the appropriate lighting.

FilterLab
---------

FilterLab can be used to design the built-in and custom filters you want to apply to content and can be used to develop and share with others your own custom filters. 


1. First make sure your animation time (bottom right corner) is set to a reasonable number.  I have found that 3 seconds is a right balance that lets people see the animation, but not too slow.

There are built-in filters such as sepia, drop shadow, hue rotation, etc.

2. Add a hue rotation and a drop shadow from the built-in filter list.
	Set the drop shadow's color to blue. 
	Set the hue rotation angle to 0.

Notice that we can copy/paste the resulting CSS (seen under CSS Syntax) in our regular markup.

3. Now click on the little cirle on the right edge of the timeline to advance the timeline to 3s.
	Set the hue rotation angle to 360. 
	Set the drop shadow color to blue.
	Play the animation - notice that the drop shadow stays the same, but everything else has the hue rotation.
	Show the CSS Animation Syntax


That's all well and nice, but let's do something a little more interesting.

4. Delete the 2 built-in filters by clicking on the minus sign in the top-right corner of each filter.

5. Add the curtains filter

6. Set the amount to 0 at time 0 and 1 at 3s and play the animation

7. Add a dissolve filter on top of that and do the same thing with the timing.

But now let's customize the dissolve filter.

8. Delete the dissolve filter.

9. Go to Add Filter->Dissolve and click the 'fork filter' on the right.

You can now click on the various tabs to show the code behind the actual vertex & fragment shaders.

You can also type garbage in to show real-time error handling

10. Go to the fragment shader.  The last line reads:

<code>
css_ColorMatrix = isVisible ? mat4(1.0) : mat4(0.0);
</code>

Select that and paste over it:

<code>
css_MixColor = isVisible ? vec4(1.0) : vec4(1.0, 0.0, 0.0, 1.0);
</code>

If the dissolve filter thinks something should be visible, mix it with white.  Otherwise, mix it with red. very simple.

11. Set the timing on the new dissolve2 filter so that the amount is 0 at 0s and 1 at 3s.  Play the animation.

This is pretty cool.  Let's share it with others.

12.  Click "Publish to Github"
You can share that gist url with others.  They can import it into their own Filter Lab.

In fact, here's a gist you can import into Filter:

13. Delete the existing curtains & dissolve filters

14. Add Filter -> Import via Gist
Paste in this link: https://gist.github.com/3813251

So you can see that  FilterLab can be used to generate the CSS markup for built-in and custom filters and used to develop your own filters and share them with others.


