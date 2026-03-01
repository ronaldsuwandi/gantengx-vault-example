NTP synchronises time with ntp server to keep time in sync. There are number of free public NTP server to synchronise from. [Google](https://developers.google.com/time) is one of the free provider. However Google NTP server does not provide leap seconds, it uses [leap smear](https://developers.google.com/time/smear) approach instead

NTP stratums
- stratum 0 is the server with the atomic clock
- stratum 1 are the ones that are connected to it - not public
- stratum 2 are servers synced with stratum 1 ones
- stratum 3 are synced with stratum 2 ones

## See also
- [[NTP drift]]
- [[NTP root dispersion]]