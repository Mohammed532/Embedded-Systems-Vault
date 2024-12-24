Also see [[Create Bare Metal Software]] for C template
### Definitions

```C
// DEFINITIONS
#define DEVICE_ADDR BASEADDR_FROM_XPARAM
#define DEVICE_CHANNEL 1_or_2
#define DEVICE_MASK 0b0000
```

### Initialization

```C
int main(){
	// device initialization
	XGpio device;
	XGpio_Config *cfg_ptr;
	
	cfg_ptr = XGpio_LookupConfig(DEVICE_ADDR);
	XGpio_CfgInitialize(&device, cfg_ptr, cfg_ptr->BaseAddress);

	//Set device mode (Input)
	XGpio_SetDataDirection(&device, DEVICE_CHANNEL, DEVICE_MASK);

	//Set device mode (Output)
	XGpio_SetDataDirection(&device, DEVICE_CHANNEL, 0);

	. . .
	
}
```

### Common Functions
```C
int main(){
	. . .

	// read binary value of device
	u32 device_val = XGpio_DiscreteRead(&device, DEVICE_CHANNEL);

	// write binary value to device
	XGpio_DiscreteWrite(&device, DEVICE_CHANNEL, device_val)
}
```


### Notes

In regards to the device mask, the mask value determine which ones should be r/w enabled (1:yes, 0:no)