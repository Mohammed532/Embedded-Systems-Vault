- Follow the steps in this [github tutorial](https://github.com/viktor-nikolov/MicroBlaze-DDR3-tutorial) (includes ram configuration)
	- Don't forget to include xdc constraint file for board (included in tutorial) and uncomment what components are needed
- Validate design ^37e3c9
	- **Encountered Errors**
		- FREQUENCY MISMATCH: If the frequency between the ram interconnect and the mig aren't matching, that means you need to create a second aclk input signal on the interconnect. connect one to the microblaze clock freq and the other to the mig ui_clk output. ^345f24
- Right click on bd and create HDL wrapper
	- Make sure you place wrapper as top design, if there's multiple bd in one project
- Go through Synth-Imp-GB run
	- After Synth run, double check IO ports. Fix any missing port values. Most likely need to uncomment some lines in the constraints file
- After bitstream is created, go to File>Export>Export Hardware. Include bitstream

Can now go and [[Create Bare Metal Software]]
