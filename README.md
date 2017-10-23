# Arduino_EPaper_2.7
Use E-Paper 2.7 inc. 

Usefull links at 

https://www.waveshare.com/wiki/2.7inch_e-Paper_HAT_(B)   

https://www.waveshare.com/2.7inch-e-paper-hat.htm

https://www.waveshare.com/2.7inch-e-Paper-HAT-B.htm


Image creator  (
https://www.waveshare.com/w/upload/3/36/Image2Lcd.7z

NOTE:
How to display an image

There are two ways to display pictures. One is display directly and other is indirectly.

Display directly: Read the data of pictures with library functions, and decode. Then convert it to arrays and send to module. About how to implement it, you can refer to the python examples of Raspberry Pi. (The C demo doesn’t display pictures directly)

Display indirectly: Converting pictures to relative arrays on PC and save as c file. Then you can use the c file on your project. This chapter we will talk about how to convert a picture to array.

    Open a picture with drawing tool comes with Windows system, create a new image, and set the pixel to 176x264.
    Because this module can only display two gray level (Only black and white), we need to convert picture to monochrome bitmap before converting it to array. That is, File --> BMP picture --> Monochrome Bitmap.

        There are two monochrome bitmap on examples pack, which are used for demonstration (raspberrypi/python/black.bmp and raspberrypi/python/red.bmp). 

    Use Image2Lcd.exe software to generate corresponding array for picture (.c file). Open picture with this software, set the parameters:
        Output data type: C language array
        Scanning mode: vertical scanning
        Output gray: single color (gray level of two)
        Maximum width and height: 176 and 264
        Include the data of Image Header: Don’t check
        Inverse color: Check (Check: the white on image will be inversed to 1, and black is inversed to 0)
    Click “Save”, to generate .c file. Copy the corresponding array into your project, and you can display picture by calling this array.


