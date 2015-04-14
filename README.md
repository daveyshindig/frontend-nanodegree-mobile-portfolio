## Website Performance Optimization portfolio project

My challenge was to optimize this online portfolio for speed. In particular, optimize the critical rendering path and make this page render as quickly as possible by applying the techniques you've picked up in the [Critical Rendering Path course](https://www.udacity.com/course/ud884).

To get started, check out the repository, inspect the code,

### Getting started

Some useful tips to help you get started:

1. Check out the repository
2. To inspect the site on your phone, you can run a local server

  ```bash
  $> cd /path/to/your-project-folder
  $> python -m SimpleHTTPServer 8080
  ```

3. Open a browser and visit localhost:8080
4. Download and install [ngrok](https://ngrok.com/) to make your local server accessible remotely.

  ``` bash
  $> cd /path/to/your-project-folder
  $> ngrok 8080
  ```

______


### Optimization methods

For this project, I've made numerous optimizations:

+ Identified and performed optimizations to achieve a PageSpeed score of 90 on index.html
+ Ensured a consistent framerate of 60 FPS for pizza.html
+ Reduced time to resize pizzas on pizza.html to <5ms
+ Minified of static resources
+ Inlined above-the-fold CSS to eliminate render-blocking
+ Compressed and sized images to reduce bandwidth of index.html access
+ Optimized of JavaScript to eliminate unnecesary computational overhead and slower than necessary DOM access methods

In views/js/main.js:

+ Pulled calculation of constants out of loops so they will not repeatedly calculate upon each loop iteration 
+ Changed all uses of ```querySelectorAll``` to (faster) ```getElementsByClassName```
+ Altered function ```changePizzaSizes(size)``` such that DOM is accessed only once per loop iteration...
+ Eliminated unnecessary/unviewable pizzas from ```addEventListener``` 

In inlined style:

+ Set ```.mover``` to ```backfact-visibility:hidden``` for a CSS transform to reduce repainting time by repainting only the moving pixels