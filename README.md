# SnowLeopardPorts
A local repo of ports configured for 10.6 Snow Leopard and either shadow newer, incompatible versions of ports or are modified to work on Snow Leopard.

This port repository is most compatible with an installation of 10.6.8 that is configured with LibcxxOnOlderSystems via MacPorts. This setup is the most comparable to newer MacOS systems which all use libc++ and clang.

A few special modifications have been made. clang-3.9, clang-4.0, and clang-5.0 have been slightly modified to default to adding -stdlib=libc++ if no stdlib is specified on the command line. This is identical to the behaviour of newer systems.

clang-5.0 has been slightly modified to allow thread_local storage, similar to newer systems 10.7+. This is done using internal clang mechanisms, using emutls.c, and enabling this on 10.6 and earlier.

Some Portfiles may require the MacOS10.7.sdk to build against. This should be placed in your SDK folder, next to the other SDKs there.


