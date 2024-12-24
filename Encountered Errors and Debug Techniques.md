
### Memory Write Error at 0x80000000000

Accidentally created an infinite for loop that kept shifting a bit value to the left

```C
u8 val = 0b10000000

while (1) {
	for(int i=0; i<8; i++){
			// here was the problem, val never reset, so kept on shifting the bit value
		XGpio_Write(..., val >> i)
	}
}
```

I'm assuming this caused an overrun issue in the ddr2 block ram, since the ram memory block starts at 0x80000000

#### Fix

~~I simply mapped all of the sections in the linker script to the bram block, ran the code again in debug mode, which cleared all of the errors in the registers, and changed the section mapping back to ram.~~

Fix didn't work when error came up again :(

**Note**: When running the code in bram, all of the registers had the same error, im assuming the blaze cpu didnt reset properly between code runs and needed to be cleared before being able to properly run again.

Possible fix: https://medium.com/@caglayandokme/extending-the-memory-limits-of-microblaze-with-an-external-ddr-6c896e75c218


### Frequency Mismatch Between Ram Interconnect and MIG

This error and how to fix is desribed in [[Steps for Creating FPGA Design#^37e3c9]]
![[Steps for Creating FPGA Design#^345f24]]

### Failed to Generate IP 'mig_7series'

Attempted fix: generating block design first then running synthesis