# IMGD 5010 - Assignment 2
## Ombre Color

For this assignment, you will create a set of instructions and then realize them in p5.js. Your goal is to both create something that is aesthetically interesting to you, and where your audience can potentially see the underlying instructions.

## Deliverables
1. Overview: a traingle-based background that fades from blue blue with a pucture of a bat drawn over it.

    a. Create an ombre background made of triangles. THe traingles should start blue, with each triangle becoming subsequently redder. The ombre should fade left to right then up and down.
 
   b. A bat should be drawn over this background. The bat will have a line of symmetry in the middle, and should be made up of the same triangles that the background is, like triangle-based pixel art.
3. Program
```
function setup() {
  createCanvas(400, 400);
  rect (0, 0, 400, 400);
  n = 10
  
  x1 = -10;
  y1 = 20;
  x2 = 0;
  y2 = 0;
  x3 = 10;
  y3 = 20;
  reflection = true;
  current_color = 250
  
  batListColumn = 
    [4,4,
     5,5,5,5,5,5,5,5,
     6,6,6,6,6,6,6,6,6,6,
     7,7,7,7,7,7,7,7,7,7,7,7,7,7,7,7,7,
     8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,8,
     9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,9,
     10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,10,
     11,11,11,11,11,11,11,11,11,11,11,11,11,
     12,12,12,12,12,
     13
    ]
  batListRow = 
    [8,32,//4
     6,7,8,9,31,32,33,34,//5
     7,8,9,10,18,22,30,31,32,33,//6
     6,7,8,9,10,11,18,19,20,21,22,29,30,31,32,33,34,//7
     6,7,8,9,10,11,12,13,14,19, 20, 21,26,27,28,29,30,31,32,33,34,//8
     9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,//9
     9,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,31,//10
     12,15,16,17,18,19,20,21,22,23,24,25,28,//11
     17,19,20,21,23,//12
     20//13
     ]
  index = 0
  //Grey ombre
  for (let i = 0; i < 20; i += 1) { 
    for (let j = 0; j < 41; j += 1) 
    { 
      let colorFill = random(250)
      if (i==batListColumn[index] && j==batListRow[index])
      {
        fill("black");
        index++;
      }
      else{
      fill(80, current_color-10, current_color); 
      }
      stroke(0, current_color, current_color);
      triangle(x1, y1, x2, y2, x3, y3);
      
      
      x1 = x2
      y1 = y2
      x2 = x3
      y2 = y3
      if (reflection)
        {
          y3 = y3 - 20
          reflection = false
        }
      else
        {
          y3 = y3 + 20
          reflection = true
        }
      x3 = x3 + 10
      current_color = current_color - .29;
      n--;
      fill(255, 255, 0); 
    }
    x1 = -10;
    x2 = 0;
    x3 = 10;
    y1 = y1 + 20;
    y2 = y2 + 20;
    y3 = y3 + 20;
  }
}
```


![image](https://github.com/user-attachments/assets/19eacb62-56d9-4e30-b20d-b3d02d500719)


## Bonus
After this, I wanted to generate a random series of colors that could fade between one another, which I did by using a random to add or subtract 20 from each color every time I called the program, which created my desire result.
![image](https://github.com/user-attachments/assets/6e9c4814-c407-4917-ad98-46e5fa56896c)

Not allowing color 3 to change genertaed more visually pleasing results, as the colors remained within the bounds of just red and green, with blue remaining the same

![image](https://github.com/user-attachments/assets/074c8850-27b4-48ba-856a-3e58b6ee7db0)
![image](https://github.com/user-attachments/assets/5680d95a-f188-41ef-82d1-7e88d0a353b3)



