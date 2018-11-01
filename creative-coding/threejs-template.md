Below is a skeleton of a typical three.js sketch

in js file:
```JavaScript
var app = app || {};

app.controller = {
  /* put animation function here */
  rotationSpeed: 0.05
};

app.init = function(){

  console.log('Hello my universe');
  
  // create a scene
  app.scene = new THREE.Scene();
  app.width = window.innerWidth;
  app.height = window.innerHeight;


  // create a camera
  app.camera = new THREE.PerspectiveCamera(
    60, 
    app.width / app.height,
    0.1,  
    1000  
  );
  /******* 
    4 params:
    * field of view (fov)
    * screen ratio
    * near field: how close to render things
    * far field: how far to render things
  **********/

  // position camera somewhere in the scene, it has a perspective
  app.camera.position.x = -30;
  app.camera.position.y = 40;
  app.camera.position.z = 30;

  // tell the camera where to look at - the center of the scene (0,0,0)
  app.camera.lookAt( app.scene.position );


  /* the renderer calculates how the canvas/browser will see these elements, based on the camera position
  it also defines how it will do the rendering calculation under the hood, i.e. WebGL hardware acceleration or fallback to a software renderer */
  app.renderer = new THREE.WebGLRenderer();


  // set the size
  app.renderer.setSize( app.width, app.height );


  // set the background colour
  app.renderer.setClearColor( 0x0000000 ); //background colour


  /*** Shadows 
  * shadows are computationally expensive, so disabled by default
  app.renderer.shadowMap.enabled = true; 
  app.renderer.shadowMap.type = THREE.PCFSoftShadowMap;
  ***/


  // create the axis
  app.axes = new THREE.AxisHelper(40);
  app.scene.add( app.axes );


  // create an ambient light
  app.ambient = new THREE.AmbientLight( 0x555555 );
  app.scene.add( app.ambient );


  // create a cube
  app.cube = app.createCube(15, 15, 15, 4);
  // using createCube function 
  app.scene.add( app.cube );


  // camera control mouse and keyboard using the library orbitControls.js
  app.controls = new THREE.OrbitControls( app.camera, app.renderer.domElement );


  // dat.gui panel top right corner
  app.gui = new dat.GUI();
  app.gui.add( app.controller, 'rotationSpeed', 0, 0.1 );

  
  // append the rendered canvas onto dom
  document.getElementById("output").appendChild( app.renderer.domElement );
  

  // draw and animate something
  app.animate();


}; // end of app init



// animate function
app.animate = function(){
  /* put animation function here */

  // rotate the cube
  app.cube.rotation.x += app.controller.rotationSpeed;
  app.cube.rotation.y += app.controller.rotationSpeed;
  app.cube.rotation.z += app.controller.rotationSpeed;

  // render
  app.renderer.render( app.scene, app.camera );

  // animate
  requestAnimationFrame( app.animate );

}; // end of app.animate



// createCube functioin
app.createCube = function( x, y, z, size ){
  var cubeGeometry = new THREE.BoxGeometry( size, size, size );
  var cubeMaterial = new THREE.MeshLambertMaterial({
    color: 0xFF8F00,
    wireframe: false
  });

  var cube = new THREE.Mesh( cubeGeometry, cubeMaterial );
  cube.position.set( x, y, z );
  // cube.castShadow = true;

  return cube;
}; // create cube

/* if you want to resize the canvas on window rezise */
app.onResize = function(){
  app.width = window.innerWidth;
  app.height = window.innerHeight;

  app.camera.aspect = app.width / app.height;
  app.camera.updateProjectionMatrix();

  app.renderer.setSize(app.width, app.height);
}
window.addEventListener( "resize", app.onResize, false );
/* resize */



// run app.init when the window is ready
window.onload = app.init;  

```

in html file:
```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>3Universe</title>
  <script src="js/three.js"></script>
  <script src="js/orbitControls.js"></script>
  <script src="js/datGui.js"></script>
  <script src="js/main.js"></script>
  <style>
    body{
      margin:0;
      overflow: hidden;
    }
  </style>
</head>
<body>
  <div id="output"></div>

</body>
</html>

```