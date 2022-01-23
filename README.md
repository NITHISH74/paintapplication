# Web Page for Paint Application

## AIM:

To design a static website for Paint Application using HTML5 canvas.

## DESIGN STEPS:

### Step 1:

Requirement collection.

### Step 2:

Creating the layout using HTML,CSS and canvas.

### Step 3:

Write javascript to capture move events.

### Step 4:

Perform the drawing operation based on the user input.

### Step 5:

Validate the layout in various browsers.

### Step 6:

Validate the HTML code.

### Step 6:

Publish the website in the given URL.

## PROGRAM :


```
<!DOCTYPE html>
<html>
  <head>
    <title>
      Rockstar 2D painter
    </title>
    <link rel="stylesheet" href="./css/layout.css" />
    <link rel="icon" href="./img/download.png" type="image/x-icon" />
  </head>
<body id="content">
    <h1>DRAWING APPLICATION</h1>
    <div id="container">
<canvas id="myCanvas" width="1080" height="1080" onclick="showCoords(event)"></canvas></div>
<center>
<button onclick="shape=1" id="keys" >Solid circle </button>
<button onclick="shape=2" id="keys">Circle</button>
<button onclick="shape=3" id="keys">Solid Square</button>
<button onclick="shape=4" id="keys">Square</button>
<button onclick="shape=5" id="keys">Solid Triangle</button>
<button onclick="shape=6" id="keys">Triangle</button>
<br>
<button onclick="size()" id="keys" >Change size</button></center>
<center>
    <button onclick="using_color(this)" id="colour" style="background: white;"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(255, 72, 72);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(255, 115, 1);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(252, 255, 60);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(94, 255, 45);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(7, 184, 1);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(49, 231,252);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(46, 112, 255);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(213, 76, 255);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(153, 0, 255);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(54, 0, 124);"></button>
    <button onclick="using_color(this)" id="colour" style="background: rgb(0, 0, 0);"></button>
    </center>
<script>
const canvas = document.getElementById("myCanvas");
const ctx = canvas.getContext("2d");
ctx.fillStyle = "#FF0000";
canvas.height = canvas.width;
ctx.transform(1, 0, 0, -1, 0, canvas.height);
let xMax = canvas.height;
let yMax = canvas.width;
let csize= 20;
let sqsize= 50;
let tsize=40;
let words="black";
function size()
{   
if (shape==1 ||shape==2){
    let c= prompt("Please enter size of circle", "Enter you are value");
    csize=c;
} 
if (shape==3 ||shape==4){
    let s = prompt("Please enter size of square", "Enter you are value");
    sqsize=s;
}
if (shape==5 || shape==6){
    let t= prompt("Please enter size of square","Enter you are value");
    tsize=t;
}
}
function using_color(element){
    words=element.style.background;
}
    function showCoords(event)
    {
    var x = event.clientX-915;
    var y = 1195-event.clientY;
    var coords = "X coords: " + x + ", Y coords: " + y;
    document.getElementById("demo").innerHTML = coords;
    
        if (shape==1){
            ctx.beginPath();
            ctx.arc(x, y, csize, 0, 2 * Math.PI);
            ctx.fillStyle=words;
            ctx.fill();
        }
        if (shape==2){
            ctx.beginPath();
            ctx.arc(x, y, csize, 0, 2 * Math.PI);
            ctx.strokeStyle=words;
            ctx.stroke();
        }
        if (shape==3){
            ctx.beginPath();
            ctx.rect(x-(sqsize/2),y-(sqsize/4), sqsize,sqsize);
            ctx.fillStyle=words;
            ctx.fill();
        }
        if (shape==4){
            ctx.beginPath();
            ctx.rect(x-(sqsize/2),y-(sqsize/2), sqsize,sqsize);
            ctx.strokeStyle=words;
            ctx.stroke();
        }
        if (shape==6){
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.lineTo(x-(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x+(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x,y)
            ctx.strokeStyle=words
            ctx.stroke();
        }
        if (shape==5){
            ctx.beginPath();
            ctx.moveTo(x, y);
            ctx.lineTo(x-(tsize/2),y-(tsize*0.86602));
            ctx.lineTo(x+(tsize/2),y-(tsize*0.86602));
            ctx.fillStyle=words
            ctx.fill();
        }
    }
</script>
<center><p id="demo" style="color: rgb(202, 0, 0);"></p></center>

<p style="color: rgb(2, 0, 2); font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, 
Cantarell,'Open Sans', 'Helvetica Neue', sans-serif;" >
</p>
<div class="footer">
  Copyright &#169; 2022 Rockstar 2D painter, Developed by NITHISHWAR S
</div>   
  <style>
h1{
    display: block;
    text-align: center;
   width: 100%;
   height: 40px;
  background-color: #d87523;
   font-style: italic;
  text-align: center;
    color: aqua;
}
center{
    font-size: 15px;

}
button{
    font-size: 30px;
}
#container{
    padding-left: 55em;
}
#myCanvas{
    background-color: #d3c5c5; 
    box-shadow: inset 0 0 5px #000000;
    backdrop-filter: blur(15px);
    border-radius: 10px;
    border: 1px solid #ffffff;
}
.button{
  font-size: 5px;
}
#keys{
    background-color: #eb0c0cc2;
    border: 2px solid rgb(255, 255, 255);
    border-radius: 50px;
    color: white;
    padding: 20px 32px;
    font-style: Garamond;
    text-align: center;
    display: inline-block;
    font-size: 20px;
    margin: 4px 2px;
    cursor: pointer;
}
#keys:hover{
    background-color:#000000;
    transition: 0.1s;
}
#content{
 background:linear-gradient(75deg,blue,violet);
}
.footer {
  display: block;
  width: 100%;
  height: 40px;
  background-color: #e7893b;
  font-size: 22px;
  font-style: italic;
  text-align: center;
  padding-top: 10px;
  margin: 0px 0px 0px 0px;
  color: #75070c;
}
#colour{
         border: 2px solid #ffffff;
        border-radius: 25px;
        padding: 25px 25px;
        text-align: center;
        display: inline-block;
        font-size: 16px;
        margin: 4px 2px;
        cursor: pointer;
        }
#colour:hover{
            opacity: 10%;
            transition: 0.1s;
        }
  </style>  
<div><h2><marquee>Thank For Visiting Our Painting page</marquee</h2></div>
</div>
</body>
</html>
```
## Output:
![image](https://user-images.githubusercontent.com/94164665/150681777-a22a17c1-c9e7-433f-861b-2381000ff4b0.png)
![image](https://user-images.githubusercontent.com/94164665/150681792-9113e666-2e48-413f-a49b-3dd60fa073f6.png)
![image](https://user-images.githubusercontent.com/94164665/150681832-8c053306-1cfb-4494-9274-ba73da191ae4.png)

## Result:

Thus a website is designed and validated for paint application using HTML5 canvas.
