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

There are 2 options for `Critical Mode`. When CRITICAL_HIBERNATE is set, `critical mode` will automatically hibernate the system when the battery capacity drops below the `CRITICAL` value; otherwise it only shows a warning message.
