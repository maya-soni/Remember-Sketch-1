let positions = []
let drawings = []
let drawingToDraw = 0

function setup() {
  createCanvas(400, 400);
  background(220)
  noStroke()
  fill('purple')
  noLoop()
}

function draw() {
  
  rect(mouseX,mouseY,20)
}

function mouseMoved() {
  positions.push( {x:mouseX,y:mouseY} )
  redraw()
}

function keyPressed() {
  if( key === 'c' ) {
    background(220)
    positions = []
  }
  
  
  if( key === 'w') {
    for( let w of positions ) {
      // templating string
      console.log( `${w.x},${w.y}`)
    }
  }
  
 
  if( key === 'm' ) {
    background(220)
    drawings.push(positions)
    positions = []
    redraw()    
  } 
  
  
  if( key === 'a' ) {
    drawCurrentDrawing()
  }
  
  
  if( keyIsDown(UP_ARROW) ) {
    drawingToDraw++
    drawCurrentDrawing()
  }
  
  
  if( keyIsDown(DOWN_ARROW) ) {
    drawingToDraw--
    drawCurrentDrawing()
  }
}


function drawCurrentDrawing() {
  if( drawings.length > 0 ) {
    background(220)    
    for( let w of drawings[drawingToDraw%drawings.length] ) {
      rect(w.x, w.y, 20)
    }
    redraw()     
  }
}


let myWriter = createWriter('.js 'csv'); {
    myWriter.print('2025-10-10,2.05'); }
    myWriter.close();
