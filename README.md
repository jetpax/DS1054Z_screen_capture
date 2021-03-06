# DS1054Z_screen_capture
'OscScreenGrabLAN.py' is a Python script that captures
whatever is displayed on the screen of a Rigol DS1000Z series oscilloscope.

It can save data as a WYSIWYG (What You See Is What You Get) picture of the oscilloscope screen,
 or as a text file in CSV (Comma Separated Values) format.

To achieve this, SCPI (Standard Commands for Programmable Instruments) are sent from the computer
to the oscilloscope, using the LXI (LAN-based eXtensions for Instrumentation) protocol over a Telnet connection.
The computer and the oscilloscope are connected together by a LAN (Local Area Network).
No USB (Universal Serial Bus), no VISA (Virtual Instrument Software Architecture),
no IVI (Interchangeable Virtual Instrument) and no Rigol drivers are required.
Python 2 is required. Python 3 is not supported.

Tested with Windows 7, Python 2.7.9 and Rigol DS1104Z (a fully upgraded DS1054Z oscilloscope).

Tested in a VMware machine with Linux Debian 7.7.0, Python 2.7.3 and PIL.


User Manual:
-----------
Usage:

    python OscScreenGrabLAN.py png|bmp|csv [oscilloscope_IP [save_path]]

Usage examples:

    python OscScreenGrabLAN.py png
    python OscScreenGrabLAN.py csv 192.168.1.3

The following usage case is not yet implemented:

    python OscScreenGrabLAN.py bmp 192.168.1.3 my_place_for_captures

This program captures either the waveform or the whole screen
    of a Rigol DS1000Z series oscilloscope, then save it on the computer
    as a CSV, PNG or BMP file with a timestamp in the file name.

    The program is using LXI protocol, so the computer
    must have LAN connection with the oscilloscope.
    USB and/or GPIB connections are not used by this software.

    No VISA, IVI or Rigol drivers are needed.


Windows Usage:
-------------
Install Python 2.7.9 from https://www.python.org/downloads.
Install "Python Imaging Library 1.1.7 for Python 2.7" from http://www.pythonware.com/products/pil.
Run the PIL (Python Imaging Library) installer as Administrator, otherwise it won't be installed properly.
Connect together the computer and the oscilloscope (by LAN).
In order to capture an image from the oscilloscope display and save it to the computer disk,
open a Command Prompt as Administrator and run "OscScreenGrabLAN.py".

Example:

    C:\Python27\python.exe OscScreenGrabLAN.py png 192.168.1.3
    C:\Python27\python.exe OscScreenGrabLAN.py csv 192.168.1.3
    
Linux Usage:
-----------
Python and PIL are already present in the default Debian 7.7.0 installation, 
so it is not necessary to manually install them.
Connect together the computer and the oscilloscope (by LAN), download the project from GitHub, open a Terminal, 
go to the project's directory and run "OscScreenGrabLAN.py". 

Example:

    python OscScreenGrabLAN.py png 192.168.1.3
    python OscScreenGrabLAN.py csv 192.168.1.3
    