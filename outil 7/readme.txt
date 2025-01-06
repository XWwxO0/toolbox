					RatioMaster
					Version 1.9.1
					*** Intro ***
RatioMaster is an application designed for spoofing uploads on BitTorrent trackers. 
It connects to a tracker and behaves like a normal BitTorrent client, but without 
actually uploading to / downloading from other peers in the swarm. It reports to the 
tracker that it's uploading (or downloading or both, it's your choice) at a certain 
rate, thus making it useful for artificially increasing your ratio on certain sites 
that track a user's overall ratio (total uploaded/total downloaded).
RatioMaster has hardcoded emulations for the most commonly used BitTorrent clients, 
but it is also able to parse external files for emulation settings, thus making it easily
extensible for your favorite client and easy to update when new versions of said clients
are released. The client files (extension ".client") are actually renamed XML files and 
the syntax should be pretty straight-forward. The emulation layer includes support for 
parameter order in GETs, reproduction of HTTP headers, generation of application-specific
peer_ids and keys and more. RatioMaster can also parse the tracker reannounce time from 
the tracker's HTTP response, and combined with the fact that you can specify down and 
up rates makes it pretty hard to detect by any anti-cheat scripts, if not downright 
impossible. Other features, like a TCP listener (so as to appear connectable on the 
tracker's peerlist) and a leecher counter (so as to stop any uploads when a torrent 
has 0 leechers) also contribute to RatioMaster's spoofing abilities.

Memory Reader
--------------------
Starting from version 1.6 RatioMaster have integrated Memory Reader tool that usefull 
when you want to read exact Peer ID, Key, Port and Number of peers announce parameters
from your regular torrent client (like uTorrent,Azureus,Bitcomet or others). Look for
the 'Memory Reader' button in Advanced Tab.

Command Line support 
---------------------
Starting from version 1.7 RatioMaster supports command line options.This feature is useful
if you want to run several torrents from batch file or shortcuts with predefined setting:
Possible keys : 
   /minimize - RM will start minimized to tray.
   /start - RM will load latest torrent (or the one provided in command line) and
automatically start it
   /downloadRate, /uploadRate - RM will set download and upload speed 
   /percent - RM will set finished percent (0% = start leeching, 100% = seeding)
   /hide  - RM will start in hidden mode, minimized and no tray icon .Use at your own
risk, as far as i know the only way to stop it, is to kill process in Task Manager.

Examples (torrentpath.torrent is a full path to the torrent file) : 

   ratiomaster.exe torrentpath.torrent
 - will load the torrent
   ratiomaster.exe torrentpath.torrent /start
 - will load the torrent from torrentpath and run it with default options
   ratiomaster.exe torrentpath.torrent /start /uploadRate:250 /downloadRate:200 /percent:100
 - will load the torrent and start it with 250 upload,200 download,and finished 100%
   ratiomaster.exe /uploadRate:250
 - will set provided value,all others will be default from settings
   ratiomaster.exe /minimize /start
 - will start ratiomaster in minimized mode with last loaded torrent.

Saving individual torrent settings 
----------------------------------
Starting from version 1.7 RatioMaster saves individual settings for each torrent and uses
those settings next time that you are loading same torrent. 
Setting files are stored in '/Torrents Config' subfolder of the ratiomaster.exe folder.

Localization support
----------------------------------
Starting from version 1.8 Ratiomaster supports different languages by using text unicode files.
Those files are stored in /lng subfolder of the ratiomaster.exe folder and should have an extension 'lng'.
Users are encouraged to create their own translations using english.lng as a template.



	*** Contact ***
Website: http://www.moofdev.net/
Forums: http://www.moofdev.net/forums/
Email: ratiomaster_06@yahoo.com 


	*** Requirements ***

RatioMaster requires that you've got the .NET Framework version 2 installed. 
You can get it from Microsoft:
http://download.microsoft.com/download/5/6/7/567758a3-759e-473e-bf8f-52154438565a/dotnetfx.exe


	*** How to use ***

1. Get a .torrent file associated with the tracker you want to spoof.
2. Load or Drag/Drop that file into RatioMaster.
3. Change the settings in the Options group to your liking: upload speed,
download speed (set to 0 to spoof upload only), finished (how much of the file do you 
want to appear that you have - set to 100% if you want to appear as a seeder) 
4. Choose 'Client Simulation' in Advanced Tab to be the same type as your regular torrent client. 
5. Optionally, look through the Advanced and Network tabs and see if you need anything 
changed there, like using a specific port or announcing through a proxy server. 
Most users won't need to change anything here.
6. Press the Start button and watch the bytes start rolling.
7. After a while, when you decide you've spoofed enough, press the Stop button to announce
to the tracker that you're ending your session.


	*** Things to remember ***
	
	
First of all, don't use very high upload speeds. Some trackers check sessions for very big
upload rates. Using a 6 MB/s upload rate when your IP belongs to an ISP who only has a 512
kbps plan is plain stupid. Check the moofdev forums on more info on maximum safe speeds 
reached by other users on different trackers.
Never spoof uploads on a tracker with few peers. If there are only 2 leechers and they're
downloading at a maximum of 300 kB/s, and you're spoofing an upload of 2 MB/s, it will 
look suspicious.
Keep the software up-to-date. Sometimes bugs are found that may get you banned on sites. 
RatioMaster includes an automatic version checker and will notify you when a new version 
is released. Update!
If you're going to take part in discussions on the moofdev forums, or other forums that 
deal with this sort of software, don't use the same username you use on trackers. 
We've had instances of tracker admins visiting the forums to see whether any of our users
were members on their trackers and... well, you can assume what happened next.
Read the forums. Sometimes users will report that a certain tracker simply cannot be 
fooled. It's better to stay informed than be banned on your favourite tracker.
Last, but not least, only spoof when you NEED to. By cheating on a torrent, 
you're disrupting the swarm and going against the spirit of p2p. 
Unless you really need to increase your ratio and there's no better way (short of paying 
money - pay2leech trackers are a lot worse than cheating peers), don't cheat.



	*** Copyrights and acknowledgements ***
	

RatioMaster (the software) was written by RatioMaster_06 (the person), with contributions
by JTS-UD (yes it's an acronym!).
We'd like to also thank:

	* 12345B for moderating our forums, finding important bugs in beta builds,fixing
	  my syntax errors and typos and for being a nice guy :)
	* our anonymous betatester, who intensively tested every beta, came up with ideas 
	  and also made some nice icons for us
	* Azurine, Samson and Thunder for beta testing and bug reports
	* All other people we forgot, who helped with their ideas
	
	*** License ***
	

RatioMaster
Copyright (C) 2005-2010, RatioMaster_06, moofdev.net
All rights reserved.

Redistribution and use in binary form, without modification, are permitted provided 
that the following conditions are met:

	* Redistributions must reproduce the above copyright notice, this list of 
	  conditions and the following disclaimer in the documentation and/or other 
	  materials provided with the distribution.
	* Neither the name of the author nor the names of its contributors may be used to 
	  endorse or promote products derived from this software without specific prior 
	  written permission.
	* Redistribution of modified binaries allowed only with prior written permission 
	  of the author.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS" AND ANY 
EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES 
OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. 
IN NO EVENT SHALL THE REGENTS OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, 
INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, 
PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS 
INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, 
STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF 
THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
