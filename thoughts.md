Pi Deck
-----------------------------------
Use a rasberry pi to emulate a stream deck functionality so I can control obs and I can use it as a button box within my racing sims.

The rasberry pi will have a GUI "button" interface which will allow a user to press a button on the pi and have a action invoked on another PC, this will be achieve by having an rest service on the main PC which will listen to commands coming from the rasberry pi and then invoke the command on the host pc.

To invoke commands in obs we will need to use webhooks plugin for obs.
To invoke commands in sims we will need to emulate a joypad (vJoy?)

Hardware Requirements
-----------------------------------
* Rasberry Pi
* Touch Screen
* Case to hold them together

Software Requirements (High Level)
-----------------------------------
* App to run on the Pi (linux?) which will:
  * gives you a configurable button interface
  * add a button which will invoke a given action
    * allow you to assign pictures to the buttons
  * allow you to have "screen" buttons which will take you to another screen
    * we could use something like Avalonia UI

* App to run on Windows which can
  * start up a rest service to accept commands
    * install with squirrel
    * run at start up and minimise to the taskbar
    * wpf? or .net core?
  * send commands to obs
  * imitate joypad input
  * imitate keyboard input

Research
----------------------------------
* OBS Websockets
  * https://github.com/Palakis/obs-websocket
* AvaloniaUI (linux UI in c#)
  * https://avaloniaui.net/docs/quickstart/
* Simulate Send KeyPress
  * https://docs.microsoft.com/en-us/dotnet/api/system.windows.forms.sendkeys?redirectedfrom=MSDN&view=netcore-3.1
* Simulate Joypad
  * vJoy? - but its an external dependancy...
    * https://github.com/bobhelander/vJoy.Wrapper
  
