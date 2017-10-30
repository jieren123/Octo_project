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

The main control flow is if-then statement. 
The player can press the letter W to up and lift his arms up, letter S to down and lay down his arms, letter A to left and change his face to left and letter D and change his face to right, also moving by 2 pixels. 
Create a basic main loop and the subroutine is to execute movement. When again is encountered, Chip8 will skip back to the matchong loop and resume from that point.
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

- Parsing 

1.Register map

Chip8 has 16 v-registers, v0-vf, which we will use to store state. In my game, I use righta and rightb to keep track of the right-arrow position.
```
:alias righta v3
:alias rightb v4
```
2.Scope
Scope refers to the visibility of variables.
In chip8, it beigns with colon (:) and end with semi-colon(;)  Move-arrow-right is starting by inserting subroutine calls into main loop.
```
: move-arrow-right
	va := righta
	vb := rightb 
	
	va += 5 
	
	i := arrow-right
	sprite righta rightb 5
	righta := va
	rightb := vb
	i := arrow-right
	sprite righta rightb 5
	sync
;

: main 
	righta := 0
	rightb := 0
	i := arrow-right
	sprite righta rightb 5
	loop 
		move-arrow-right
		#dancing
	again

```
Also anything after the hash symbol (#) is ignored by it.


## Reference 

- [Octo Chip-8](https://github.com/JohnEarnest/Octo) the most accurate Chip-8 reference online.
- [Chip8](http://mattmik.com/chip8.html)
