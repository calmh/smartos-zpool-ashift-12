zpool with ashift=12
====================

This is the regular zpool binary from SmartOS `joyent_20140207T053435Z`,
compiled so that `zpool create` always uses ashift=12 for all vdevs.
This can be used to create such pools with 512 byte sector devices for
the purpose of enabling future replacement with 4096 byte sector
devices.

Note that there are caveats around efficient disk usage when using RAIDZ
variants with ashift=12 pools. Mirroring is nice.

This can also be used to create pools with devices that lie about their
sector size, but seriously just throw them away instead.
