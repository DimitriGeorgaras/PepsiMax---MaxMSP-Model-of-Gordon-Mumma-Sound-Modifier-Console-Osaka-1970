# PepsiMax-MaxMSPModel-of-Gordon-Mumma-Sound-Modifier-Console-Osaka-1970
A Max MSP model of Gordon Mumma's Sound modifying console purpose built for the Pepsi Pavilion at the 1970 Osaka World Fair.  
All the parameters and ranges are modelled after the the euro rack circuit kit designed by Michael Johnsen (original schematic by Gordon Mumma, updated by Johnsen for euro rack format).  
The oscillator and envelope ranges are quite limited, presumably due to the limitation of the hardware at the time. 
This MaxMSP recreation attempted to stay as true to the ranges found on Johnsen's euro rack module kit.

The 'PepsiMax.maxpat' file is a MaxMSP patch.
Upon initial opening of the file, user sees the presentation mode interface of all the dials.
The file can be oppened in a bpatcher object to use the GUI interface in any existing max patch (Easiest way to acess GUI).
Alternativly, the contents of the patcher can be copy and pasted into another max patch to have the ability to send control signals to the live.dias.
Inside the unlocked patch, there is a single inlet and single outlet which are the input and output resepectivly.

Control Decriptions:
FM:
Gain: Gain of envelope filter, does not affect audio signal gain into other modules. Value goes from 0-1. When the indicator LED goes red, the envelope value flatlines at 1.
Register: Changes pitch of FM oscillator, which is FM modulated with audio signal.
Mode 1 Fixed Pitch: Pitch of FM oscillator is variable through the Pos/Width knob with the following ranges: 90-126, 636-870, 2508-3475.
Mode 2 Variable Pitch: Pitch of FM oscillator is variable through the Pos/Width knob, as well as the envelope of input audio signal. The modulation depth of the envelope on the FM oscillator pitch varies with the position of the Pos/Width knob. 
Mode 3 Vibrato Fixed: Pitch of FM oscillator is  modulated by Vibrato oscillator. Rate of vibrato oscillator controled by VibRate knob. Pos/Width knob controls the depth of modulations of the vibrato oscillator on the FM pitch.
Mode 4 Vibrato Variable: Pitch of FM oscillator is  modulated by Vibrato oscillator. Rate of vbrato oscillator controled by VibeRate knob AND the envelope of audio signal. 
Threshold: Controls the SQUELCH functionality. When turned to the right, all signal is passed through at any amplitude. As knob is turned to the left, lower amplitude signals get cut off (similar to noise gate). When tunned just right, only the loudest moments of the audio signal are passed through the squelch. The envelope gain knob is useful to get a more usable range out of the threshold is the material is quiet.
Slide: Controls the rate of change of the SQUELCH, effectivley the attack and release time of the gating. When turned to the left, gating occurs quickly. When turned to the right, the attack and release is slower and more 'natural'. This function is not present on the original schematic. It was added in this emulation to get closer to the original sound.
Bypass: Bypasses FM section, goes to AM section.

AM:
AM Rate: Rate of amplitude modulation oscillator.
RateMod: Controls the amount the envelope filter modulates the rate of the AM oscillator. Left no effect on speed, right full envelope modulates speed.
AM Width: Controls the width of AM modulation. When turned left, the signal volume goes from fully on to fully off. When turned fully to the right, the signal volume does not modulate and stays always on. As the knob is turned to the left, the depth of the modulation increases.
Bypass: Bypasses AM section, goes to HPF section.

HPF:
HPF Rate: Rate of high pass filter oscillator. Left slow, right fast.
RateMod: Controls the amount the envelope filter modulates the rate of the HPF oscillator. Left no effect on speed, right full envelope modulates speed.
Bypass: Bypasses the HPF section, goes directly to output.
