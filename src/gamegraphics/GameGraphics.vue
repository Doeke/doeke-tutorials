<template>
  <h1>Video Game Graphics: An Introduction</h1>
  <Cube3D />

  <p>
    In this article we will take a short look into the world of programming video game graphics.
    I will talk about what is needed to draw a 3-dimensional cube like the one we see above,
    and afterwards you should be able to understand the source code for the example.
    The full code for this tutorial can be found on github:
    <a href="https://github.com/doeke/doeke-tutorials/">github.com/doeke-tutorials/</a>
  </p>

  <h2>Triangles</h2>
  <p>
    In video game graphics, everything you see is actually made out of flat triangles, placed next to each other to give the illusion of complex shapes.
    This means that even the surface of objects like a cube or a sphere are approximated using multiple smaller triangles.
    These triangles are also called polygons, each corner of a polygon is called a vertex (plural: vertices).
  </p>
  <p>
    To position a triangle in 3-dimensional space, we only have to describe the position of each of the three corners in X, Y, Z coordinates.
    Modern video games can create photo-realistic environments made up out of thousands of triangles!
  </p>

  <h2>CPU - Central Processing Unit</h2>
  <p>
    The CPU in a computer is good at executing series of complex tasks, one at a time.
    This is because that is how most computer programs are written,
    every line of code needs to be executed after the previous line has completed.
    This works great for almost anything... but not for video game graphics!
  </p>
  <p>
    For video games, we need to draw our environment, often made out of thousands of triangles,
    to a screen, which can have millions of pixels, and we also need to do this many times per second to create a video-like experience!
    Drawing each pixel with the CPU, one by one, is out of the question, it would be way too slow!
  </p>

  <h2>GPU - Graphics Processing Unit</h2>
  <p>
    To solve this problem, the GPU was invented. Unlike a CPU, the GPU has a great number of smaller cores,
    each capable of drawing polygons and pixels independently of the other cores.
    In other words, they can draw on all the pixels of the screen, at the same time!
  </p>
  <p>
    Great, that's one problem solved, but it created a new problem:
    How does our computer program, which is executed by the CPU, communicate with the GPU inside the computer?
    This is where graphics libraries like WebGL come in, using these we can tell the GPU exactly what we want it to draw.
  </p>

  <h2>Buffers and textures</h2>
  <p>
    All the data that a normal computer program needs to work with, is stored inside computer memory, which is linked to the CPU.
    However, the data that the GPU needs, such as images and information about the triangles,
    needs to be stored inside the GPU's own memory rather than in CPU memory.
    The reason for this again has to do with performance (speed), for the GPU it is much faster to have its own memory chip close by.
  </p>
  <p>
    The downside of this is that triangle and image data will first need to be copied to the GPU memory before we can draw the game.
    This is what happens during video game loading screens, the user has to wait while we copy all this data to the GPU memory!
    Number data like triangle positions are called "buffers" when they're stored in GPU memory, and images like the Vue logo in the example are called "textures".
  </p>

  <h2>Shader programs</h2>
  <p>
    Shader programs are small programs written in a computer language made specifically for the GPU.
    The two main parts of a shader program are called the vertex shader and the fragment shader.
  </p>
  <p>
    The vertex shader tells the GPU where on the screen each corner of every triangle should be placed.
    This changes every time the object that the triangle is a part of moves or rotates,
    and also when the player changes the direction in which they look.
    The fragment shader is responsible for telling the GPU what the final color of each pixel on the screen will be,
    based on the information about the triangle that occupies that place on the screen.
  </p>

  <h2>Canvas Element</h2>
  <p>
    Web pages are made out of elements for text, tables, images, etc.
    It used to be impossible to draw 3-dimensional triangles and pixels from inside the web browser.
  </p>
  <p>
    For this purpose, the &lt;canvas> element was invented.
    The canvas element is like a smaller screen inside a web page which can be given a width and height in pixels,
    and to which we can draw either 2d or 3d graphics.
  </p>

  <h2>Finally</h2>
  <p>
    Thanks for reading! If you have any questions, don't hesitate to ask.
    I had to leave out a lot of details, if there is interest I can make a sequel.
  </p>
  <p>
    The code for the cube example comes from the
    <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_textures_in_WebGL">Mozilla web tutorials</a>,
    an excellent resource for learning!
  </p>
</template>

<script setup lang="ts">
import Cube3D from './Cube3D.vue';
</script>

<style>
</style>
