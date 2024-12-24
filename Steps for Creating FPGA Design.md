- Follow the steps in this [github tutorial](https://github.com/viktor-nikolov/MicroBlaze-DDR3-tutorial) (includes ram configuration)
	- Don't forget to include xdc constraint file for board (included in tutorial) and uncomment what components are needed
- Right click on bd and create HDL wrapper
	- Make sure you place wrapper as top design, if there's multiple bd in one project
- Validate design
- Go through Synth-Imp-GB run
	- After Synth run, double check IO ports. Fix any missing port values. Most likely need to uncomment some lines in the constraints file
- After bitstream is created, go to File>Export>Export Hardware. Include bitstream

Can now go and [[Create Bare Metal Software]]
