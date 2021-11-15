# Screensaver
This is my screensaver for my creative coding class! I went on a family trip to Paris with my family a couple of years back, and I distinctly remember being in the city at night, surrounded by all of the colorful lights. When I was looking at them, I remember how they all started to blur together, as a mix of the car headlights, neon signs, and fairy lights. I wanted to achieve a similar effect in my screensaver, with lots of circular blurs of color and areas of brightness.  I experimented with multiple components like the speed, size, and color of the circles, and ended up with a result that I felt represented my memory of Paris.



let ballCount = 600;
let x = [];
let y = [];
let xSpeed = [];
let ySpeed = [];
let size = [];
let r = [];
let g = [];
let b = [];
let o = [];

function setup() {
  createCanvas(windowWidth, windowHeight);

  for (let i = 0; i < ballCount; i++) {
    x[i] = width / 8;
    y[i] = height / 8;
    xSpeed[i] = random(-5, 5);
    ySpeed[i] = random(-5, 5);
    size[i] = random(20, 40);
    r[i] = random(256);
    g[i] = random(25);
    b[i] = random(256);
		o[i] = random(100);
  }
}

function draw() {
  background(0, 50);
  
  for (let i = 0; i < ballCount; i++) {

    x[i] = x[i] + xSpeed[i];
    y[i] = y[i] + ySpeed[i];
    
    if (x[i] < 0 || x[i] > width) {
      xSpeed[i] *=-1;
    }

    if (y[i] < 0 || y[i] > height) {
      ySpeed[i] *= -1;
    }

    fill(r[i], g[i], b[i]);

    noStroke();

    ellipse(x[i] * random(1,1.005), y[i] * random(1,1.005), size[i]);
  }
} 
