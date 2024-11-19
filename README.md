# LinuxInHA
Usually I create and destroy Linux VM in order to make some tests or develop stuff. I want to monitor/control them from HA

## Glances

If you just want to monitor the Linux machine, deeply monitor but without taking control of it, this is clearly the best option.

### Installation:
```
apt-get install glances
```

## Go-hass

If you want to be able to execute scripts to that machine thru HA and you dont need a deeep monitor, this is your best option.

### Installation:

Visit [go-hass official page](https://github.com/joshuar/go-hass-agent) , where you will find detailed installation instructions.

Find your package in [relases section](https://github.com/joshuar/go-hass-agent/releases) -> [At this moment was this](https://github.com/joshuar/go-hass-agent/releases/download/v10.3.2/go-hass-agent_10.3.2_amd64.deb)

```
wget https://github.com/joshuar/go-hass-agent/releases/download/v10.3.2/go-hass-agent_10.3.2_amd64.deb
dpkg -i go-hass-agent_10.3.2_amd64.deb
apt-get install -f
dpkg -i go-hass-agent_10.3.2_amd64.deb
```

Now you need some Xwindows server in order to export X11 sessions from Linux, I will say a very goos option is to install [Mobaxterm](https://mobaxterm.mobatek.net/). Just remember to activate X11 forwarding when configuring your ssh connection to the Linux machine.

![Image](MobaXtermX11FWD.PNG)

Time to start with the basic configuration, as a non root user:

```
go-hass-agent run
```

