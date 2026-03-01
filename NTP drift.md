[[NTP]] can drift overtime hence why it's recommended to have more than 1 NTP server to sync from

Use `ntpstat` command to check if the ntp is drifted or not. It shows the "time correct to within" which is the **root dispersion + root delay / 2**

Use `ntpq -c -rl` to display root dispertion

To check for drift (also to check what time the server is): 
- `cat /var/lib/ntp/drift` (CentOS)
- `/var/db/ntp.drift` (MacOS)
- check `ntp.conf` file (`/etc/ntp.conf`)

NTP Drift file unit is in parts per million (PPM) where

`1 PPM = 1 part per million = 1 microsecond per second = 3.6ms per hour = 86.4ms per day`

https://serverfault.com/questions/184257/seemingly-poor-quality-of-ntp-time-synchronization-using-a-gps-clock/184442#184442

If the NTP has been drifted, one approach is to run `ntpdate` or to restart the ntpd service `service ntpd restart`. By default NTP will self-correct, but if the skew is too large, NTP won't be able to self-correct and manual intervention is required (run `ntpdate` or restarting `ntpd` service)
- Once `ntpd` is stopped, run `ntpdate <time server name/ip>`
- After that start `ntpd` service again
