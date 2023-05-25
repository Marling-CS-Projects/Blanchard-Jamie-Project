# 2.2.1 Cycle 1

## Design

### Objectives

I plan to tidy up the starting point and make it so that sprite files have a transparency effect that activates for any pixel that's (255,0,255). I will then use this to add a sprite for the stage and a character sprite.

* [x] Tidy up the starting point to only include necesarry functions
* [x] Not display any pixel with the colour (255,0,255) to allow sprites to overlap
* [x] Add and display a character's bitmap file
* [ ] Add and display a bitmap file for the stage and background

### Usability Features

* Colour contrast - Especially for early development I need contrasting colours so I can easily identify where each element is. This also makes it more accessable for users.

### Key Variables

| Variable Name | Use                               |
| ------------- | --------------------------------- |
| cSrc          | Colour variable for an rgb colour |
| ScreenWidth   | 1920                              |
| ScreenHeight  | 1080                              |

### Pseudocode

```
procedure do_something
    
end procedure
```

Graphics.cpp

```
static constexpr int ScreenWidth = 1920;
static constexpr int ScreenHeight = 1080;
```

SpriteEffect.h

```
if (cSrc != 16711935) {
		gfx.PutPixel(xDest, yDest, cSrc);
}
```

## Development

### Outcome

### Challenges

I had to identify the specific cSrc for (255,0,255) by using the debugger to find the PutPixel() call for running a sprite and looking for what the cSrc variable was. I also had to decide what was unnecesarry, eventually resulting in the loss of files like Animation.cpp, Animation.h, Bencher.h, Bencher.txt, Character.cpp, Character.h, COMInitializer.cpp and COMInitializer.h so that I was only left with the default ChiliFramework and the ability to add sprites. I also had to remove all calls to those functions in files like Game.cpp and Game.h

## Testing

Evidence for testing

### Tests

| Test | Instructions  | What I expect     | What actually happens | Pass/Fail |
| ---- | ------------- | ----------------- | --------------------- | --------- |
| 1    | Run code      | Thing happens     | As expected           | Pass      |
| 2    | Press buttons | Something happens | As expected           | Pass      |

### Evidence
