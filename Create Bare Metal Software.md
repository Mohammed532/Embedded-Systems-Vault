1. Create workspace in Vitis
	- Can just place in folder of Vivado project
2. Create Platform component
	- Personal naming preference: board_name_project (ei a750t_temp_sensor)
3. Create Application component
4. Add C source file
	- Need to add source file for includes to populate
	- Common file includes
		- xparameters.h: can find device information (gpio or iic baseaddr, device id, etc)
		- xil_printf.h
		- xgpio.h
		- xil_types.h
	- Can also find header definitions under project_platform(ie a750t_temp_sensor) > output > sw > standalone > includes
	- 