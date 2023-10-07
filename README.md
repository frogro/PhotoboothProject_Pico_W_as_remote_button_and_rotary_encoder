# Raspberry Pi Pico W as HTTP client: Use of Hardware Buttons and Rotary Encoder
This a Raspberry Pi Pico W CiruitPython code for using the Pico W as a HTTP client in the Photobooth Project of Andreas Blaesius (https://photoboothproject.github.io). You can connect several Buttons or a Rotary Encoder to trigger different actions.

Preparation:

1. Download the latest adafruit_circuitpython_etc.uf2 file and copy it on the CIRCUITPY drive as described here: https://learn.adafruit.com/pico-w-wifi-with-circuitpython/installing-circuitpython
2. Create your settings.toml file including your Photobooth´s AP wifi_ssid and wifi_password as described here: https://learn.adafruit.com/pico-w-wifi-with-circuitpython/create-your-settings-toml-file.
3. Download the latest Adafruit CircuitPython Library Bundle that contains the required CircuitPython libraries for this project. Download the latest 8x.zip file from here: https://github.com/adafruit/Adafruit_CircuitPython_Bundle/releases/
4. Unzip the zip file and copy the following files from the lib folder to the CIRCUITPY lib folder: adafruit_debouncer.mpy, adafruit_requests.mpy, adafruit_ticks.mpy
5. Download the code.py file and copy it to the Pico´s CIRCUITPY folder.
6. Have fun!

<b>Expected behaviour:</b>  
Up to 5 buttons can be used which trigger up to 6 different web requests for start-picture, start-collage, start-custom, start-print, start-video and shutdown-now as descirbed in the documentation: https://photoboothproject.github.io/FAQ#can-i-use-hardware-button-to-take-a-picture. 
There is also LED support for arcarde push buttons, meaning if you use a combined LED button, triggering the button will also light up the LED.
Also a rotary encoder is implemented: It triggers web requests for cw (clockwise) and ccw (counter-clockwise). Pressing the encoder´s push button will trigger a web request for rotary-btn-press. 
Do not forget to define your [Photobooth IP] and [Hardware Button Server Port] below in the code! (Default value for the Hardware Button Server Port is 14711). Button 1 (btn1 on GPIO 10) will do two different actions depending on short or long press: A short press will trigger the web request for the "picture_url", a long press will trigger the web request for the "collage url". 
