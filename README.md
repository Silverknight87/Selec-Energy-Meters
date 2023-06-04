# Selec-Energy-Meters
**Documentation for Selec Energy Meters**

The repo contains User manuals for the EM4M and EM2M meters. These can also be found on the Selec website.

1. Selec EM4M-3P-1C-100A (sw ver 1.01) Note: uses Big Endian  
Note: The Selec EM4M-3P-1C-100A (sw ver 1.00) uses Little Endian instead of big Endian, so the high and low byte need to be swapped depending on the sw version on your meter


The manuals list Modbus read registers to extract Data from the Selec Meters.  

The Repo also contains Node-red flows to read all the modbus registers over serial and extract useful values and send it out via mqtt or other means on nodered. Node-red-Contrib-Modbus Package needs to be pre installed on Nodered to get this working. There are other ways to do the same using python programs or even use a esp microcontroller or arduino to extra data from Modbus devices but i have a PI sitting near the meters and doing varions other stuff including acting as a wifi access point, so using Nodered on a PI was super easy for me also considering my limited programming skills. 

**Requirements: **

Raspberry PI 3B with local installation of Node-Red.  
node-red-contrib-modbus Package   
Rs485 to USD adapter  
Thin wires to connect to RS485 ports on the Selec Meters. (I used 2 cores from an ethernet cable for this connectivity.  
Selec Modbus meter  

![image](https://github.com/Silverknight87/Selec-Energy-Meters/assets/12622121/71862184-e3ef-4d2e-849f-372a27cdf4b6)  

In my case, the Meters have been configured to the following Slave addresses manually via the physical buttons on the meter.  

EM4M-Grid - 1  
EM2M  - 2  
EM4M-Load - 3  
  
 In the nodered flows, the function node after the inject node specifies the address for each Meter for the Modbus Getter node to poll for data from. The modbus getter needs to be configured with the correct serial adapter on the PI that the usb to serial adapter is connected to.   
  
 Baud rate should match the baud rate, stop bits and parity configured on the energy meters.
 
