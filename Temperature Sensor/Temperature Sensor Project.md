---
aliases:
  - Temperature Sensor
tags:
  - project
  - a7-50t
---
## Synopsis

The purpose of this project is to utilize the temperature sensor on board the A750T to read the temperature and display it on the 7seg display.

## Functionality Report

- C code need to read the sensor data, and display that data onto the 7seg display
- User should also be able to press a button to switch between conversions (C-F-K)

## Components Needed

- Microblaze
- Temp Sensor
- 7seg display
- button

## Process

1. Write HDL for the needed components
	- [[Steps for Creating FPGA Design]]
2. Write bare metal software for reading sensor and button and writing to display
	- [[Reading I2C Temp sensor]]
	- [[Writing to 7seg display]]
	- 
	