# MERMAAIDS_SDR

Read the directions below to start SDR Sharp and get its plugins. 

###########################################
# SDR Sharp
###########################################

First make sure that Microsoft .Net 5.0 is downloaded on your computer. If it is not, then go to https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-5.0.401-windows-x86-installer so that it can be downloaded. After it downloads, run the installer and follow its directions.

Download the files from this GitHub by pressing the green code button and downloading the zip file. After it downloads, extract the files. 

Double click on install-rtlsdr.bat which will download the correct drivers and the files rtlsdr.dll and zadig.exe into the folder. Then make sure that your RTL-SDR is plugged in. 




In the folder where you extracted the sdrsharp files find the file called zadig.exe. Right click this file and select "Run as administrator".

In Zadig, go to "Options->List All Devices" and make sure this option is checked. If you are using Windows 10, in some cases you may need to also uncheck "Ignore Hubs or Composite Parents"

Select "Bulk-In, Interface (Interface 0)" from the drop down list. Make sure it is Interface 0 (ZERO), and not "1". Note on some PCs you may see something like RTL2832UHIDIR or RTL2832U instead of the bulk in interface. This is also a valid selection. Double check that USB ID shows "0BDA 2838 00" as this indicates that the dongle is selected.

WARNING: DO NOT select anything else or you will overwrite that device's driver! DO NOT click around randomly in Zadig.

It needs to install the WinUSB driver, so also ensure that WinUSB is selected in the box after the arrow next to where it says Driver (this is the default selection). The box to the left of the green arrow is not important, and it may show (NONE) or (RTL...). This left hand box indicates the currently installed driver, and the box to the right the driver that will be installed after clicking Replace/Install Driver.

Click Replace Driver. On some PC's you might get a warning that the publisher cannot be verified, but just accept it by clicking on "Install this driver software anyway". This will install the drivers necessary to run the dongle as a software defined radio.




Run SDRSharp.exe. Then in the middle left of the screen, set the source to "RTL-SDR (USB)". Click on the Gear Icon (Configure Source) and set the RF Gain maybe about a quarter of the way up. You can change this later to get a better or clearer signal. Press the Play button to begin using SDRSharp. 

If SDR Sharp does not work, follow the instructions found here to download SDR Sharp from their own website instead. They have the same but a little more detailed instructions along with some pictures and will likely help you solve some problems you may have. It is where we got the instuctions from too. https://www.rtl-sdr.com/rtl-sdr-quick-start-guide/






Frequency Scanner & LevelMeter Plugins for SDR Sharp

Read the Directions Below to get the plugins to work

###########################################
# Frequency Scanner
###########################################

To get the Frequency Scanner plugin running: 
  - Move "SDRSharp.FrequencyScanner.dll" into the SDR Sharp "Plugins" folder
  - Copy a line of code to the "Plugins.xml" file which is one of the SDR Sharp files
      - Edit "Plugins.xml"
      - Go to \<sharpPlugins> section and add the line of code as shown below (if there is a backslash in front of the "<" in the code below, don't include it):
  
        \<add key="Frequency Scanner" value="SDRSharp.FrequencyScanner.FrequencyScannerPlugin,SDRSharp.FrequencyScanner" />
  
  - Restart SDR Sharp
  - Top left hamburger icon shows all available plugins, click on "Frequency Scanner"


###########################################
# LevelMeter
###########################################

To get the LevelMeter plugin running: 
  - Move "SDRSharp.LevelMeter.dll" and "SDRSharp.LevelMeter.xml" into the SDR Sharp “Plugins” folder
  - Copy a line of code to the “Plugins.xml” file which is one of the SDR Sharp files
      - Edit "Plugins.xml"
      - Go to \<sharpPlugins> section and add the line of code as shown below (if there is a backslash in front of the "<" in the code below, don't include it):
  
        \<add key="LevelMeter" value="SDRSharp.LevelMeter.LevelMeterPlugin,SDRSharp.LevelMeter" />
  
  - Restart SDR Sharp
  - Top left hamburger icon shows all available plugins, click on "LevelMeter"

Take a look to the config file "SDRSharp.LevelMeter.xml" if you like to change the default settings (needs to restart SDR#)
 
Source code is available at https://subversion.assembla.com/svn/sdrsoft/levelmeter

Credits for LevelMeter: 
  The aGauge Usersontrol is used in this project 
  http://www.codeproject.com/Articles/448721/AGauge-WinForms-Gauge-Control
  The code runs under The zlib/libpng License (http://opensource.org/licenses/zlib-license.php)
  Author of the LevelMeter Plugin: 
    do2bhe@yahoo.de
