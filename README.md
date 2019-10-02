# rBH1750FVI
rBH1750FVI is an open source library for the Digital Ambient Light Sensor BH1750FVI.

This B4R library
* is written in C++ (using the Arduino IDE 1.8.9 and the B4Rh2xml tool).
• is wrapped based on the BH1750FVI project (see credits).
• supports I2C addresses: 0x23 or 0x5C.
• supports various resolution modes. Recommended mode Continuous_H_resolution.
• tested with Digital Ambient Light Sensor model GY-301 BH1750FVI connected to an Arduino MEGA.

[B4R](https://www.b4x.com/b4r.html) development tool for native Arduino and ESP programs by [Anywhere Software](https://www.b4x.com).

## Files
* rBH1750FVI.zip archive contains the library and sample projects.

## Install
From the zip archive, copy the content of the library folder, to the B4R additional libraries folder keeping the folder structure.

## Wiring
```
BH1750FVI = Arduino MEGA
VCC = 3.3v 
GND = GND 
SCL = SCL 
SDA = SDA 
ADDR = A3 - slave device address 0x23
OR
ADDR = Vin - slave device address 0x5C
```

## B4R Example with all Functions
```
Sub Process_Globals
    Public Serial1 As Serial
    Private bh As BH1750FVI
    Private Timer1 As Timer
End Sub

Private Sub AppStart
    Serial1.Initialize(115200)
    Log("AppStart")
    'Init the sensor with low I2C address 0x23 and the recommended high resolution mode
    bh.Initialize(bh.Device_Address_L, bh.Continuous_H_resolution_Mode)
    Timer1.Initialize("Timer1_Tick", 1000)
    Timer1.Enabled = True
End Sub

Sub Timer1_Tick
    Log(bh.LightIntensity, "lx")
End Sub
```

## Credits
* Anywhere Software for providing B4R (and of course the whole B4X suite) [Info](https://www.b4x.com/)
* Genotronex for the Digital Light Sensor BH1750 library [Info](https://github.com/Genotronex/BH1750FVI_Master)
* Friends-of-Fritzing foundation for fritzing [Info](https://fritzing.org)

## Licence
GNU General Public License v3.0.
