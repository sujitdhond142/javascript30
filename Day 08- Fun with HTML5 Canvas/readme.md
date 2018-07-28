## Day 08 - Fun with HTML5 Canvas

### Draw on canvas with mouse.

### Challenge Solution

1. Get canvas and set width and height
```
const canvas = document.querySelector('#draw');
canvas.width = window.innerWidth;
canvas.height = window.innerHeight;
```

2. Get and configure canvas context
```
const ctx = canvas.getContext('2d');
ctx.lineJoin = 'round';
ctx.lineCap = 'round';
ctx.lineWidth = 100;
```

3. Set global variables for canvas drawing
```
let isDrawing = false;
let lastX = 0;
let lastY = 0;
let hue = 0;
let direction = true;
```

4. In draw function add following:
    1. Function will run only when mouse is down
    ```
    if(!isDrawing) return;
    ```
    2. Draw line on canvas
    ```
    ctx.beginPath();
    ctx.moveTo(lastX,lastY);
    ctx.lineTo(e.offsetX,e.offsetY);
    ctx.strokeStyle = `hsl(${hue},100%,50%)`;
    ctx.stroke();
    ```
    3. Change width of line according to direction (+/-)
    ```
    if(ctx.lineWidth >= 100 || ctx.lineWidth<=1){
        direction=!direction;
    }
    if(direction){
        ctx.lineWidth++;
    }else{
        ctx.lineWidth--;
    }
    ```
    4. Change hue of stroke
    ```
    if(hue>=360){
        hue=0;
    }
    hue++;
    ```
    5. Set lastX and lastY position to offset position
    ```
    [ lastX, lastY ] = [ e.offsetX, e.offsetY ];
    ```
5. Add event listeners and functions
```
canvas.addEventListener('mousedown', (e) => { 
    isDrawing=true;
    [ lastX, lastY ] = [ e.offsetX, e.offsetY ];
});

canvas.addEventListener('mousemove',draw);
canvas.addEventListener('mouseup', () => isDrawing=false);
canvas.addEventListener('mouseout', () => isDrawing=false);
```
