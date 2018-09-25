Below is a skeleton of a typical p5.js sketch

```JavaScript
// setup() executes only once and at the very beginning
// firstly create a full window canvas 
function setup() {
  createCanvas(windowWidth, windowHeight);
}

function draw() {
    // draw() executes over and over once setup() has executed
}

function windowResized() {
  // this function executes everytime the window size changes

  // set the sketch width and height to the windowWidth and windowHeight. This gets rid of the scroll bars.
  resizeCanvas(windowWidth, windowHeight);
}
```