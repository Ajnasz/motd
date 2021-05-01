# MOTD

Scripts for Message Of The Day for Linux ssh and terminal.

Based on https://github.com/RIKRUS/MOTD

## Changes

- Kept only general system information scripts
- No need of manual configuration to get available mount points
- List of services can be configured outside from the script for easier deployment to different machines
- Removed bashism

## Installation

Copy the scripts to the /etc/update-motd.d/ folder.

```sh
rsync -avz * --exclude README remote-server.com:tmp/motd/
ssh remote-server.com
cd downloads/motd
sudo cp * /etc/update-motd.d/
```

## Configuration

Create the file /etc/update-motd/.services where each line should be a name of a service.
For the list of services see the output of `systemctl`.

For example:
```sh
echo "nginx\npostgresql" | sudo tee /etc/update-motd/.services
```
