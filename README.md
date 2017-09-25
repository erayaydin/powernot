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
SAFE=55
DANGER=54
CRITICAL=53
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
