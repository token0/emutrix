If you know your way around with linux, EMutrix should be fairly easy to install, but
if you are new to Linux, this is a step-by-step guide to install EMutrix from source.

Also, see [this post](http://groups.google.com/group/emutrix/browse_thread/thread/8294e88ef6d45076). Specially if you are on OpenSUSE

## Prerequisites ##
Besides the compatible soundcard, you will need a working linux installation, with ALSA (Advanced Linux Sound Architecture) drivers for E-mu cards installed.

Don't worry, most _recent_ versions of popular distributions come with this installed by default. If you already have sound, you're good to go, skip to "Getting the source". If not, run
```
amixer --version
```
in a console (or terminal) to find out if you have a compatible version of ALSA: it should be at least 1.0.15, although 1.0.14 will work for older cards, too.

## Getting the source and dependencies ##
Download the latest source package from http://code.google.com/p/emutrix/downloads/list

To compile EMutrix you will also need the development packages for Qt (A toolkit, mostly for the GUI) and ALSA. If you are running a debian-based distribution like Ubuntu, open a cosole and install them with the following command:
```
sudo apt-get install build-essential libqt4-dev libasound-dev`
```

## Compilation ##
Now, extract the EMutrix source code in some place in your home folder, and switch to that place using the following command:
```
cd /place/where/you/extracted/emutrix/
```

Use the
```
ls
```
command to list the files present in your current folder. You should see a few files named README, Makefile, COPYING, among others.

To finally compile EMutrix, simply type
```
make
```
If you get a message about a missing file "/usr/share/qt4/mkspecs/linux-g++/qmake.conf", try running
```
qmake "CONFIG+=debug"
```
and then running make again.
It may take a while. If you get errors, please comment below or send a message to  [the EMutrix discussion group](http://groups.google.com/group/emutrix/post) for help.

## Running EMutrix ##
If you successfully compiled EMutrix, again, type
```
ls
```
into the console. Now you should see a new file called "emutrix". This is the program. Try running it with
```
./emutrix
```

Be aware that the sound will be muted on program start. Slowly rise the master volume fader on the left side of the window and start playing with the routing matrix in the middle. Have fun!

## Installation ##
If you are satisfied with EMutrix you can install it with the
```
sudo make install
```
command. Then you can run it by typing emutrix in the console from any folder or add an icon to your desktop manager, if you like.
Remember to subscribe to the discussion group or periodically check back to see if new versions of EMutrix are out. It is still in very early stages of development.

Again, if you get errors or something doesn't work as expected don't hesitate to comment below or post to [the EMutrix discussion group](http://groups.google.com/group/emutrix/post). It may be helpful if you attach the output of the
```
amixer info
```
command to your message.
