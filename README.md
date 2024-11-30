MonitorMate_ModBus 
===========

A monitoring system for the Outback Power MATE3/MATE3S. 
It processes data from MATE3/MATE3S using ModBus protocol, reformats it for logging, charting, and display on a web server.
Modbus comunication with MATE3/MATE3s was done base on https://github.com/basrijn/Outback_Mate3 -- Thanks Bas!

Charts and graphs are creating using Highcharts JS for free under the Creative Commons "Attribution-NonCommercial 3.0 License" regulations. http://www.highcharts.com

This is a fork from https://github.com/instanttim/MonitorMate -- Thanks Tim for your great work!

How does this software work?
===========
The software is divided in two parts:

- Python script for query MATE3/MATE3S using ModBus protocol,registering the data in the database and query’s.
- PHP/HTML/JavaScript webpage for visual representation.

ReadMateStatusModBus.py
===========
- Query MATE3/MATE3S and gets data, format, register in the database and returns a json file that is used for display current status. As of version 0.5.1 MQTT is implemented for further integation with Home Assistant -- more info here https://github.com/chinezbrun/mate3_homeassistant
- ReadMateStatusModBus.py script is running once every X minute -- task should be created (windows or Linux)
- ReadMateStatusModBus.cfg is the config file for this script

ReadMateStatusModBus.sh (is not mandatory)
===========
Is an example of InitScript for ReadMateStatusModBus.py in LINUX.This script should run with minimum one minute frecvency .
See your specific OS/distributions documentaiton for setting up daemons/tasks.

getstatus.php
===========
Gets data from database an returns a json string.

monitormate.html / monitormate.js
===========
Visual representation of devices status and history. Works with getstatus.php for history and with matelog for “real time” status.

config.php
===========
Configuration file. Contains database connection parameters, record interval(not used), security token(not used), time zone, and power system configuration.

Installation and Execution
===========

1. Download MonitorMate_ModBus and extract it.
2. Rename the config file to config.php (remove .sample)
2. Edit the config file to your liking.
3. Create the database manually, and a new database user if necessary.
4. Use database.sql to create tables in your MySQL database. (I suggest phpAdmin to import)
5. Copy the “WebServer” directory to your web server.
6. Copy the "DataStreamRelay" directory to your host computer (if it's not the one you're using)
7. Configure ReadMateStatusModBus.cfg
8. Set a task in host computer to run ReadMateStatusModBus.py every "X" minute (TaskScheduler in Windows)

ex Linux : /usr/local/bin/python3.6 /var/www/html/DataStreamRelay/ReadMateStatusModBus.py
ex: windows: D:\xampp\python\python37\python.exe D:\DataStreamRelay\ReadMateStatusModBus.py
depending on your paths

Go to  http://www.YOURSERVER.com/index.php (maybe you have to wait a little depending your record interval.)

NOTE : this repository reached EOL - no support will be provided as of 01.12.2024
