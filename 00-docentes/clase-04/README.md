# clase-04

demostración de que sin arreglos la vida es muy dura

```javascript
// quiero hacer cinco elipses
// esas elipses quiero que partan
// en lugares aleatorios
// y que despues se muevan
// aleatoriamente por el lienzo

let posX0;
let posY0;

let posX1;
let posY1;


function setup() {
  createCanvas(400, 400);
  
  posX0 = random(0, 400);
  posY0 = random(0, 400);
  
  posX1 = random(0, 400);
  posY1 = random(0, 400);
  
}

function draw() {

  background(220);
  
  ellipse(posX0, posY0, 80, 80);
  ellipse(posX1, posY1, 40, 40);
  
  posX0 = posX0 + random(-2, 2);
  posY0 = posY0 + random(-2, 2);
  
  posX1 = posX1 + random(-2, 2);
  posY1 = posY1 + random(-2, 2);
  
}
```

ahora con arreglos

```javascript
// quiero hacer cinco elipses
// esas elipses quiero que partan
// en lugares aleatorios
// y que despues se muevan
// aleatoriamente por el lienzo

let numElipses = 5;

// posX y posY son arreglos vacios
let posX = [];
let posY = [];


function setup() {
  createCanvas(400, 400);
  
  // creo condiciones iniciales
  // para posX y posY de todas las elipses
  for (let i = 0; i < numElipses; i++) {
    posX.push(random(0, 400));
    posY.push(random(0, 400));
  }
  
}

function draw() {

  background(220);
  
  // dibuja las elipses
  for (let i = 0; i < numElipses; i++) {
    ellipse(posX[i], posY[i], 80, 80);
  }
  
  // actualizar coordenadas
  for (let i = 0; i < numElipses; i++) {
    posX[i] = posX[i] + random(-2, 2);
    posY[i] = posY[i] + random(-2, 2);
  }



  // SUGERENCIA JULIO: FILL
    
 
  
  //posX1 = posX1 + random(-2, 2);
  //posY1 = posY1 + random(-2, 2);
  
}
```

ahora con arreglos y con colores distintos para cada elipse

```javascript
// quiero hacer cinco elipses
// esas elipses quiero que partan
// en lugares aleatorios
// y que despues se muevan
// aleatoriamente por el lienzo
// quiero que cada elipse tenga un color
// aleatorio y que se mantenga en el tiempo

let numElipses = 5;

// posX y posY son arreglos vacios
let posX = [];
let posY = [];

// rojo, verde, azul son arreglos vacios
let rojo = [];
let verde = [];
let azul = [];

function setup() {
  
  createCanvas(400, 400);
  
  // condiciones iniciales
  
  // para posX y posY de todas las elipses
  // para colores iniciales
  for (let i = 0; i < numElipses; i++) {
    posX.push(random(0, 400));
    posY.push(random(0, 400));
    
    rojo.push(random(0, 255));
    verde.push(random(0, 255));
    azul.push(random(0, 255));
  }
  
}

function draw() {

  background(0);
  
  // dibuja las elipses
  for (let i = 0; i < numElipses; i++) {
    // SUGERENCIA JULIO: fill de colores
    noStroke();
    fill(rojo[i], verde[i], azul[i]);
    ellipse(posX[i], posY[i], 80, 80);
  }
  
  // actualizar coordenadas
  for (let i = 0; i < numElipses; i++) {
    posX[i] = posX[i] + random(-2, 2);
    posY[i] = posY[i] + random(-2, 2);
  }
  
}
```

bodypose

<https://editor.p5js.org/montoyamoraga/full/upAlkmyeR>
