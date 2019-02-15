# PowerNot

Power notification tool for i3 window manager.

## Configuration

You can configure tool with manually editing `powernot` file.

### Modes

There is 4 modes in tool.

- Charging Mode
- Discharging Mode
  - Safe Mode
  - Danger Mode
  - Critical Mode

This mode switches handling with percentage of remaining battery.

```
SAFE=30
DANGER=15
CRITICAL=5
```

### Timers

- TIMER (Discharging default timer)
- CHARGING_TIMER (Charging timer)
- SAFE_TIMER (Discharging safe mode timer)
- DANGER_TIMER (Discharging danger mode timer)
- CRITICAL_TIMER (Discharging critical mode timer)

```
TIMER=5
CHARGING_TIMER=10
SAFE_TIMER=5
DANGER_TIMER=2
CRITICAL_TIMER=1
```

Every mode have different timers for sleeping process. You can change this
settings with editing `powernot` file.

### Safe Exit

```
SAFE_EXIT=1
```

There is 2 options for `Critical Mode`. When safe exit is enabled,
`critical mode` only shows message; otherwise its `hibernate` system
directly.

### Using powernot as a systemd service
Systemd's user mode can be used to autostart and run `powernot` in the background.

First, create a `service` file in `~/.config/systemd/user/powernot.service`. Make sure to replace `USERNAME` with your actual username.

```
$ cat ~/.config/systemd/user/powernot.service
[Unit]
Description=powernot

[Service]
ExecStart=/home/USERNAME/git/powernot/powernot

[Install]
WantedBy=default.target
```

Enable the service if you want the service to be autostarted:
```
systemctl --user enable powernot.service
```

You can also manually start the service (if it has not been autostarted already):
```
systemctl --user start powernot.service
```

To check the current status of the service, run:
```
systemctl --user status powernot.service
```
