
* Anne Pro 2

I just got my first mechanical keyboard and have been trying to use
it. It's tricky enough that I need to take some notes.

** Application Setup

A PC app is available from their site. I decided to run the deb file
on Ubuntu.

http://en.obins.net/

The app installs in =/opt/ObinsKit= and the executable is
=/opt/ObinsKit/obinskit=

The app runs. Plugging int the keyboard via usb and trying to connect
to it result in an device error and a core dump. I found a workaround
here:

#+BEGIN_SRC bash
Ubuntu/Debian

Most Linux distros use udev to manage access to physical devices. To allow non-root access

our keyboard, before using Obenslab Starter for the first time, we need the following operations:

Create file obinslab-starter.rules under /etc/udev/rules.d

SUBSYSTEM=="input", GROUP="input", MODE="0666"

# For ANNE PRO 2

SUBSYSTEM=="usb", ATTRS{idVendor}=="04d9", ATTRS{idProduct}=="8008",

MODE="0666", GROUP="plugdev"

KERNEL=="hidraw*", ATTRS{idVendor}=="04d9", ATTRS{idProduct}=="8008",

MODE="0666", GROUP="plugdev"

## For ANNE PRO

SUBSYSTEM=="usb", ATTRS{idVendor}=="0483", ATTRS{idProduct}=="5710",

MODE="0666", GROUP="plugdev"

KERNEL=="hidraw*", ATTRS{idVendor}=="0483", ATTRS{idProduct}=="5710",

MODE="0666", GROUP="plugdev"

2. Reload rules by execute: sudo udevadm control --reload-rule

3. Unplug and replug keyboard
#+END_SRC

It seemed to work after that and I remapped a couple keys and fiddled
with the lighting.

** Bluetooth

This seemed like a mess but I finally figured it out.

1) Turn keyboard swith on

The switch is underneath the keyboard

2) Initiate Pairing

=FN2 + 1,2,3,4= (hold 5 seconds)

The number button should glow but then flicker quickly green after
five seconds. Pairing with the device should work.

3) Save pairing?

I'm not sure if this is necessary. Once a pairing exists, it needs to
be saved to one of the four presets:

#+BEGIN_SRC bash
FN1 + B
1
ESC
#+END_SRC

4) Start from scratch.

Turn power off/on.

Hit any key (such as shift) to wake up the keyboard.

The bluetooth should connect within a couple seconds.

I was never able to get this thing to pair with either of my tablets
(one old and one brand new) and I was never able to get it to pair
with settings 2-4. Also, whenever I tried to pair it with 2-4 it made
my phone forget the pairing for 1. I think I'll just have to
leave this paired to my phone.

Testing it some more it seems the bluetooth connection is super flakey
and I have to re-pair a lot. Let me just practice typing with this and
see what happens.

** Keyboard Mapping

I was starting to like the FN1 + WASD as cursor movement until I
realized that much of my typing involves word
movement. (ctrl+left,right) and word selection (shift+ctrl+left,right)

My first naive solution to this was to may ctrl+shift+left and
ctrl+shift+right to distinct keys but this didn't seem possible. I
probably have this wrong but I went on to other solutions.

I found this thread:

https://www.reddit.com/r/AnnePro/comments/ao0qzv/anne_pro_2_arrow_keys_issue/

The first comment is an amazing solution. He remaps all the keys on
the lower right side of the keyboard. This means using caps log for
FN1 but giving up on FN1. As a result, you need to go through the FN2
map and move any useful function to FN1. This wasn't that hard.

His solution was to remap the arrow keys to FN1,FN2,left shift, and
some other key. I tried that and determined that my hands
automatically use both the left and right shift for capitalization
when touch typing. This solution didn't work for me.

My alterntive is to leave shift alone but to add left alt to the
mix. This gives me a row of keys: left,right,up,down. It's not as
intuitive as a diamond patter but it's nice to stick four fingers on
something in the lower left of the keyboard and have my left hand jump
in with ctrl and shift as necessary.
