## Day 01 - JS DrumKit

An awesome JS DrumKit that can be played from keyboard keys.

Challenge Solution

- data-key attribute is same for audio tag and div showing buttons
- so we get both with querySelector having specific keyCode 
- we add .playing class to active div and then remove it after 0.3 sec with setTimeout function
- we select audio tag with specific keyCode and then play audio with audio.play() method

