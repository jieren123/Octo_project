Octo
====
- Dance following its arrow

![Dance following its arrow](https://github.com/jieren123/Octo_project/blob/master/gif/dancing_1.gif)
- Free-Dancing

![Dancing~ Dancing~ Dancing~](https://github.com/jieren123/Octo_project/blob/master/gif/dancing_2.gif)

- [Octo](http://johnearnest.github.io/Octo/) is a high-level assembler for the [Chip8](http://mattmik.com/chip8.html) virtual machine, complete with an environment for testing programs. 
- The Chip8 keypad is different from your keyboard as follows:
```
	Chip8 Key   Keyboard
	---------   ---------
	 1 2 3 C     1 2 3 4
	 4 5 6 D     q w e r
	 7 8 9 E     a s d f
	 A 0 B F     z x c v
```
- Control Flow
The main control flow is if-then statement. The subroutine is between the loop and again. 
The player can press the letter W to up and lift his arms up, letter S to down and lay down his arms, letter A to left and change his face to left and letter D and change his face to right, also moving by 2 pixels. 
(Example of Free Dancing)
```
: main	
	i := facing-left 
	v0 := 30
	v1 := 20
	loop
		clear
		sprite v0 v1 12
		v2 := key
		if v2 == 7 then i := facing-left 
		if v2 == 7 then v0 += -2 
		if v2 == 9 then i := facing-right 
		if v2 == 9 then v0 +=  2
		if v2 == 5 then i := facing-up 
		if v2 == 5 then v1 +=  -2
		if v2 == 8 then i := facing-down 
		if v2 == 8 then v1 += 2 

	again
```	
## Reference 

- [Octo Chip-8](https://github.com/JohnEarnest/Octo) the most accurate Chip-8 reference online.
- [Chip8](http://mattmik.com/chip8.html)
