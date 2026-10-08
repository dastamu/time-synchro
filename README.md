# time-synchro
>How to use time synchronization

## Ubuntu 22.04
```sh
sudo nano /etc/systemd/timesyncd.conf
'
[Time]
NTP=194.146.251.100 194.146.251.101
'
sudo systemctl restart systemd-timesyncd.service

sudo timedatectl set-ntp on
sudo timedatectl set-timezone Europe/Warsaw

timedatectl
'              Local time: czw 2026-10-08 11:16:23 CEST
           Universal time: czw 2026-10-08 09:16:23 UTC
                 RTC time: czw 2026-10-08 09:16:23
                Time zone: Europe/Warsaw (CEST, +0200)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no'
```
## EL 9
```sh
sudo nano /etc/chrony.conf
'
server 194.146.251.100 iburst
server 194.146.251.101 iburst
'
sudo systemctl restart chronyd

sudo timedatectl set-ntp true
sudo timedatectl set-timezone Europe/Warsaw

sudo chronyc makestep # synchro now
chronyc sources -v
chronyc tracking
timedatectl
'              Local time: czw 2026-10-08 11:37:29 CEST
           Universal time: czw 2026-10-08 09:37:29 UTC
                 RTC time: czw 2026-10-08 09:37:29
                Time zone: Europe/Warsaw (CEST, +0200)
System clock synchronized: yes
              NTP service: active
          RTC in local TZ: no'
```
