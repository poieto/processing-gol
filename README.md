# processing-gol
In this project we explore the social rules for John Conway's Game of Life - using p5.js and poieto led by Feminist.AI members
<br></br>

## *Processing the Game of Life* - with p5.js and poieto
<br></br>
### I. ABOUT

Here at [Feminist.AI](https://www.feminist.ai/) we run critical education programs around algorithms, artificial intelligence and artificial life. Some of our current programming focuses on algorithmic bias such as our recent *Algorithms of Oppression* book club co-hosted by The Women's Center for Creative Work, in collaboration with The Free Black Women's Library LA. 

In this workshop, *Processing the Game of Life*, we’ll be exploring the social implications of algorithms through the metaphor of John Conway’s *Game of Life*.

We all have different life experiences. Different life experiences can vary across location - consisting of different social constructs and lived experiences. Everybody has different backgrounds and that can affect how people function and what opportunities they have access to.

Today, we'll be using Conway's Game of Life to consider these ideas. Although the [Game of Life](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life) is pretty technical and literal, we’re going to play around with its rules. Let’s consider life as a playing field or a “grid”, where people are given different backgrounds and opportunities - when we “play” the sequence of our lives, we don’t know what will emerge from the starting state of these backgrounds. The Game of Life has a similar setup: we start with a grid that represents squares or cells, and put information into it. These cells can be either “living” or “dead”, and depending on the status of those cells, we don’t know what will emerge once we press play. 

[John Conway](https://www.nytimes.com/2020/04/15/technology/john-horton-conway-dead-coronavirus.html)’s Game of Life is a logic game represented through an animation of moving “cells” on a grid. In today's beginner-friendly workshop, we will introduce to the Game of Life as an entry point for discussing how inequality can affect social outcomes. We’ll provide an animation of the Game of Life implemented in the p5.js editor, and we will all create new social and cultural rules for the game that result in new animated patterns, framing this research with the social design tool poieto. Through these exercises, you’ll gain a critical understanding of the Game of Life and learn how to manipulate video animations with community software [Processing](http://processing.org/).


<br></br>
### II. GOL Technical Approach with Processing / P5.JS *(from [The Coding Train](https://thecodingtrain.com/CodingChallenges/085-the-game-of-life.html)/[Nature of Code](https://natureofcode.com/))*


##### *WHAT ARE CELLULAR AUTOMATA?*

Conway's Game of Life is just one example of a **cellular automata** - aka a simulation of a system of individual "cells". A cellular automata can be represented by "cell" objects, or squares, with [a few key characteristics](https://natureofcode.com/book/chapter-7-cellular-automata/): 
- The cells live on a grid.
- Each cell has a state. Cells can be dead (represented by 0 in the code) or alive (represented by 1).
- Each cell has a "neighborhood" of adjacent cells - aka the surrounding cells on the grid.

![](https://i.imgur.com/vh3M6AY.png)
###### A cell neighborhood, taken from *[The Nature of Code](https://natureofcode.com/book/chapter-7-cellular-automata/)* by Daniel Shiffman

The figure above shows a neighborhood of cells. In this example, the surrounding neighbors are the 8 cells surrounding the circled particular cell. 

Cellular automata can evolve by systematically applying different rule-sets to every cell on the grid. Applied to the whole grid over and over, this can create different patterns of behaviour that we can analyze and manipulate.

These rules allow for patterns to emerge and create copies of themselves on the grid - similar to biological production and evolution. The Game of Life, developed by John Conway in 1970, is the most famous example of what we call cellular automata.


##### *HOW CELLULAR AUTOMATA EVOLVE*

In each generation, we evaluate every individual cell and apply our rules to it to determine whether it's alive (1) or dead (0). Once we're done, we then get a new state based on the previous state, and its neighbors.

In the below examples, alive cells are shown in **black** and dead cells are shown in **white**.

Here are some images of the different generations of our simulation. We aren’t going to get too deep into the code - this is just a high level understanding of what’s happening. 

*The images below are pulled from [The Nature of Code](https://natureofcode.com/book/chapter-7-cellular-automata/) by Daniel Shiffman:*

###### Imagine the neighborhood (image above)laid out on a horizontal line. You can see in figures 7.11 and 7.12  you can see how the neighboring cells produce the 0 and 1 states. 
![](https://i.imgur.com/DUmpy0m.png)

![](https://i.imgur.com/wJXN1tB.png)

###### In figure 7.14 you can see this concept translated into an array (series of numbers).
![](https://i.imgur.com/Bg1JN6f.png)

##### *RULES TO THE GAME OF LIFE*

Here are the 3 basic rules for the Game of Life. As you learn about these - think about new states of the cell. What does it mean to expand your definition of "neighboring cells"?

**Simplified Rules:**
Alive cell = 0; dead = 1.

**How you can die:**
- **Loneliness**: Alive cells less than 2 live neighbors = dies
- **Overpopulation**: Alive cells with more than 3 live neighbors = dies
![](https://i.imgur.com/V7kJOaM.png)

**Come back to life:**
- **Birth**: Dead cells with have 3 live neighbors =  come back to life
![](https://i.imgur.com/pnjAVUU.png)

**Stay the same:**
- **Staying alive**: Live cells with 2 or 3 neighbors =  live
- **Staying dead**: Dead cells with anything other than three live neighbours = stay dead

Applying these rules to a grid, we can see [a few types of behavior patterns](https://camo.githubusercontent.com/a710386de69bcb8577875246196c7fb07144ff0c/68747470733a2f2f6d656469612e67697068792e636f6d2f6d656469612f3456565a547654717a5252304255774e49482f67697068792e676966) emerge among groups of cells. All of them have fun names!

**Still lifes**: These are groups of cells that do not change from one generation to the next. Remember the rules - why do these groups not appear to change? 

Block:
![](https://i.imgur.com/U2YCH7h.png)

Beehive: 
![](https://i.imgur.com/1YcviHv.png)

Loaf:
![](https://i.imgur.com/T5BYtCw.png)

Boat:
![](https://i.imgur.com/FtcnPdf.png)

Tub:
![](https://i.imgur.com/5xX4Mbc.png)

**Oscillators**: These forms switch back and forth between two states, as the cells switch from being alive to dead.

Blinker:
![](https://i.imgur.com/ENMivVP.gif)

Toad:
![](https://i.imgur.com/M2izEs4.gif)

Beacon:
![](https://i.imgur.com/dCsgm4o.gif)

Pulsar:
![](https://i.imgur.com/r53Q1gF.gif)

**Spaceships**: Over multiple generations, the patterns of cell forms appear to "move" around the grid in predictable ways.

Glider: 
![](https://i.imgur.com/wiACf3y.gif)

Spaceships:
![](https://i.imgur.com/bE8njiF.gif)
![](https://i.imgur.com/hBtlO5Z.gif)

##### Images via [Wikipedia](https://en.wikipedia.org/wiki/Conway%27s_Game_of_Life).

Depending on the states of the starting grid, the Game of Life can create beautiful patterns that range from simple and random, to complex and geometric!

<br></br>
### III.GOL / p5.js Technical exercise with Nicci Yin and Hailey Mah.
Now, we'll be looking at an implementation of Conway's Game of Life in a p5.js sketch. p5.js is a free, open-source JavaScript library for creative coding. Sketches can be run and edited right in your web browser - no software downloads needed.

Play around with the code **[in this p5.js sketch](https://p5js.org/examples/simulate-game-of-life.html)**! Together, we'll try changing the canvas size, background color, and activation rules for the neighboring cells. 

**Before we begin:** The default speed of the animation is set to 60 frames per second, which is quite fast! If you want to change the speed of the animation to see what's going on, specify the frame rate by adding`frameRate();` within the `setup()` function.

**1. a) Edit the canvas size**
Think about access to space and how the canvas may affect the duration or spread of active cells or “lives”. Try changing 400 to 800 - or make a tiny 200 x 200 canvas size.
```
  function setup()
      createCanvas(720, 400); 
```

**1. b) Edit the cell size** 
Next, try editing the cell size by changing the value assigned to `w`. What happens if you make `w` bigger? Smaller? How might this be compared to looking at a map? 
```
  function setup()
      createCanvas(720, 400);
      w = 20;                     //the cell size
```
**2. Change your grid color**
Check out [this reference doc](https://p5js.org/reference/#/p5/fill) to find out how to indicate different color values that you can input into `fill()`. Then, [check out this color picker by w3](https://www.w3schools.com/colors/colors_rgb.asp) to select your own color values!
```
function draw() {
  background(255);
  generate();
  for ( let i = 0; i < columns;i++) {
    for ( let j = 0; j < rows;j++) {
      if ((board[i][j] == 1)) fill(0);     //draws alive cells
      else fill(255);                     //draws dead cells
```


**3. Try different neighbors**
Try changing the rules for how the number of neighbors impacts whether a cell is alive or dead. What impact does it have on the behavior of the cells?

```
 if      ((board[x][y] == 1) && (neighbors <  2)) next[x][y] = 0;   //loneliness             
else if ((board[x][y] == 1) && (neighbors >  3)) next[x][y] = 0; //overproduction               
else if ((board[x][y] == 0) && (neighbors == 3)) next[x][y] = 1;  //reproduction               
else     next[x][y] = board[x][y];
```
<br></br>
### IV. GOL / p5.js / poieto exercise with Stephanie Marie Cedeño and Sarah Cheung
Create your own Game of Life metaphor with processing and poieto

**Think about: **

* The states of your cell, your neighbors - what is your metaphor?

* How are our own real-life social conditions informed by those of our neighbours?

* How can differences in our data change our understanding of an experience?


<br></br>
### V. Technical / Learning Info

**Materials Needed**
Computer with internet access and your web browser of choice
Note: We will be using the p5.js web editor, and will be viewing documents on Google Slides and Github.

**Prerequisite Materials**
Optional: Watch an intro video to [Conway’s Game of Life by The Coding Train (Dan Shiffman)] (https://www.youtube.com/watch?v=tENSCEO-LEc)
Optional: Explore the Game of Life section under the Cellular Automata Examples in [The Nature of Code] (https://natureofcode.com/book/chapter-7-cellular-automata/)
Bonus: Watch The Coding Train’s [Coding Challenge for the Game of Life using p5.js!] (https://thecodingtrain.com/CodingChallenges/085-the-game-of-life.html)


**Learning outcomes:**
* Gain an understanding of the rules that constitute Conway’s Game of Life
* Connect the Game of Life to wider conversations around the presence or absence of resources and social conditions
* Learn how different rules for the Game of Life lead to different outcomes, and be empowered to create their own rules
* Learn how to modify an existing Processing sketch and play with code
* Learn how patterns in code can emerge and change based on simple rules

**Goals:** 
* Introduce beginner audiences to the open-source platform Processing
* Help participants visualize social rules and what happens when they are altered
* Make participants comfortable with manipulating video animations in Processing
* Establish a space for safe, open dialogue between participants
* Encourage participants to gain critically engage with ideas of access and inequality
* Encourage participants to explore the relationship between form, culture and code

<br></br>
### VI. Share your work ! 
Feminist.AI will be hosting critical programs and education modules this winter that stem from the ideas in Dr. Safiya Umoja Noble’s book Algorithms of Oppression using the tool to create a Feminist Search Engine, along wiht other Algorithms of Oppression inspired programming. We highly encourage you to join in our future programs, submit their own ideas for programs, or get involved with the Feminist.AI team.

We would love to share your projects! Please give us permission to share your work, e mail a screenshot of your project and/or work to christine@poieto.com

**Social for Feminist.AI:**
website: [feminist.ai](https:/feminist.ai/)
IG:https://www.instagram.com/feministai/
Twitter: https://twitter.com/feminist_ai
FB: https://www.facebook.com/FeministAIProjectsBitsBytes/
If you'd like to volunteer, email social@mutable.studio

**Social for Socio-tech design tool poieto:**
IG: https://www.instagram.com/poi.eto/
Twitter: https://twitter.com/poieto_craft
If you'd like to volunteer, email christine@poieto.com



