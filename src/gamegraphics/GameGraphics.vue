<template>
  <h1>Video Game Graphics: An Introduction</h1>
  <Cube3D />

  <p>
    In this article we will take a short look into the world of programming video game graphics.
    I will talk about what is needed to draw a 3-dimensional cube like the one we see above,
    and afterwards you should be able to understand the source code for the example.
    The full code for this tutorial can be found on github.
  </p>

  <h2>Vertex, vertices</h2>
  <p>
    A point in 3d is called a vertex (plural: vertices)
    A vertex is defined as 3 coordinates: (X, Y, Z)
  </p>

  <h2>Polygons</h2>

  <p>
    - Everything can be drawn using only triangles
    - One triangle is made up of 3 points, or vertices
    - Each point has 3 coordinates (x, y, z)
  </p>

  <h2>Central Processing Unit</h2>
  <p>
    - The CPU is good at doing one complex task at a time
    - Every computer program you write is executed by the CPU, one line at a time
    - This works well for most things... but not for video game graphics
    - Video games need to draw each pixel on the screen many times per second
    - The CPU was too slow to draw pixels one by one
  </p>

  <h2>Graphics Processing Unit</h2>
  <p>
    - The GPU (
    - cpu, ram, gpu and gpu memory
  </p>

  <h2>Buffers</h2>
  <p>
    - A buffer is a chunk of data in the GPU memory
    - This data can describe a list of vertices,
  </p>

  <h2>Textures</h2>
  <p>
  </p>

  <h2>Shader programs</h2>
  <p>
  </p>

  <h2>Vertex shader</h2>
  <p>
  </p>

  <h2>Fragment shader</h2>
  <p>
  </p>

  <h2>Matrix / Matrices</h2>
  <p>
    - A matrix is a short array of numbers that describes a rotation, translation
    - Dont worry about the details, leave that to the gl-matrix library
    - By describing the view position as a matrix we can move through environments
  </p>

  <h2>Canvas Element</h2>
  <p>
  </p>
  <p>
    Web pages are made out of elements for text, tables, images, etc.
    Originally, there was no way to draw triangles and pixels inside the web browser.
    Video games
    For this purpose, the &lt;canvas> element was invented.
    Canvas is like a little screen inside a web page which can be given a width and height in pixels,
    and to which we can draw either 2d or 3d graphics.
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
