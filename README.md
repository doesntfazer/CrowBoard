# Crowboard
![crowboard](https://i.imgur.com/Rg7IYPw.jpg)
 Single Board 34/36 Key Keyboard

Revision 1 of this keyboard is built as followed. 

1. Solder on the diodes. if doing through hole diodes make sure that you do this before soldering in the switches or else you're going to have a very hard time. You will want to put them on the back of the board. This is the side with the large crow on it. You want to make sure that you solder them with the line facing left. Or towards the square pads. There is a diode per switch, so 36 in total.

2. Solder on the Pico. you can surface mount solder this to the board. I recommend putting some solder on one of the corner pads, setting the pico on top, then soldering it into place. You can also use pins if that suits you better. Before soldering the switches, I recommed you test each switch pad using some tweezers.

3. Solder in the switches. Remember, if you got the rev1, it only supports Choc's. If you have the MX version, I highly recommend getting 5 pin MX switches if you are doing PCB mount.

4. put the rubber feet on the bottom of the board. 1 on each corner. 1 on the top middle of the board, and one on the bottom middle of the board.

5. If you purchased a kit from KeyboardDweebs.net, your Pico came pre-flashed. When you plug it into your computer it will show up like a flash drive. You can open the code.py in a notepad and edit the keymap. See [KMK firmware's documentation](https://github.com/KMKfw/kmk_firmware/blob/master/docs/README.md) for more info. If you ordered these for yourself, or just bought the PCB's and sourced your hardware elsewhere, check out the [Keyboard Dweebs Firmware repository](https://github.com/doesntfazer/Keyboard-Dweebs-Firmware-repository/tree/main/KMK/CrowBoard) to get the right firmware. Don't forget to flash your board with [Circuit Python](https://circuitpython.org/board/raspberry_pi_pico/) before you transfer the files over. If you'd rather use QMK, please see the below instructions, and you can disregard anything that has to do with flashing 



QMK Flashing instructions. (If desired, I still recommend KMK at this point)
Please note: This has to be done in a linux enviroment as far as I am aware. I don't believe QMK Msys is supported either. At least in my testing. 
Setting up your build enviroment:
1. Use this to download the repository. git clone --branch feature/raspberry-pi-rp2040-support 
2. cd into qmk_firmware folder
3. See [setting up your build enviromet](https://docs.qmk.fm/#/getting_started_build_tools) to get the prerequisites installed.
4. after that is completed run "make git-submodule"
5. Then you can run  qmk compile -kb crowboard -km default
6. once it is compiled it will show up in the .build folder as crowboard_default.uf2
7. plug in the keyboard while holding the reset button down on the pico
8. It should show up as RPI-RP2 in your file manager
9. Drag and drop the .uf2 file into it. 
10. You're done. Enjoy qmk on an RP2040
