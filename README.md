pavolume is a simple python PulseAudio volume control for the command line. It is designed to be bound to your XF86Audio* keys so you can comfortably control PulseAudio volume.

![pavolume notifications](http://i.imgur.com/SnVxL.png)

# Usage

	pavolume show              # show volume and mute status as notification
	pavolume volup             # increase volume
	pavolume voldown           # decrease volume
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


## Using pavolume with awesome
If you are using [awesome](http://awesome.naquadah.org/), you can use the following key bindings to control pavolume:

	awful.key({       }, "XF86AudioRaiseVolume", function() awful.util.spawn("pavolume volup") end),
	awful.key({"Shift"}, "XF86AudioRaiseVolume", function() awful.util.spawn("pavolume volup --nolimit") end),
	awful.key({       }, "XF86AudioLowerVolume", function() awful.util.spawn("pavolume voldown") end),
	awful.key({       }, "XF86AudioMute", function() awful.util.spawn("pavolume mutetoggle") end),

Pressing the volume up/down keys normally will increase/decrease volume, if you hold shift, you can increase the volume over 100%.

If these bindings don't work for some reason, try calling the commands from the command line directly. If this works, then check whether the pavolume script is also visible from awesome's <code>$PATH</code>. If its still not working, you can insert full path to your pavolume folder and pavolume file e.g. /home/user/.config/pavolume/pavolume. 

## Using pavolume with qtile
If you are using [qtile](http://www.qtile.org/), you can use the following key bindings to control pavolume:

    Key([], "XF86AudioRaiseVolume", lazy.spawn("pavolume volup")),
    Key(["Shift"], "XF86AudioRaiseVolume", lazy.spawn("pavolume volup --nolimit")),
    Key([], "XF86AudioLowerVolume", lazy.spawn("pavolume voldown")),
    Key([], "XF86AudioMute", lazy.spawn("pavolume mutetoggle")),

Pressing the volume up/down keys normally will increase/decrease volume, if you hold shift, you can increase the volume over 100%.

If these bindings don't work for some reason, try calling the commands from the command line directly. If this works, then check whether the pavolume script is also visible from awesome's <code>$PATH</code>. If its still not working, you can insert full path to your pavolume folder and pavolume file e.g. /home/user/.config/pavolume/pavolume. 

# Dependencies

* <code>pacmd</code>
* Python 3 with packages:
	* <code>docopt</code>
	* <code>pygobject</code>

# Questions, Comments, Code
If you have questions or comments, drop me a mail on GitHub! Code contributions are always welcome, too!

