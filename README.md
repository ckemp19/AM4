# audio
Misc. files related to music &amp; audio production

## DISCLAIMER
These files are being shared as a courtesy to others who wish to try what I've done on my own devices. By copying or downloading these files you are accepting any risk. I make no guarantees that they will work for your use case, and accept no liability for potential damage to your equipment. 

Manufacturers' names are used for reference only, they imply no endorsement by said manufacturer.

### page28.txt
This is a configuration file for using the Paint Audio MIDI Captain (firmware v5) with the Fractal Audio AM4 amp modeler. It was written for use as a "superset" file - version 5.13 firmware came with superset pages 0-27 included, hence the name page28.txt (feel free to adjust the file numbering as necessary).

This configuration sets: 
- buttons 1-4 to switch between Presets 1-4 in the currently active Preset Bank (A-Z).
- buttons A-D to switch between Scenes 1-4 in the currently active Preset.
- Up & Down buttons (aka key5 and keyE) are used to switch to the next/previous Preset Bank (A-Z).

#### Behavior
Colors for Preset and Scene switches are set using hex codes to match the AM4 colors for Presets (green) and Scenes (red). I recommend setting the AM4 to Effects mode for maximum flexibility, as several others have done. This allows you to toggle individual effects while using MIDI Captain to handle Preset & Scene switching.

Note that, at first launch, all buttons are lit. You must select a Preset and a Scene on the MIDI Captain, at which point only the selected switch will remain lit. 

All switching logic is driven from the MIDI Captain, it does not read status from the AM4. Because of this (unfortunately) the Bank switching is a bit blind - the MC display will show a number: 
   0 = Bank A
   4 = Bank B
   8 = Bank C
  12 = Bank D
  etc. 
  
You have to select a Preset after switching Banks to see it reflected on the AM4.

*This has to do with how the switching is done, i.e. Bank A1 + 4 = Bank B1, Bank A1 + 8 = Bank C1.*


#### Installation
- Download page28.txt or copy the raw code to a text file on your computer.
- Connect your MIDI Captain to your compute via USB.
- Boot your MIDI Captain into USB more by holding down button 1 and powering on the MIDI Captain. You should see the volume "MIDICAPTAIN" appear.
- Open MIDICAPTAIN, and drag page28.txt into the "superset" folder.
- Eject the MDIDCAPTAIN volume and power off the MIDI Captain.
- Connect the MIDI Out port of the MIDI Captain to the MIDI In port on the AM4.
- Boot your MIDI Captain into SuperMode by holding down button A and powering on the MIDI Captain.
- Long-press the Up/Down buttons to load Page 28.

### AM4 Configuration
Go into Setup Mode on your AM4. Navigate to SETUP > MIDI/Remote and configure the following:

MIDI Channel	1 (or match your MIDI Captain output channel)	

*Must match the channel MIDI Captain sends on*

Receive MIDI PC	ON	

*Allows AM4 to receive Program Change messages from MIDI Captain*

Send MIDI PC	OFF	

*You don't need AM4 sending PC back; MIDI Captain is controlling it*

Ignore Redundant PC	ON	

*Prevents the preset from reloading if the same PC is sent twice*

### Removal
If you don't want to use the configuration anymore, simply boot your MIDI Captain into USB mode as indicated above, delete the file, and restart the MC.

#### Thanks to Paint Audio support and duck.ai for assistance with getting this working!
