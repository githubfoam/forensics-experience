# forensics-experience

[![process accounting CI workflow](https://github.com/githubfoam/forensics-experience/actions/workflows/process-accounting-workflow.yml/badge.svg?branch=master)](https://github.com/githubfoam/forensics-experience/actions/workflows/process-accounting-workflow.yml)  

UAV - Unmanned aerial vehicle forensics
~~~~
DatCon 
case study: flight logs, motor speeds, battery usage, a tool designed to interpret .DAT files specifically from DJI UAV

CsvView and DatCon are free offline apps that provide the means to analyze log files produced by the Phantom 3, Phantom 4, Phantom 4 Pro, Inspire 1, Spark, and Mavic Pro drones. To use one, or both, of these apps just download and install on your PC, Mac or Linux machine.
https://datfile.net/
~~~~
~~~~
DJIFix 
carves  images  and videos  through  the commandline

Repairing Corrupt DJI Video Files
if you accidentally power off your DJI quadcopter (Phantom, Mavic, Spark, or Inspire) before stopping video recording, you'll be left with a file that's corrupt, and cannot be played. 
http://djifix.live555.com/
~~~~
~~~~
ST2Dash der Flightlog Konverter für die  ST10+/Q500.

https://www.drohnen-forum.de/index.php/Thread/12303-ST2Dash-der-Flightlog-Konverter-f%C3%BCr-die-ST10-Q500/
~~~~

~~~~
DroneLogbook
STANDARD Free
Perfect for the hobbyist and individual user who wants to track key flight 

Log your flights with detail
Import your flight log to fill info automatically, view GPS trace and replay it in 3D.
https://www.dronelogbook.com/hp/1/index.html
~~~~
~~~~
Gryphon Drone Forensics Tool

 this tool aims to extract critical events happened during the flight of an Unmanned Aerial System/Vehicle, running Ardupilot flight stack. This tool is part of the research paper Gryphon: Forensics on Dataflash and Telemetry Logs.
https://github.com/emantas/gryphon_dft
~~~~
~~~~
process accounting on Linux
RHEL :  yum install psacct
Ubuntu : sudo apt-get install acct
https://man7.org/linux/man-pages/man5/acct.5.html
~~~~
Anti-Forensics
~~~~

Timestamps

TimeStomp

parse MFT files
https://github.com/dkovar/analyzeMFT

Extract $MFT record info and log it to a csv file. 
https://github.com/jschicht/Mft2Csv

collect MFT files
https://github.com/orlikoski/CyLR

Parser for $UsnJrnl on NTFS 
https://github.com/jschicht/UsnJrnl2Csv

Parser for $LogFile on NTFS 
https://github.com/jschicht/LogFileParser

https://github.com/jschicht/SetMace

Hiding Data in Slack Space using bmap
http://dl.packetstormsecurity.net/linux/security/bmap-1.0.17.tar.gz

slacker.exe

Finding Data in Slack Space
sleuthkit/autopsy

Disable Timestamps - UserAssist
registry key that maintains dates and hours when each executable was run by the user

Disabling UserAssist
Set two registry keys both to zero

HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced\Start_TrackProgs
HKEY_CURRENT_USER\SOFTWARE\Microsoft\Windows\CurrentVersion\Explorer\Advanced\Start_TrackEnabled

Disable Timestamps - Prefetch
information about the applications executed with the goal of improving the performance of the Windows system

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\SessionManager\Memory Management\PrefetchParameters

Set two registry keys both to zero
EnablePrefetcher and EnableSuperfetch

Disable Timestamps - Last Access Time
Whenever a folder is opened from an NTFS volume on a Windows NT server, the system takes the time to update a timestamp field on each listed folder, called the last access tim

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem
set value to 1
NtfsDisableLastAccessUpdate

Delete USB History
USBSTOR registry key that contains sub keys which are created whenever you plug a USB Device 

HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Enum\USBSTOR
saves information about the USBs
C:\Windows\INF\setupapi.dev.log

https://www.nirsoft.net/utils/usb_devices_view.html


Disable Shadow Copies

#List shadow copies
vssadmin list shadowstorage
#Delete  shadow copies
vssadmin delete shadow

disable shadow copies
services-Volume Shadow Copy-Properties-Startup type-Disabled

Overwrite deleted files

Delete Windows event logs

eventvwr.msc-Windows Logs-Clear Log
Get-EventLog -LogName * | ForEach { Clear-EventLog $_.Log }

Disable Windows event logs

services-Windows Event Log-Properties-Startup type-Disabled

reg add 'HKLM\SYSTEM\CurrentControlSet\Services\eventlog' /v Start /t REG_DWORD /d 4 /f

Disable $UsnJrnl

fsutil usn deletejournal /d c
~~~~