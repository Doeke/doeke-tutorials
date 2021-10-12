<template>
  <h1>Video Game Graphics: An Introduction</h1>
  <Cube3D />

  <p>
    In this short article we will take a look at the world of programming video game graphics.
    I will talk about what is needed to draw a 3-dimensional cube like the one we see above,
    and afterwards you should have a better understanding of graphics programming.
    The source code for this project, including the spinning cube and this article can be found on github:
    <a href="https://github.com/doeke/doeke-tutorials/">github.com/doeke-tutorials/</a>
  </p>

  <h2>Triangles</h2>
  <p>
    In video game graphics, everything you see is actually made out of flat triangles, placed next to each other to give the illusion of complex shapes.
    This means that even the surface of objects like a cube or a sphere are approximated using multiple smaller triangles.
  </p>
  <img src="/bunnytriangles.jpg" class="image">
  <p>
    These triangles are also called polygons, each corner of a polygon is called a vertex (plural: vertices).
    To position a triangle in 3-dimensional space, we only have to describe the position of each of each vertex in X, Y, Z coordinates.
    The position or color of a vertex is called an attribute of the vertex.
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
  <img src="/architecture_comparison.jpg" class="image">
  <p>
    Great, that's one problem solved, but it created a new problem:
    How does our computer program, which is executed by the CPU, communicate with the GPU inside the computer?
    This is where graphics libraries like WebGL come in, using these we can tell the GPU exactly what we want it to draw.
  </p>

  <h2>Buffers</h2>
  <p>
    All the data that a normal computer program needs to work with, is stored inside computer memory, which is linked to the CPU.
    However, the data that the GPU needs, such as the colors and positions the triangles,
    also needs to be stored inside the GPU's own memory rather than just in CPU memory.
    The reason for this again has to do with performance (speed), it is much faster for the GPU to have its own memory.
  </p>
  <p>
    The downside of this separate memory is that the triangle data will first need to be copied to the GPU memory before we can draw the game.
    This is what happens during video game loading screens, the user has to wait while data for complex environments is copied to the GPU memory!
    Data like triangle colors and positions are stored in arrays called "buffers" inside GPU memory, which need to be created before they can be used.
  </p>

  <h2>Shader programs</h2>
  <p>
    Shader programs are small programs written in a different computer language made specifically for the GPU.
    The two main parts of a shader program are called the vertex shader and the fragment shader.
    We can ignore the other stages in the image below, they happen automatically.
  </p>
  <img src="/pipeline.png" class="image">
  <p>
    The vertex shader tells the GPU where on the screen each corner of every triangle should be placed.
    This changes every time the object that the triangle is a part of moves or rotates,
    and also when the player changes the direction in which they look.
    The fragment shader is responsible for telling the GPU what the final color of each pixel on the screen will be,
    based on the information about the triangle that occupies that place on the screen.
  </p>

  <h2>Canvas Element</h2>
  <p>
    Web pages are made out of simple HTML elements for text, tables, images, etc.
    That's why it used to be impossible to draw 3-dimensional games from inside the web browser.
  </p>
  <p>
    For this purpose, the &lt;canvas> element was invented.
    The canvas element is like a smaller screen inside a web page which can be given a width and height in pixels,
    and to which we can draw either 2d or 3d graphics using WebGL!
    To animate the cube, we execute the render function many times per second using a requestAnimationFrame callback.
  </p>

  <h2>Code</h2>
  <p>
    <a href="https://github.com/Doeke/doeke-tutorials/blob/main/src/cubeCode.ts">You can view the source code for the spinning cube here</a>.
    Hopefully with the information above, the code should be a little easier to understand.
    The source for the cube example originally comes from the
    <a href="https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API/Tutorial/Using_textures_in_WebGL">Mozilla web tutorials</a>,
    an excellent resource for learning more!
  </p>
  <p>
    There is a lot more to talk about (you may notice I skipped matrixes entirely), but I hope this serves as a basic introduction.
    Thanks for reading!
  </p>
</template>

<script setup lang="ts">
import Cube3D from './Cube3D.vue';
</script>

<style>
.image {
  width: 70%;
  margin: 32px auto;
  display: block;
}
</style>
