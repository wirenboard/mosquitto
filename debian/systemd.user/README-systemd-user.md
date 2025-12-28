
# Running mosquitto as a systemd user service

## Basic commands

Since 2.0.22-4 the mosquitto service packaged by Debian can be run as a user.
The service is enabled for the current user with 
```
systemctl --user enable mosquitto
```
and can then be started with 
```
systemctl --user start mosquitto
```
All other service commands can be given as expected.


## Configuration

On first startup a default configuration is created in 
`~/.config/mosquitto/mosquitto.conf`. For security reasons the created 
configuration only lets mosquitto listen on the unix domain socket
`/run/user/<uid>/mosquitto/mosquitto.socket`.

