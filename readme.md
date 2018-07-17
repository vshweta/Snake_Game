#SNAKE GAME
**NAME:** SHWETA VERMA
**CATEGORY:** HTML5,CSS,JAVASCRIPT

_ _ _
**This is a very simple classic snake game created using the Canvas in HTML,CSS used for basic user interface and Javascript code.**
The Important thing to know before start is that our snake is formed by box(square) where each box is made up of 32px.The movement of Snake takes place by removing the tail of the snake and unshift the new head to the front of the snake.

##INSTRUCTIONS


1. Create a Canvas Element In our html.
2. Draw the body of the snake,ground,food and the score.
3. Create the structure of the food and the Snake.
4. Check the check_collision to check if the snake has touched itself or the boundary.
5. Create the main function which has to run everything we need to play.
6. Use the _keycode_ event to move the snake using keyboard controls.
7. To run it on a server. Save the html page as index.php.

##The Snake

###How to Draw the Snake Using Canvas:

```js
function create_snake(){
for( let i = 0; i < snake.length ; i++){
        ctx.fillStyle = ( i == 0 )? "green" : "white";
        ctx.fillRect(snake[i].x,snake[i].y,box,box);
        
        ctx.strokeStyle = "red";
        ctx.strokeRect(snake[i].x,snake[i].y,box,box);
    }
}

```

###The Movement of the Snake:

```js
	function snake_movement(){
     let snakeX = snake[0].x;
    let snakeY = snake[0].y;
    
    // which direction
    if( d == "LEFT") snakeX -= box;
    if( d == "UP") snakeY -= box;
    if( d == "RIGHT") snakeX += box;
    if( d == "DOWN") snakeY += box;
    }
```

##Keyboard Controls

```js
	let d;

document.addEventListener("keydown",direction);

function direction(event){
    let key = event.keyCode;
    if( key == 37 && d != "RIGHT"){
        left.play();
        d = "LEFT";
    }else if(key == 38 && d != "DOWN"){
        d = "UP";
        up.play();
    }else if(key == 39 && d != "LEFT"){
        d = "RIGHT";
        right.play();
    }else if(key == 40 && d != "UP"){
        d = "DOWN";
        down.play();
    }
}

```


##To check Collision

```js
	function collision(head,array){
    for(let i = 0; i < array.length; i++){
        if(head.x == array[i].x && head.y == array[i].y){
            return true;
        }
    }
    return false;
}

```
July 17, 2017 6:40 PM

