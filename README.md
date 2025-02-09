# Mystique-Art
A P5.js script that is used to create some Art using Geometric Shapes Only.

![image](https://github.com/user-attachments/assets/54fb7433-8797-4da9-9125-e7632e244747)

## P5.js script:
``` 
function setup() {
  createCanvas(300, 300);
}

function draw() {
  background(255)
  
  firstStrip(0, 50);
  secondStrip(50, 100);
  thirdStrip(100, 200);
  fourthStrip(200, 300);
  
  strokeWeight(3)
  line(0, 50, width, 50);
  strokeWeight(4)
  line(0, 100, width, 100);
  strokeWeight(4)
  line(92, 200, width, 200);
}

//Goes From 0, 50
function firstStrip(startY, endY){
  
  strokeWeight(2);
  let hatLength = 50;
  let hatCount = width / hatLength;
  let squareShifter = 5;
  
  for(let i = 1; i <= hatCount; i++){
    let endX = i * hatLength;
    let startX = endX - hatLength;
    
    drawHat(startX, endX, startY, startY + 25);
    drawSquare(startX + squareShifter, endX - squareShifter, startY + 10, endY);
  }
    
  function drawHat(minX, maxX, minY, maxY){
    line(minX, maxY, (maxX-minX) / 2 + minX, minY);
    line((maxX-minX) / 2 + minX, minY, maxX, maxY);
  }
    
  function drawSquare(minX, maxX, minY, maxY){
    let midX = (maxX - minX) / 2 + minX;
    let midY = (maxY - minY) / 2 + minY;

    line(minX, midY, midX, minY);
    line(midX, minY, maxX, midY);
    line(maxX, midY, midX, maxY);
    line(midX, maxY, minX, midY);
  }
}

//Goes From 50 to 100
function secondStrip(startY, endY){
  
  let arcDiameter = 100;
  let arcRadius = arcDiameter / 2;
  let arcCount = width / arcDiameter;
  
  drawPattern();
  
  function drawPattern(){
    for(let i = 1; i <= arcCount; i++){
      let arcCentreX = (arcDiameter * i) - arcRadius;
      let arcCentreY = startY;
      
      let triangleFirstPointX = (arcCentreX - arcRadius) + 10;
      let triangleLastPointX = (arcCentreX + arcRadius) - 10;
      
      arc(arcCentreX, arcCentreY, arcDiameter, endY, 0, PI, CHORD);
      
      triangle(triangleFirstPointX, startY, arcCentreX, endY - 10, triangleLastPointX, startY)
    }
  }
}

//Goes From 100 to 200
function thirdStrip(startY, endY){
  
  drawFirstPart();
  drawSecondPart();
  drawThirdPart();
  
  function drawFirstPart(){
    for(let i = 1; i <= 10; i++){
    
      if(i % 2 == 0){
        fill(255)
      }
      else{
        fill(0)
      }
    
      triangle(0 + 10, 150 - 10, 100 - 10, startY + 10, 10 * i, endY - 10)
      triangle(10, startY + 10, 100 - 10, 150 - 10, 100 - (10 * i), endY - 10)
    }
  }
  
  function drawSecondPart(){
    rectMode(CENTER)
    fill(0)
    square(150, 150, 80, 10)
  }
  
  function drawThirdPart(){
    noFill()
    let arcCount = 20;
    for(let i = 0; i < arcCount; i++){
      let percent = (arcCount - i) / arcCount;
      arc(290, endY - 10, (2 * 90) * percent, (160) * percent, PI, 3 * (PI / 2))  ;
      arc(200, endY - 10, (2 * 90) * percent, 160 * percent, 3 * (PI / 2), 2 * PI)
      
    }
  }
}

function fourthStrip(startY, endY){
  
  drawFirstPart();
  drawSecondPart();
  drawThirdPart();
  
  function drawFirstPart(){
    for(let i = 1; i <= 10; i++){
    
      if(i % 2 == 0){
        fill(255)
      }
      else{
        fill(0)
      }
    
      triangle(0 + 10, 150 - 10, 100 - 10, startY + 10, 10 * i, endY - 10)
      triangle(10, startY + 10, 100 - 10, 150 - 10, 100 - (10 * i), endY - 10)
    }
  }
  
  function drawSecondPart(){
    for(let i = 0; i < 11; i++){
      triangle(110 + (i * 7.5), endY - 10, 110  + (i * 7.5), startY + 10 + (i * 2.5), 190 , endY - 10)  
    }
    
    // triangle(115, endY - 10, 115, startY + 15, 190 , endY - 10)
  }
  
  function drawThirdPart(){
    noFill()
    let arcCount = 20;
    
    for(let i = 0; i < arcCount; i++){
      let percent = (arcCount - i) / arcCount;
      arc(290, startY + 10, (2 * 90) * percent, (160) * percent, PI / 2, PI);
      arc(200, startY + 10, (2 * 90) * percent, 160 * percent, 0, PI / 2)
      
    }
  }
  
  strokeWeight(3)
  line(90.5, startY + 9, 290, startY + 9)
  line(190, endY - 10, 190, startY + 9)
}

```

## Link to Sketch:
[https://editor.p5js.org/rsutter/full/VZLVNSO6D](https://editor.p5js.org/map.gamedev.ubi/sketches/8VGtjLTyZ)
