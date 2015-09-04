##cystation v1.0.0

**Code:** http://neetco.de/cyfause/cystation.git <BR>
**IRC:** irc://irc.rizon.net/cystation <BR>

##DOWNLOADING

Either use git bash, and type "git clone http://neetco.de/cyfause/cystation.git" into it,
"clone on desktop" on the sidebar, or "download zip".

##INSTALLATION

First-time installation should be fairly straightforward.  First, you'll need
BYOND installed.  You can get it from http://www.byond.com/.  Once you've done 
that, extract the game files to wherever you want to keep them.  This is a
sourcecode-only release, so the next step is to compile the server files.
Open tgstation.dme by double-clicking it, open the Build menu, and click
compile.  This'll take a little while, and if everything's done right you'll get
a message like this:

```
saving tgstation.dmb (DEBUG mode)
tgstation.dmb - 0 errors, 0 warnings
```

If you see any errors or warnings, something has gone wrong - possibly a corrupt
download or the files extracted wrong. If problems persist, ask for assistance
in irc://irc.rizon.net/cystation-coderbus

Once that's done, open up the config folder.  You'll want to edit config.txt to
set the probabilities for different gamemodes in Secret and to set your server
location so that all your players don't get disconnected at the end of each
round.  It's recommended you don't turn on the gamemodes with probability 0, 
except Extended, as they have various issues and aren't currently being tested,
so they may have unknown and bizarre bugs.  Extended is essentially no mode, and
isn't in the Secret rotation by default as it's just not very fun.

You'll also want to edit config/admins.txt to remove the default admins and add
your own.  "Game Master" is the highest level of access, and probably the one
you'll want to use for now.  You can set up your own ranks and find out more in
config/admin_ranks.txt

The format is

```
byondkey = Rank
```

where the admin rank must be properly capitalised.

Finally, to start the server, run Dream Daemon and enter the path to your
compiled tgstation.dmb file.  Make sure to set the port to the one you 
specified in the config.txt, and set the Security box to 'Safe'.  Then press GO
and the server should start up and be ready to join.

###HOSTING ON LINUX
We use BYGEX for some of our text replacement related code. Unfortunately, we
only have a windows dll included right now. If you're up to it, you can head
over to https://code.google.com/p/byond-regex/ and compile it for linux.

Otherwise, edit the file `code/_compile_options.dm`, and comment out:
`#define USE_BYGEX`
at the bottom, so that it looks like this:
`//#define USE_BYGEX`
Recompile the codebase afterwards.

##UPDATING

To update an existing installation, first back up your /config and /data folders
as these store your server configuration, player preferences and banlist.

Then, extract the new files (preferably into a clean directory, but updating in
place should work fine), copy your /config and /data folders back into the new
install, overwriting when prompted except if we've specified otherwise, and
recompile the game.  Once you start the server up again, you should be running
the new version.

##LICENSE

See LICENSE-AGPLv3.txt and LICENSE-GPLv3.txt for more details.
All content including icons and sound is under a Creative Commons 3.0 BY-SA
license (http://creativecommons.org/licenses/by-sa/3.0/).
