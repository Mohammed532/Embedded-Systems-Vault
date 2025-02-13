Also see [[Writing to GPIO devices]] 
Writing to the 8 digit 7seg display on the a750t requires two GPIO connections. One for the common anodes, determining which digit is turned on, the other for the cathodes, which determines which segment to turn on. 

![[Pasted image 20241211130544.png]]
_Page 23 of [Ref Manual](https://digilent.com/reference/_media/reference/programmable-logic/nexys-a7/nexys-a7_rm.pdf)_

Best way of understanding, writing to the bit corresponding to the proper cathode channel turns on the segmant for ALL digits, but only one anode can be turned on at a time.

![[Pasted image 20241211131500.png]]
_7seg Alphabet_

**NOTE!!**: Turns out, writing a 1 turns OFF the segment/anode. That was fun to learn :)))))

### Order of segment bits

Obtained by looking at package pins of the IO ports 
8bits => DP |  CG | CF | CE | CD | CC | CB | CA

### Possible Pseudo Code for writing 'Hello' on display

```c
// assuming max char count for display is 18 (8 digits + 8 decimals + 2 colons)
char display_text[18] = "Hello"

for(int i = 0; i < len(display_text); i++){
	SEVSEG_CATHODE = char_to_binary(display_text[i]);
	SEVSEG_ANODE = binary(i);
	// need logic for controlling decimal point and colon
}

```


## Questions

- How is the decimal point and colon leds controlled? #unanswered
	- The decimal point is controlled by the leftmost bit ([[#Order of segment bits]]). There doesn't seem to be a way to control the colons?
- How to time display? #unanswered