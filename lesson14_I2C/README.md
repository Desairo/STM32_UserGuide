# I2C(Inter-Integrated Circuit)
Protocol used to achieve the serial data communication between IC's close to each other.SPI is simpler than I2C.  

---

## I2C Important Information
1)It is dedicated specification designed by NXP.  
2)I2C is used as multi master and the architecture taken care by hardware.  
3)Here acknowledgement is recieved automatic.  
4)It consist of two pins only SDA and SCL.Both this pins are pulled up to +VCC.  
5)It talks to slave based on slave address.It works in half duplex mode.  
6)Here max speed is 4MHZ and slave can make master wait by holding clock down if it's busy.  

---

