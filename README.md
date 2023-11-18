# Cheatsheet

[https://threejs.org/docs/](https://threejs.org/docs/)

# Canvas

---

## Create new canvas

```jsx
//
const canvas = document.querySelector("canvas.webgl");
```

## Create Threejs Scene

```jsx
const scene = new THREE.Scene();
```

# Objects

---

## Create new Objects

```jsx
//Create new Geometry                //W, H, D
const myGeometry = new THREE.BoxGeometry(1, 1, 1);

//Create new Material
const myMaterial = new THREE.MeshBasicMaterial({ color: 0xff0000 });

//Add Geometry and Material together and create a Mesh
const myObject = new THREE.Mesh(myGeometry, myMaterial);

//alternativ clean methode
const myObject = new THREE.Mesh(
  new THREE.BoxGeometry(1, 1, 1),
  new THREE.MeshBasicMaterial({ color: 0xff0000 })
);

//Add mesh to scene
scene.add(myObject);
```

## Create new Group

Groups can be used to set a certain syntax to every object in the group. For example you can apply `myGroup.position.x = 3` and all the objects in this group will move to the right by 3

```jsx
//instatiates new group called "myGroup"
const myGroup = new THREE.Group();
scene.add(myGroup);

//adds "myObject" to the group
myGroup.add(myObject)

```

## Create new Camera

```jsx
//Create new Perspective Camera      //FOV //Width //Height //Near //Far
const myCamera = new THREE.PerspectiveCamera(75, 800 / 600,0.1 ,100);

//Create new Orthographic Camera  //Left //Right //Top //Bottom //Near //Far
const myCamera = new THREE.OrthographicCamera(-1, 1, 1, -1, 0.1, 100);

//Adjust Cameras Position
myCamera.position.z = 3;

//Add camera to scene
scene.add(myCamera);

```

## Create new Axes-Helper

```jsx
																		//Lenght of each stroke
const axesHelper = new THREE.AxesHelper(2);
scene.add(axesHelper);
```

## Adjust position of an Object

```jsx
//Control the different Axes 
myObject.position.x = 0.7
myObject.position.y = -0.6
myObject.position.z = 1

//Alternative 
myObject.position.set(0.7, -0.6, 1);
```

## Adjust rotation of an Object

### Rotation

```jsx
//180° = Math.PI
//90° = Math.PI / 2

//Control the different degrees of every axes
myObject.rotation.y = Math.PI * 0.25;
myObject.rotation.x = Math.PI * 0.25;

//Select which axes gets rotated first
myObject.rotation.reorder("YXZ");
```

## Scale an Object

```jsx
//Scale the different axes of an object
myObject.scale.x = 2;
myObject.scale.y = 0.5;
myObject.scale.z = 0.5;

//Alternative
myObject.scale.set(2, 0.5, 0.5);
```

## Add Object to Canvas

This can be used to add Objects, Cameras, Axes-helper and all sorts of Stuff that is visible on the Canvas.

```jsx
scene.add(myObject);
```

# Scaling

---

# Controls

---

### Import

```jsx
import { OrbitControls } from "three/examples/jsm/controls/OrbitControls.js";
```

## Camera Controls

```jsx
//OrbitControls                   //camera //DomElement
const controls = new OrbitControls(camera, canvas);
```