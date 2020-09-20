---
layout: post
title:  "Spotify without Spotify"
date: 2020-07-21
background: 
---

# The Problem

A while ago I noticed that the fans in my laptop became loud even while I wasn't doing any computing-heavy tasks. I got curious about this and started to monitor the CPU-usage of the running processes. It turned out that the process that used the most of my CPU was the official Spotify client.

I usually have Spotify configured so that it autostarts with the system. Even though I'm listening to the music on my smartphone I need to have the PC client open so that the current song title gets displayed in my status bar. This way I can leave my phone in the pocket and still see on my laptop which song is currently playing.

After doing a bit of googling I found out that the desktop client for Spotify is not very optimized and especially the advertisement banners on the home screen (which I had open most of the time) need a lot of CPU power. Additionally the Linux client isn't a very passionate project from the developers at Spotify and gets rarely updated.

Because I don't want to have such a CPU and battery hungry process constantly running on my laptop I decided to find a more lightweight replacement for the official client. In this post I will present my solution and give a overview of how to configure your system so that you get the following features:

- use a command-line interface to search and play music just like you would do in on any other client.
- get the current song title displayed on whatever window manager bar you are using
- control the music through keyboard shortcuts
- all of the above, no matter on which device the music is actually playing

# The Solution

After I spent way to much time on testing out all different kinds of configurations I found a solution that I'm happy with. The core elements of this solution are:

- the [spotifyd](https://github.com/Spotifyd/spotifyd) client.
- the [spotPRIS2](https://github.com/freundTech/SpotPRIS2) dbus interface.
- the [spotify-tui](https://github.com/Rigellute/spotify-tui) command-line interface.
- the [spotify_status.py](https://github.com/Bergschrat1/polybar-spotify) script which was originally written by [Jvanhijn](https://github.com/Jvanrhijn) as a module for polybar but works for everything else just as well. I have adapted it a bit so that it uses the spotPRIS2 interface instead of the official Spotify interface.

All of these projects are open-source and the installation instructions can be found on Github.
The spotify_status.py script can be placed anywhere and should be made executable:

~~~shell
chmod +x ./spotify_status.py
~~~

After all the software is installed there is some configuration to do:

# Set up a Spotify device with spotifyd

First we have to create a Spotify device that can play music and that appears on other Spotify clients. For this we use spotifyd. You can find an example configuration file for spotifyd on my [Github](https://github.com/Bergschrat1/setup_spotify) repository. This has to be placed at `~/.config/spotifyd/spotifyd.conf` .

To let spotifyd log into your spotify account you have to choose some form of authentication in the config file. I recommend using a keyring which requires you to make a new keyring entry. The entry needs to have specific attributes which is described on the [spotifyd Github](https://github.com/Spotifyd/spotifyd)

Now just start and enable the spotifyd service with systemd:

~~~sh
$ systemctl --user start spotifyd.service
$ systemctl --user enable spotifyd.service
~~~

# Spotify Interface

To control the music with commands and to get information about the current song we need to have some kind of dbus interface.

After some testing I found the built-in spotifyd dbus interface to be instable and unreliable, that's why I decided to use the spotPRIS2 interface instead.
The only downside of spotPRIS2 that I could find is that the name of the dbus interface seems to be randomly generated and changes from time to time. That's why I had to make the selection of that device robust against this change.

But first we need to make spotifyd and spotPRIS2 autostart with the system. For that I use their systemd services. To tell spotPRIS2 for which device it should create an interface you need to add a parameter to the spotpris2.service file located at `/usr/lib/systemd/user/spotpris2.service`
For that just change the line containing `ExecStart`:

~~~
%%/usr/lib/systemd/user/spotpris2.service

ExecStart=/usr/bin/spotpris2 -d='{your systemd spotify device}'
~~~
The device name has to be the exact same as in your `spotifyd.conf` file!

To make this setup robust against the random name changes from spotpris2, I decided to declare a global variable that I can read whenever I want to contact the interface. This can be done by including this snippet in your ~/.xinitrc file (or whichever file your system reads on startup).

```sh
dbus_interface=$(dbus-send --print-reply --dest=org.freedesktop.DBus /org/freedesktop/DBus org.freedesktop.DBus.ListNames | grep spotpris)
tmp=${dbus_interface##*.}
export SPOTPRIS_INTERFACE=${tmp%\"}
```

With this you can bind your multimedia keys to control your music. It depends on your window manager how to configure this. The relevant keys and commands are:

~~~sh
# Play/Pause
Key: XF86AudioPlay
Command: dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotpris.$SPOTPRIS_INTERFACE /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.PlayPause

# Next song
Key: XF86AudioNext
Command: dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotpris.$SPOTPRIS_INTERFACE /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.Next

# Previous song
Key: XF86AudioPrev
Command: dbus-send --print-reply --dest=org.mpris.MediaPlayer2.spotpris.$SPOTPRIS_INTERFACE /org/mpris/MediaPlayer2 org.mpris.MediaPlayer2.Player.Previous
~~~

# spotify-tui

If you want a nice GUI to select and control music I highly recommend spotify-tui.
It has all the functionality you need for listening to your Spoitfy playlists or browse music without the annoying adds and recommendation from the official Spotify client.
The setup is a bit tricky since you need to insert your spotify api key. But this process is explained very well on the project's [Github page](https://github.com/Rigellute/spotify-tui).

# Integration into the statusbar

If you want to get the current song title displayed in your status bar, you can just execute the spotify_status.py script and it will return the song title as a string. It also takes arguments to customize the output.
This way the song status can easily be implemented in basically every status bar and window manager.

# Conclusion

Wth these tools you have all the functionality from the official Spotify client minus the annoying ads and minus the high CPU usage. In my testing I found that all programs running simultaneously are barely using any CPU or RAM which is a huge improvement over the original setup.
