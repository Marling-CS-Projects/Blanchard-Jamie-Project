# 2.2.1 Cycle 1 - Setup of Sprites

## Design

### Objectives

I plan to tidy up the starting point and make it so that sprite files have a transparency effect that activates for any pixel that's (255,0,255). I will then use this to add a sprite for the stage and a character sprite.

* [x] Tidy up the starting point to only include necessary functions
* [x] Not display any pixel with the colour (255,0,255) to allow sprites to overlap
* [x] Add and display a character's bitmap file
* [x] Add and display a bitmap file for the stage and background

### Usability Features

* Colour contrast - Especially for early development I need contrasting colours so I can easily identify where each element is. This also makes it more accessible for users.

### Key Variables

| Variable Name | Use                                      |
| ------------- | ---------------------------------------- |
| cSrc          | Colour variable for an rgb colour        |
| ScreenWidth   | 1920                                     |
| ScreenHeight  | 1080                                     |
| wr            | Stores window variables, such as wr.left |

### Pseudocode

{% code title="Game Loop" %}
```
function Go
    run function graphics.BeginFrame
    run function UpdateModel
    run function ComposeFrame
    run function graphics.EndFrame
```
{% endcode %}

{% code title="ComposeFrame" %}
```
function ComposeFrame
    graphics.DrawSprite(0,0,background)
    graphics.DrawSprite(100,100,character)
```
{% endcode %}

```
function DrawSprite
    for j=0 to character.height
        for i=0 to character.width
            if colour != (255,0,255) then
                PutPixel(x+i, y+j, colour)
```

## Development

### Outcome

I have altered the code to allow a better starting point. Now, I can add sprites with a transparency effect (so sprites can overlap). This was done by not displaying pixels of colour (255,0,255)

{% code title="SpriteEffect.h" %}
```
if (cSrc != 16711935) {
		gfx.PutPixel(xDest, yDest, cSrc);
}
```
{% endcode %}

I also changed the screen resolution so that I have more screen space to work with

{% code title="Graphics.cpp" %}
```
static constexpr int ScreenWidth = 1920;
static constexpr int ScreenHeight = 1080;
```
{% endcode %}

After doing this I also had to position the screen so the window fits on the screen

{% code title="MainWindow.cpp" %}
```
wr.left = 0;
wr.right = Graphics::ScreenWidth + wr.left;
wr.top = 0;
wr.bottom = Graphics::ScreenHeight + wr.top;
```
{% endcode %}

\
The starting point is also tidy enough that I can clearly see what functions perform what action.&#x20;

### Challenges

I had to identify the specific cSrc for (255,0,255). I did this by using the debugger to find the PutPixel() call for running a sprite. After I found that I could see active variables, so see the cSrc variable for the current colour. I also had to decide what was unnecessary, eventually resulting in the loss of files like Animation.cpp, Animation.h, Bencher.h, Bencher.txt, Character.cpp, Character.h, COMInitializer.cpp and COMInitializer.h so that I was only left with the default ChiliFramework and the ability to add sprites. I also had to remove all calls to those functions in files like Game.cpp and Game.h

## Testing

<figure><img src="../.gitbook/assets/image (12).png" alt=""><figcaption><p>Character and stage</p></figcaption></figure>

### Tests

| Test | Instructions | What I expect                       | What actually happens        | Pass/Fail |
| ---- | ------------ | ----------------------------------- | ---------------------------- | --------- |
| 1    | Run code     | The assets to display on the screen | Assets appearing as expected | Pass      |
