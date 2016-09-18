# SnowLeopardPorts
a local repository of MacPorts that are configured for Snow Leopard and shadow newer incompatible versions of ports

MacOSX 10.6 (Snow Leopard) has some incompatabilities with some of the newest ports available on MacPorts that cannot be repaired in the existing MacPorts heirarchy. The goal of project is to generate a "local repository" of portfiles and associated patches that will in some cases modify the existing portfiles to work on Snow Leopard, and in other cases will bring back older versions of ports that still work on Snow Leopard but can't easily be found in the current MacPorts portfile distribution.

Before we begin, to have any hope of keeping your Snow Leopard machine reasonably up to date with currently-available software, you need to follow the excellent instructions here <https://trac.macports.org/wiki/LibcxxOnOlderSystems> to upgrade your C++ underpinnings and your current compiler chain to something modern. This repository assumes you have your Snow Leopard system set up in this fashion, and it's highly likely that most or all of the modifications here will not function otherwise, or other unpredictably bad things might happen.


To use a local repository, you designate a folder to be your local MacPorts repository (collection of portfiles and patches). Then you index them using "sudo portindex" from the base directory. I use "/opt/myports" as the base directory for my local repository, and run "sudo portindex" from that directory.

Finally, you need to add the local repository to your macports sources file (usually "/opt/local/etc/macports/sources.conf"), putting your local repository AHEAD of the Macports repository:

-----
file:///opt/myports
rsync://rsync.macports.org/release/tarballs/ports.tar [default]
--------

Then, when you look for ports, you will find your own local portfiles before you find the official macports portfiles. That's how this process works.
