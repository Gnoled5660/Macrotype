# Macrotype
<img width="2940" height="1082" alt="Macropad_with_Case_2026-Jun-15_12-51-55PM-000_CustomizedView37122516277_png" src="https://github.com/user-attachments/assets/22f076a1-08fb-456f-b659-dfaa1f1d5323" />

# Description
This is a fully custom wireless hot swappable macropad with a custom Microcontroller. It has a total of nine fully custom programmable keyswitches and a rotary encoder as well as a 0.91 OLED display. It still remains pretty compact, while having that many components. It's size is approximately 10x6.8x1.6cm. There is a LiPo 3.7V Battery built in, but if you want to charge it, you can simply charge the battery via the USB-C receptacle. The macropad has an IC charger built in. If it is connected to the USB-C port, then the nRF52840 MCU chip, will be directly powered by the external power source, while the battery is being charged. However, if it is not connected to an external power supply, then the chip will be powered by the battery.

# Assembling the macropad
It is quite straight forward to assemble everything. As the PCB will be preassembled by JLCPCB, since there are many components that cannot be hand soldered, there is not much to do on the soldering part. It is only necessary to solder the display and the rotary encoder onto the PCB and connect the Battery with the socket. There are four mounting holes on the PCB, that are used to screw screws onto the CAD model. For this project, you only need four M2 screws. It is also recommended to use heated threat inserts, to have a more guarentee more grip.

# Schematic and Components
The main component is the nRF52840, a relatively cheap chip, that is capable of bluetooth low energy. This chip functions as the main processing unit, to handle all the actions that can be done with the board. Another important component is the BQ24074, it is an IC charger that can charge the battery, while still letting power to the MCU. As the battery is a 3.7V LiPo, the voltage always varies between 3.3V and 4.0V. Thats why there is also a Low Dropout Regulator, that convert the voltage to 3.3V.

<img width="847" height="588" alt="Bildschirmfoto 2026-06-15 um 15 30 08" src="https://github.com/user-attachments/assets/6ae6993c-5bdc-4111-82bd-87488bc95a0e" />


# PCB
The PCB is a 4 layer PCB, with the first and fourth layer function as signal transmitting layers. The second layer is a big Ground plane and the third layer is a hybrid layer with signal tracks and Ground planes. The most crucial part of the PCB is the radio frequency part. This part cannot have any tracks or Ground planes above or under it, as any distrubances might change the frequency.

<img width="468" height="339" alt="Bildschirmfoto 2026-06-15 um 15 33 07" src="https://github.com/user-attachments/assets/f9562e6d-4176-45a4-a90c-8130a4bf282f" />


<img width="401" height="558" alt="Bildschirmfoto 2026-06-15 um 15 30 40" src="https://github.com/user-attachments/assets/41fdd68b-ad4e-46ae-9b08-17dd05f2f166" />

# Firmware 
To boot the nRF52840 chip, you have to use a bootloader and connect it physically to the pin sockets on the board. There is a row with the sockets CLK and SWD. Connect it to these rows and flash the Firmware onto it. You can find it in the folder Firmware. Afterwards, you can simply connect the chip via the USB-C port to a computer and upload the uf2 file, which contains all the keyboard settings. The keyboard firmware was built with ZMK.
