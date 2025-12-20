# SPI(Serial Peripheral Interface)
1)SPI allows communication between one master and number of slaves.Slave can be EEPROM, Sensor, Display,etc.  
2)SPI uses 4 pins for communication which includes MISO(Matser-In Slave Out), MOSI(Master-Out Slave In), SCK(Serial Clock), 
SS(Slave Select).  
3)MISO used when we transmit in slave mode and recieve in master mode, MOSI works opposite to MISO, both of this are data pins.  
4)SCK is produced by master and goes to slave.If SCK not present no any communication happens.  
5)SS is used to select any one slave for communication.
6)SPI used to gather the sensor data at high frequency.SPI used to do short distance communication.SPI communication is based on shift register.  

---

## SPI Bus
1)SPI allows MCU to communicate using different configurations, depending on device targeted and application requirements.  
2)Different types of communication methods are followed here which includes Full Duplex, Half Duplex, Simplex method.    
3)Full Duplex method is a default configuration and there are two unidirectional lines between MOSI and MISO pins.Here data synchronously shifted on clock edges.  
4)Half Duplex have one single cross connection line used to link shift register of master and slave together.In this with clock edges data is synchronously 
shifted between shift register in transfer direction selected reciprocally by both master and slave.  
5)Simplex method consist of single master/slave application.It is transmit only or recieve only.  
6)Setting is same as Full Duplex.It ignores data on unused input pin.It is considered as GPIO standard pin.  
7)Master is not going to get anything form slave.It is transmit only.

---



