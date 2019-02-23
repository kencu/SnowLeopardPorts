# SnowLeopardPorts
A local repo of ports configured for 10.6 Snow Leopard and either shadow newer, incompatible versions of ports or are modified to work on Snow Leopard.

This port repository is most compatible with an installation of 10.6.8 that is configured with LibcxxOnOlderSystems via MacPorts. This setup is the most comparable to newer MacOS systems which all use libc++ and clang. I use it with my default compiler set to macports-clang-5.0 in macports.conf.

Some Portfiles may require the MacOS10.7.sdk to build against. This should be placed in your SDK folder, next to the other SDKs there.

Previously this repo contained specially enhanced versions of clang that allowed better defaulting and thread_local storage on 10.6 and less. These changes have all been moved into MacPorts now, so are no longer needed here.


