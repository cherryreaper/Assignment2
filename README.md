# IMGD 5010 - Assignment 2
## Ombre Color

For this assignment, you will create a set of instructions and then realize them in p5.js. Your goal is to both create something that is aesthetically interesting to you, and where your audience can potentially see the underlying instructions.

## Deliverables
1. I would like the program to create a series of triangles that fade from blue to red in an ombre fashion. The triangles should be small and fill the entire screen, each subsequent triangle slighlty redder than the last. In addition, the lines o fthe triagnle will blend in with the blue parts, but become more apparent when fading to red. The ombbre will happen left to right, then up and down.
2. Program
```
function setup() {
  createCanvas(400, 400);
  rect (0, 0, 400, 400);
  n = 10
  
  x1 = -20;
  y1 = 40;
  x2 = 0;
  y2 = 0;
  x3 = 20;
  y3 = 40;
  reflection = true;
  current_color = 250
  for (let i = 0; i < 10; i += 1) { 
    for (let j = 0; j < 21; j += 1) 
    { 
      fill(80, current_color-10, current_color);
      stroke(0, current_color, current_color);
      triangle(x1, y1, x2, y2, x3, y3);
      
      x1 = x2
      y1 = y2
      x2 = x3
      y2 = y3
      if (reflection)
        {
          y3 = y3 - 40
          reflection = false
        }
      else
        {
          y3 = y3 + 40
          reflection = true
        }
      x3 = x3 + 20
      current_color = current_color - 1.2;
      n--;
      fill(255, 255, 0); 
    }
    x1 = -20;
    x2 = 0;
    x3 = 20;
    y1 = y1 + 40;
    y2 = y2 + 40;
    y3 = y3 + 40;
  }
}
```


![image](https://github.com/user-attachments/assets/d00afe5e-dcff-4fa9-8afc-52d493a09c14)

Here is a fun mixed version where the colors of the strokes are a random value between white and black
![image](https://github.com/user-attachments/assets/ef7f4d9a-1d6f-4a3a-af6c-4bef24c5542c)



##Bonus
After this, I wanted to generate a random series of colors that could fade between one another, which I did by using a random to add or subtract 20 from each color every time I called the program, which created my desire result.
![image](https://github.com/user-attachments/assets/6e9c4814-c407-4917-ad98-46e5fa56896c)

Not allowing color 3 to change genertaed more visually pleasing results, as the colors remained within the bounds of just red and green, with blue remaining the same

![image](https://github.com/user-attachments/assets/074c8850-27b4-48ba-856a-3e58b6ee7db0)
![image](https://github.com/user-attachments/assets/5680d95a-f188-41ef-82d1-7e88d0a353b3)



