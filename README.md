# CyberBiology
Artificial evolution

This is a little entertainment project, evolution simulator. Every little cell on screen ("a bot") has its own little neural net.
Bot makes moves based on output layer data, it can produce energy via photosynthesis, attack other bots, move and divide. 
When dividing bot creates a copy of his brain, but there is a chance it will mutate a little in the process. 

## What's new?
+ World is now larger than the screen, use arrow keys to move your camera
+ You can now save entire worlds, including parameters set in Adaptation window!

  You already have a super cool world in "SavedObjects/" directory called the Divers! 
In it bots have to dive to the bottom of the screen to multiply and photosynthesis is only available 
above water, so they dive up and down and evolve! I only saved a small fraction of it because othervise 
the file was too large. But it doesn't matter, they will fill the world quickly.
## Что новго 15.01.2023
Времена года допилены.
Добавлены настройки параметров ботов в интерфейсе, а также параметров сезонов ...
добавлен новый сенсор зрения через клетку и чуть увеличил нейросеть. Что позволило им учиться лазить в лабиринты..
Добавленна папка Distrib тут последний собранный файл для Windows x64 и библиотеки, пока возможно не все, потом добавлю недостающие.
## Screenshots

![Screenshot1](/Screenshots/5.png?raw=true "Screenshot1")
![Screenshot2](/Screenshots/4.png?raw=true "Screenshot2")


## What you need to build it

+ SDL

+ Dear Im GUI

+ ImPlot


## Interface

### Main window
Contains all info about simulation

### Controls
+ Start/Stop button (Pause/unpause)
+ PS reward - how much energy a bot gets with one tick of photosynthesis
+ skip - how many turns you calculate before you draw new frame (set to 0 if you want to render every frame)
+ brush - brush size for mouse actions sich as remove (eraser tool)

### Selection
Info about selected bot, some useful buttons to mess with it

### Display
Rendering method. 
+ Bot natural color (just its color)
+ Bot rations (carnivores red, herbivores green, grey if never ate, blue if eats apples or organics)
+ Energy (yellow = low energy, red = maximum energy)
+ No render means you only compute without rendering, starts to simulate very fast

### Mouse function
Choose what to do with your mouse clicks

### Aditional
Some more windows


## Keyboard

Using keyboard is more handy because interface becomes laggy during simulation

+ "Space" - Start/Pause
+ "Plus sign near numpad" - make 1 step
+ "F1" - Spawn a group of random bots
+ "F2" - Create vertical wall
+ "Numpad 1-4" - Select rendering method
+ "Home" - Set camera at X = 0
+ Arrow keys (left, right) - Move camera
+ "Page Up", "Page Down" - Move camera fast
+ "End" - Find first bot on screen


## How to use Settings file
First of all you need to setup your screen resolution, otherwise you wouldn't see the interface.
After that you change your rendering area width ("FieldRenderCellsWidth") and
world height ("FieldCellsHeight") to match your screen. World can be wider than your render area,
but you have to keep its width divisible by 16 without a remainder, it's needed for multi threading.

All changable parameters are listed in that file.
