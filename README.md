# PowerNot

Power notification tool for i3 window manager.

## Configuration

You can configure some settings by manually editing the `powernot` file.

### Modes

There is 4 modes in powernot.

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

- TIMER (current timer depending on current battery state)
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

Every mode has different sleeping timers. You can change them by editing the `powernot` file.

### CRITICAL_HIBERNATE

```
CRITICAL_HIBERNATE=1
```

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
