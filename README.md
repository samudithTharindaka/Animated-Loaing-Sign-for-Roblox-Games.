# Roblox Loading Panel Animation

## Overview

This project provides an animated loading panel suitable for any Roblox game. Unlike traditional static loading screens, this solution utilizes an animated frame set, allowing for dynamic and engaging loading animations. The scripts are designed using Object-Oriented Programming (OOP) principles to ensure modularity and ease of use.

## Project Structure

The project is organized into one local script and two modular scripts:

1. **Local Script**: Manages the overall loading animation and coordinates the modular scripts.
2. **Modular Scripts**: Includes two classes, `LoadingAnim` and `LetterAnim`, responsible for different aspects of the animation.

## Classes

### 1. `LoadingAnim` Class

The `LoadingAnim` class handles the animation of the loading icon.

- **Constructor**: Takes an object as a parameter to initialize the loading animation.
- **isStop**: A boolean variable used to control the animation loop.
- **Functions**:
  - `start()`: Starts the animation loop.
  - `stop()`: Stops the animation loop.

### 2. `LetterAnim` Class

The `LetterAnim` class manages the animation of the loading text.

- **Constructor**: Takes an object as a parameter to initialize the text animation.
- **Functions**:
  - `start()`: Starts the text animation loop.
  - `stop()`: Stops the text animation loop.

## Local Script

The local script creates instances of the `LoadingAnim` and `LetterAnim` classes and runs them in separate threads. This ensures that both the icon and text animations run simultaneously and smoothly.

## How to Use

1. **Download the Repository**: Download the .rbxl file and get the "status" frame to anywhere you need

## Example Usage
```Lua
local this = script.Parent
local loadingComponents = this.loader:GetChildren()
local load = require(script.LoadingAnim)
local anim = require(script.letterAnimate)

-- Create a coroutine for text animation
local function textAnimationCoroutine(label)
    local newAnime = anim.new(label)
    newAnime:start()
end

-- Start the text animation coroutine
coroutine.wrap(textAnimationCoroutine)(this.label)

-- Start the frame animation immediately
local newload = load.new(this.loader)
newload:start()
   
