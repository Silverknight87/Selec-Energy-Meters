# Selec-Energy-Meters
Documentation for Selec Energy Meters

The repo contains User manuals for the following

1. Selec EM4M-3P-1C-100A (sw ver 1.01) Big Endian 
2. Selec EM4M-3P-1C-100A (sw ver 1.00) Little Endian
3. Select EM2M-1P-1C-100A

The manuals list Modbus read registers to extract Data from the Selec Meters.

The Repo also contains Node-red flows to read all the modbus registers over serial and extract useful values and send it out via mqtt or other means on nodered. There are other ways to do the same using python programs or even use a esp microcontroller or arduino to extra data from Modbus devices but i have a PI sitting near the meters and doing varions other stuff including acting as a wifi access point, so using Nodered on a PI was super easy for me also considering my limited programming skills. 

Requirements:
Raspberry PI 3B with local installation of Node-Red.
Rs485 to USD adapter
Thin wires to connect to RS485 ports on the Selec Meters. (I used 2 cores from an ethernet cable for this connectivity. 

![image](https://github.com/Silverknight87/Selec-Energy-Meters/assets/12622121/71862184-e3ef-4d2e-849f-372a27cdf4b6)



