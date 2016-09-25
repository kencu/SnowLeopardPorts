# SnowLeopardPorts
a local repository of MacPorts that are configured for Snow Leopard and shadow newer incompatible versions of ports

MacOSX 10.6 (Snow Leopard) has some incompatabilities with some of the newest ports available on MacPorts. The goal of project is to generate a local collection of portfiles and associated patches that will in some cases modify the existing portfiles to work on Snow Leopard, and in other cases will bring back older versions of ports that still work on Snow Leopard but can't easily be found in the current MacPorts portfile distribution. Snow Leopard-specific fixes to existing ports will be submitted to MacPorts for consideration into the main repository, and if these fixes are accepted, then the version in SnowLeopardPorts will no longer be required and will be removed.

Before we begin, to have any hope of keeping your Snow Leopard machine reasonably up to date with currently-available software, you need to follow the excellent instructions here <https://trac.macports.org/wiki/LibcxxOnOlderSystems> to upgrade your C++ underpinnings and your current compiler chain to something that can compile modern software. This repository assumes you have your Snow Leopard system set up in this fashion, and it's highly likely that most or all of the modifications here will not function otherwise, or other unpredictably bad things might happen.

To use a local repository, you designate a folder to be your local MacPorts repository (collection of portfiles and patches). In this case, you could go to the /opt directory, and clone the SnowLeopardPorts git repository right there `sudo git clone https://github.com/ken-cunningham-webuse/SnowLeopardPorts.git` That makes `/opt/SnowLeopardPorts` the base directory for the local repository, and when you run `sudo portindex` from inside that directory, you update the port index MacPorts uses to find the Portfiles.

Finally, you need to add the local repository to your macports sources file (usually `/opt/local/etc/macports/sources.conf`), putting your local repository AHEAD of the Macports repository:
```
file:///opt/SnowLeopardPorts
rsync://rsync.macports.org/release/tarballs/ports.tar [default]
```
Then, when you look for ports, macports will find the SnowLeopardPorts portfiles before the official MacPorts portfiles. That's how this process works. Other port searches and requests will pass through tigerports and use the full untouched MacPorts repository.

Here are some instructions from the macports website <https://guide.macports.org/chunked/development.local-repositories.html>. The only thing I'd update in these instructions is to use `/opt/SnowLeopardPorts` due to permissions issues, but you can use other locations as well if you need to (like `/Users/Shared/SnowLeopardPorts`, for example).

You might wonder why there are not very many ports in SnowLeopardPorts -- and that is because in general, almost all of the 20,000 ports on MacPorts "just work" and don't need to be replaced with older versions or modified to work on Snow Leopard. You will be surprised, I think how many current versions of software compile and run very nicely on Snow Leopard just "out of the box". 

Some examples of what is in TigerPorts:

```
aria2 --> high-speed downloader, modified to work on Snow Leopard
glfw @3.12 --> last version that compiles and runs on Snow Leopard
```
If you have any contributions to make to this collection, please feel free to add, suggest, or put in a pull request!
