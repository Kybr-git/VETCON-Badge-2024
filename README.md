# 2024 VETCON Badge Assembly Instructions



This is the code for the 2024 VETCON Badge.

Functions:

1. GIF Player
2. Puzzle
3. About Screen

## Step 1: Compile and Flash

1. Install Visual Studio Code on your computer (free)
2. Open Visual Studio Code and install the PlatformIO IDE plugin 

![image](https://github.com/user-attachments/assets/01458e41-9ad7-4f2a-a918-1484ab1f5019)

3. Download the firmware from this page as a .zip

![image](https://github.com/user-attachments/assets/ecd72e5b-8424-4fb9-a81e-9e916e193757)


4. Extract all
5. In Visual Studio Code, select the PlatformIO icon and hit the "Open Project" button

![image](https://github.com/user-attachments/assets/b203753b-07ee-4740-a2c7-501e758477a4)

6. Navigate to the extracted folder, inside the Firmware folder, point it at the platformio.ini file
7. Plug the badge's ESP32 into your computer via the usb-c port.  PlatformIO should automatically recognize the badge's ESP32.
8. In PlatformIO, hit the build button (checkmark icon)

![image](https://github.com/user-attachments/assets/04bb9985-9fb0-4736-979d-6df2109658b8)

9. In PlatformIO, hit the upload button (right arrow icon).  That's it - your badge should now flash.  DO NOT UNPLUG DURING FLASH!!!

![image](https://github.com/user-attachments/assets/f357828b-7623-410c-9d59-cb33a187adee)

10. Now that the firmware is flashed we need to configure the SD card.  Plug in your SD card to your computer.
11. IF NEEDED: format the card FAT32
12. Copy all the GIFs from the "GIFs" folder to the root directory of the SD card.  Do NOT create a folder on the card.
13. Insert your SD card into the badge behind the LCD screen.  Make sure you push the card all the way in, the top of the SD card should be roughly flush with the top of the "2024" text.

## Step 2: Solder the power pads
1. On the back side of the badge, there are 2 empty holes under the ESP32 chip.  If you look inside, you should be able to see the two small power pads, one at the bottom of each hole on the inner half.  They are not centered on the hole, this is so you can solder them to the wall of the hole easier.  

![image](https://github.com/user-attachments/assets/eacb89b8-361e-44ed-95ed-ffb2cc8128af)

3. CAREFULLY solder these pads to the wall of the holes.  This is tricky, go slow and make sure the pad gets hot.  You need to make sure the solder gets onto the pad at the bottom, don't just fill the top of the hole with the solder.  If you're struggling with this step, we can solder them for you at next year's con (we planned to do this ourselves at the con, alas, customs had other plans for us).  

4. Insert the battery (the bump goes on the right as you're looking at the battery holder, provided you're not holding it upside-down...)

5. It should power on.  You're done!

## Troubleshooting

If your computer can't connect to the board, then try placing the board into boot mode manually using the VERY small buttons on either side of the USB plug:

1. Hold down the button with a `B` next to it.
2. Hold down the button with a `R` next to it.
3. Release the button with a `R` next to it.
4. Release the button with a `B` next to it.
5. Tell PlatformIO to upload the code
6. Momentarily press the button with a `R` next to it.

## Images for the SD Card

If you want, you can upload your own GIFs to the badge, but you need to format the GIF first.

The GIFs must be in 565RGB Format. See the `ImageConverter` directory for a script.

The GIFs must be in 160x128 format.  There are free resizing tools available online.

The naming convention for the gif file should be: `<ServiceName>##.gif`

Example: `coastguard10.gif`

Service Names for when naming files:

* `coastguard`
* `airforce`
* `navy`
* `marine`
* `army`
* `spaceforce`

IMPORTANT: You must use the next available sequential number in the filename of your GIF (if you see navy01 through navy10 already, name yours "navy11").  Do not skip numbers or you run the risk of crashing the badge if that number is randomly called.
