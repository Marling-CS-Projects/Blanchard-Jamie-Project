# 2.1 Design Frame

## Systems Diagram

![](https://github.com/Marling-School/alevel-project-template/blob/docs/.gitbook/assets/System%20Diagram.jpg)

<figure><img src="../.gitbook/assets/Computing Diagram.png" alt=""><figcaption></figcaption></figure>

This diagram shows the different parts of the game that I will focus on creating. I have split each section into smaller sub-sections. Throughout the development stage, I will pick one or two of these sections to focus on at a time to gradually build up and piece together the game. I have broken the project down this way as it roughly corresponds to the [success criteria](../analysis/1.5-success-criteria.md). This was done with [computational methods](../analysis/1.4b-computational-methods.md) in mind to make development easier.

## Usability Features

Usability is an important aspect to my game as I want it to be accessible to all. There are 5 key points of usability to create the best user experience that I will be focusing on when developing my project. These are:

### Effective

Users can achieve the goal with completeness and accuracy. To do this, I will make it easy for the players to realise that they need to reach a goal in order to complete a level. I will make this goal clear to see so there is no confusion over where the players need to go.

#### Aims

* Make the controls easy to use but make movement precise
* Clearly display lives and percent so each player can see who's winning

### Efficiency

Efficiency refers to the speed and accuracy to which a user can complete the goal. To do this, I will create a menu system which is easy to navigate through in order for to find what you are looking for. The information which is more important can be found with less clicks.

#### Aims

* Create a menu system that is quick and easy to navigate through
* Create a controls system that isn't too complicated but allows the player to do multiple actions

### Engaging

The solution is engaging for the user to use. To do this, I will build the game around the local multiplayer mode as multiplayer keeps players engaged due to the sense of friendly rivalry and friendship. I will also create 5 characters with unique move sets to allow battles to have more uniqueness per battle. Having a simple art style allows players to understand what's going on, reducing frustration.

#### Aims

* Create a series of characters that players can play as
* Create a local multiplayer and singleplayer mode
* Incorporate a style of game art the suits the game

### Error Tolerant

The solution should have as few errors as possible and if one does occur, it should be able to correct itself. To do this, I will write my code to manage as many different game scenarios as possible so that it will not crash when someone is playing it.

#### Aims

* The game doesn't crash
* The game does not contain any bugs that damage the user experience

### Easy To Learn

The solution should be easy to use and not be over complicated. To do this, I will create simple controls for the game. I will make sure that no more controls are added than are needed in order to keep them as simple as possible for the players.

#### Aims

* Create a list of controls for the game
* Create a display in the pause menu that shows player controls

## Pseudocode for the Game

### Pseudocode for game

This is the basic layout of the object to store the details of the game. This will be what is rendered as it will inherit all important code for the scenes.

```
object Game
    function BeginFrame()
    function UpdateModel()
    function ComposeFrame()
    function EndFrame()
end object

compile game to exe file
```

### Pseudocode for a level

This shows the basic layout of code for a Phaser scene. It shows where each task will be executed.

```
class Level extends Phaser Scene

    procedure preload
        load all sprites and music
    end procedure
    
    procedure create
        start music
        draw background
        create players
        create platforms
        create puzzle elements
        create enemies
        create obstacles
        create finishing position
        create key bindings
    end procedure
    
    procedure update
        handle key presses
        move player
        move interactable objects
        update animations
        check if player at exit
    end procedure
    
end class
```
