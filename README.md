#Leap OSC to MIDI for Osculator

This is an OSCulator mapping intended to be used with Nick Fox Gieg's [LeapToOSC processing library](https://github.com/N1ckFG/LeapToOsc). It simply demuxes the OSC message, and maps each finger and hand's X,Y, and Z positions to a midi parameter or note, which can be used in programs like Ableton Live to drive audio and music effects.

###Software

In order to use this workflow, you'll need the following:

* [Leap Motion Software](https://developer.leapmotion.com/)
* [LeapToOSC](https://github.com/N1ckFG/LeapToOsc) 
* [OSCP5 Library for Processing](http://www.sojamo.de/libraries/oscP5/)
* [Processing](http://processing.org)
* [OSCulator](http://osculator.net)
* This OSCulator mapping
* [Ableton Live](http://ableton.com)



###Process

* Start Leap Motion and run the visualizer to make sure it is tracking your hands properly
* Make sure the OSCP5 library is present in your processing libraries folder, along with LeapToOSC.
* Load the LeapToOSC.pde file in processing, and run the sketch. Check out the visualizer and make sure it is registering your fingers properly.
* Start OSCulator, and load this mapping. 
* Ensure that you are listening on port 7110 for OSC messages. As you move your fingers in front of the leap, you should see the different mappings lighting up green and yellow. You can use the quick look button in OSCulator to see the ranges for each finger (ex: finger0-1 > finger > z). Whenever the z finger position crosses the center mark on the graph, the note is triggered, with the velocity / pitch / etc associated with the x and y positions of the fingers. You can change these mappings so that, for example, the x is the note, and the y and z are the parameters, etc. You can also change the min and max range for each coordinate by clicking the arrow in the upper right of OSCulator to access the ranges.
* Lastly, start up Ableton Live. In the browser, go to sounds > piano keys > grand piano (or choose whatever instrument set you want to use). Drag it into one of the midi slots. The instrument rack should be pre-armed and listening for MIDI!
* If you don't hear anything, go to Ableton's Preferences > MIDI Sync menu and ensure Input: OSCulator Out is set to "on" for both "Track" and "Remote" as well as IAC Driver (Bus 1).

Good luck! Let me know if you come up with something cool.


