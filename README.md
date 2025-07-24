# Application

[Resilio-Sync](https://www.resilio.com/individuals/)

## Description

Resilio Sync (formerly BitTorrent Sync) by Resilio, Inc. is a proprietary
peer-to-peer file synchronization tool available for Windows, Mac, Linux,
Android, iOS, Windows Phone, Amazon Kindle Fire and BSD. It can sync files
between devices on a local network, or between remote devices over the Internet
via a modified version of the BitTorrent protocol.

Although not touted by the developers as an intended direct replacement nor
competitor to cloud-based file synchronization services, it has attained much of
its publicity in this potential role.This is mainly due to the ability of
Resilio Sync to address many of the concerns in existing services relating to
file storage limits, privacy, cost, and performance.

## Build notes

Latest GitHub stable release from Arch Linux AUR.

## Usage

```bash
docker run -d \
    -p 8888:8888 \
    -p 55555:55555 \
    --name=<container name> \
    -v <path for media files>:/media \
    -v <path for config files>:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e HEALTHCHECK_COMMAND=<command> \
    -e HEALTHCHECK_ACTION=<action> \
    -e UMASK=<umask for created files> \
    -e PUID=<uid for user> \
    -e PGID=<gid for user> \
    binhex/arch-resilio-sync
```

Please replace all user variables in the above command defined by <> with the
correct values.

## Access application

`http://<host ip>:8888`

## Example

```bash
docker run -d \
    -p 8888:8888 \
    -p 55555:55555 \
    --name=resilio-sync \
    -v /media:/media \
    -v /apps/docker/resilio-sync:/config \
    -v /etc/localtime:/etc/localtime:ro \
    -e UMASK=000 \
    -e PUID=0 \
    -e PGID=0 \
    binhex/arch-resilio-sync
```

## Notes

User ID (PUID) and Group ID (PGID) can be found by issuing the following command
for the user you want to run the container as:-

```bash
id <username>
```

___
If you appreciate my work, then please consider buying me a beer  :D

[![PayPal donation](https://www.paypal.com/en_US/i/btn/btn_donate_SM.gif)](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=MM5E27UX6AUU4)

[Documentation](https://github.com/binhex/documentation) | [Support forum](https://forums.unraid.net/topic/103784-support-binhex-resilio-sync/)
