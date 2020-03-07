# this script read Mate3 data write values in MariaDB
# output JSON file with all info

version history:
=====================================
05.05.2019 - 0.1.0       - first release
07.05.2019 - 0.2.0 major - moved variables up, introduced error treatment subroutine, 
		        correct list ->wrong display of Operating Mode FXR
11.05.2019 - 0.2.1 minor - introduce error and warning mode , JSON file is now complete
14.05.2019 - 0.2.2 minor - correct error of double FNDC display in JSON
14.05.2019 - 0.2.3 minor - design changes
31.05.2019 - 0.3.0 major - save datatime direct to SQL table - date field in SQL table should be set from "current timestamp" to "none" 
06.06.2019 - 0.3.1 minor - update links inside
08.06.2019 - 0.4.0 major - moved variables in config.txt 
18.06.2019 - 0.4.1 minor - bug correction aux mod FXR
23.07.2019 - 0.4.2 minor - small design updates on error reporting
01.11.2019 - 0.4.3 minor - change the error file name to general_info 
31.12.2019 - 0.4.4 minor - errors flag not displayed correct for FM60/80.this is fixed now
07.03.2019 - 0.5.0 major - add MQTT for Home Automation integration (Bat, SOC,AC, Operational Mode)
                         - add option for second path for JSON file (potential use in Home Automation)
                         - ReadMateStaus.cfg updated
--------------------------
in use 0.5.0
