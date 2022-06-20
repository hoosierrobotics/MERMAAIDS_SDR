# MERMAAIDS_SDR

Read the directions below to start SDR Sharp and get its plugins. 

###########################################
# SDR Sharp
###########################################

First make sure that Microsoft .Net 5.0 is downloaded on your computer. If it is not, then go to https://dotnet.microsoft.com/en-us/download/dotnet/thank-you/sdk-5.0.401-windows-x86-installer so that it can be downloaded. After it downloads, run the installer and follow its directions.

Run SDRSharp.exe and set the source to "RTL-SDR (USB)". Press Play to begin using SDRSharp. 

If SDR Sharp does not work, follow the instructions found here to download SDR Sharp from their own website instead. https://www.rtl-sdr.com/rtl-sdr-quick-start-guide/






Frequency Scanner & LevelMeter Plugins for SDR Sharp

Read the Directions Below to get the plugins to work

###########################################
# Frequency Scanner
###########################################

To get the Frequency Scanner plugin running: 
  - Copy "SDRSharp.FrequencyScanner.dll" into the SDR Sharp "Plugins" folder
  - Copy a line of code to the "Plugins.xml" file which is one of the SDR Sharp files
      - Edit "Plugins.xml"
      - Goto \<sharpPlugins> section and add one line as described below (if there is a backslash in front of the "<" in the code below, don't include it):
  
        \<add key="Frequency Scanner" value="SDRSharp.FrequencyScanner.FrequencyScannerPlugin,SDRSharp.FrequencyScanner" />
  
  - Restart SDR Sharp
  - Top left hamburger icon shows all available plugins, click on "Frequency Scanner"


###########################################
# LevelMeter
###########################################

To get the LevelMeter plugin running: 
  - Copy "SDRSharp.LevelMeter.dll" and "SDRSharp.LevelMeter.xml" into the SDR Sharp “Plugins” folder
  - Copy a line of code to the “Plugins.xml” file which is one of the SDR Sharp files
      - Edit "Plugins.xml"
      - Goto \<sharpPlugins> section and add one line as described below (if there is a backslash in front of the "<" in the code below, don't include it):
  
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
