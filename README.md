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

