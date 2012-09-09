pavolume is a simple python PulseAudio volume control for the command line. It is designed to be bound to your XF86Audio* keys so you can comfortably control PulseAudio volume.

![pavolume notifications](http://i.imgur.com/SnVxL.png)

# Usage

	pavolume show              # show volume and mute status as notification
	pavolume volup             # increase volume
	pavolume voldown           # increase volume
	pavolume volset 50%        # set volume to 50%
	pavolume volset 200%       # boost volume to 200%
	pavolume muteon            # mute audio output
	pavolume muteoff           # un-mute audio output
	pavolume mutetoggle        # toggle mute


You can use the <code>--quiet</code> switch to not play a blip sound and the <code>--noshow</code> switch to not show libnotify notifications. If you want to allow <code>volup</code> to go over 100%, you can use the <code>--nolimit</code> switch:

	pavolume volup --nolimit   # turn it to 11!

# Installation
Clone the git repo somewhere and put <code>pavolume</code> on your <code>$PATH</code>. The <code>pavolume.conf</code> can go in one of these places:

* The same directory as pavolume
* <code>$XDG_CONFIG_HOME/pavolume/pavolume.conf</code>, i.e. <code>$HOME/.config/pavolume/pavolume.conf</code>
* <code>/etc/pavolume/pavolume.conf</code>

Make sure to edit the config file so that it points to a valid blip sound file (it uses the Ubuntu message sound by default). Other than that, pavolume will use the first sink registered in your system.

# Dependencies

* <code>pacmd</code>
* Python 3 with packages:
	* <code>docopt</code>
	* <code>pygobject</code>

# Questions, Comments, Code
If you have questions or comments, drop me a mail on GitHub! Code contributions are always welcome, too!

