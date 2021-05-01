# MOTD

Scripts for Message Of The Day for Linux ssh and terminal.

Based on https://github.com/RIKRUS/MOTD

## Changes

- Kept only general system information scripts
- No need of manual configuration to get available mount points
- List of services can be configured outside from the script for easier deployment to different machines
- Removed bashism

## Installation

```sh
rsync -avz * --exclude README remote-server.com:tmp/motd/
ssh remote-server.com
sudo cp 40-services 30-hdd-free 20-sysinfo /etc/update-motd.d
```

## Configuration

Create the file /etc/update-motd/.services where each line should be a name of a service.
For the list of services see the output of `systemctl`.

For example:
```sh
echo "nginx\npostgresql" | sudo tee /etc/update-motd/.services
```
