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
```
