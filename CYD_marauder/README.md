<p>CHEAP YELLOW DISPLAY PROJECT ESP32-2432S028</p>
<p>Cheap Yellow Display hacked to be Li Powered with power button, charger, enlarged case and minimal soldering. Most of my projects start out rough and then I refine compromises.</p>
<ul>
    <li>Li Charger Board from Amazon with Micro USB charging going through a micro usb breakout board I had.</li>
    <li>Cool lock switch (power button) that I had laying around.</li>
    <li>2 pin cables to remove my bad solder jobs</li>
    <li>1100 mah Li Battery from Amazon</li>
    <li>Cheap Yellow Display - Resistive Touch for now</li>
    <li>3d Printed case that I modified for the button, battery and board while keeping the original size aspects. Its just a bit deeper. USB ports on the end are opened up to allow greater cable use.</li>
    <li>Marauder loaded via web flash tool - I will modify this to use the capacitive display as soon as I test it on my bench.</li>
</ul>
<p>&nbsp;</p>
<p>
<img src="https://github.com/bryanshellpuppy/arduinohacks/blob/main/CYD_marauder/Images/power_supply_design.png?raw=true" height="902" width="1155"><br>&nbsp;</p>

ALLWAYS CHECK YOUR POLARITY. Boards, cables, and devices do not follow a standard and you will cook stuff if your not careful.

Purchase: (Links are provided using my Affiliate account. This provides a few pennies when you buy the product from Amazon. I do not promote specific products for greater commission.)

<p>Qty 1    Cheap Yellow Display ESP32-2432S028 Resistive Display (2.8") <a href="https://amzn.to/3TCveyI">Amazon Affiliate Link</a></p>
<p>Qty 1    USB to Lipo charge circuit board <a href="https://amzn.to/3ZBCbUG">Affiliate Link</a></p>
<p>QTY 1    1100MAH LI Battery (Small to fit in case)<a href="https://amzn.to/3BbIl3Q">Affiliate Link</a></p>
<p>Qty 1    Power Button <a href="https://amzn.to/3XSu0C7">Affiliate Link</a></p>
<p>Qty 1    Micro USB Female breakout board (Either 90 degree or standard)<a href=https://amzn.to/4eBf7Ka">Affiliate Link</a></p>
<p>Qty 1    2 pin Female battery cable with connector (or solder directly to the board <a href="https://amzn.to/47DUniv">Affiliate Link</a></p>
<p>Qty 1    4 pin cable provided with the cheap yellow display, you can buy separately or directly solder.</p>
<p>&nbsp;</p>
<p>Optional for External Antenna Upgrade</p>
<p>Qty 1    f.ul to SMA cable for a wifi antenna <a href="https://amzn.to/3zuX7lw">Affiliate Link</a></p>
<p>Qty 1    male f.ul solder on connector (if you want external antenna) <a href="https://amzn.to/4eCqgud">Affiliate Link</a></p>
<p>Qty 1    Wifi SMA antenna - Male SMA <a href="https://amzn.to/3XUViYL">Affiliate Link</a></p>

Building the Charge Power Circuit:
<p>&nbsp;</p>
First layout your parts. Solder the batter connector to the 
<span class="auto-style1">[1]</span>BAT + and <span class="auto-style1">[2]</span> -. Do not hookup power to the board until completely done just in case of an error. Polarity is important.
<p>
<img src="https://raw.githubusercontent.com/bryanshellpuppy/arduinohacks/refs/heads/main/CYD_marauder/Images/IMG_3851-2.png" height="841" width="824"></p>
Solder the device power cable (4-pin) positive to one side of the lock switch 
<span class="auto-style1">[5]</span>(power button) solder a red wire from the power button to the + out on the board. This will cut the power when button is unlocked. Solder the black 
<span class="auto-style1">[7]</span> Neg wire from the (4-pin) cable to the - out of the battery charge board.
<p>&nbsp;</p>
Solder the + side next to the USB port <span class="auto-style1">[3]</span> on the board or + IN to a red wire, then solder it to the V+ 
<span class="auto-style1">[3]</span> on the micro USB breakout board. Solder a black wire to the - IN pad 
<span class="auto-style1">[4]</span> next to the micro USB port on the charge board. Then solder the other end to the V- 
<span class="auto-style1">[4]</span> on the micro USB board. This will allow a micro USB cable to charge the battery even if the switch is off.
<p>&nbsp;</p>
Connect the battery to the female connector using the correct polarity. To test charge, plug in a micro USB cable to the new port soldered to IN + / IN - and you should see a red light (charging) illuminate on the board. If everything is working correctly, the board is now sending power to the battery and monitoring the charge. Now you can hook up the power 4-pin cable to the P5 port on the CYD. Its next to the onboard micro USB, and the optional USB-c port at the bottom of the board.
<p>&nbsp;</p>
Once connected, if a red light on the back of the display does not illuminate, press the yellow power button. This should cause the display to boot up into a test application, unless you have already flashed it with Marauder 1.0.0.
<p>&nbsp;</p>
After all the testing is complete you can affix the board, battery and power button in the 3d-printed case. If you have chosen to use an External WIFI antenna (Advanced users only) then you will want to follow the instructions on scraping the traces and adding a f.ul port to the ESP32 board. This is very tedious work and the parts are VERY small. I melted several of the connectors before I got the hang of it so be careful.<br>
<p>&nbsp;</p>
If you want to add the External WIFI antenna, you can do it a few different 
ways. All are more advanced and I am not showing you how but giving you some 
references if you want to attempt it. You could brick your device or destroy the 
WIFI on the board.<p>&nbsp;</p>
&nbsp;<p>One way is to hard wire the antenna wire, such as this person did:
<a href="https://community.home-assistant.io/t/how-to-add-an-external-antenna-to-an-esp-board/131601">
https://community.home-assistant.io/t/how-to-add-an-external-antenna-to-an-esp-board/131601</a></p>
<p>Another way it to solder an SMA connector to the board:
<a href="https://www.youtube.com/watch?app=desktop&amp;v=-8hxk81H6QI">
https://www.youtube.com/watch?app=desktop&amp;v=-8hxk81H6QI</a></p>
<p>&nbsp;</p>
<p>I did something that I have done on a Pi Zero 2, I scraped the trace and 
scraped away the trace between + and - of the antenna. Then I carefully soldered 
on a u.fl connector, burning my hands a lot. There is only one way this can go 
on, its very hard to get it just right and I would recommend against it unless 
you know what your doing. You need a tiny solder tip on a very accurate solder 
station or you will burn or melt something. <br>This is why I am not giving 
instructions on how to do this. You can google at your own risk. I have however 
provided a front cover with the antenna addition so that if you do go this 
route, the case is ready for the SMA antenna and u.fl to SMA wire. Please 
proceed at your own risk on this. I melted several of these tiny connectors 
before I figured out just how to solder it.</p>
<p>&nbsp;</p>
<p>&nbsp;</p>