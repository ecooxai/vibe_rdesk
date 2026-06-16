# Instructions

After finishing each task, rebuild and run or stop and restart this WM at `:11`. It has an X server started there. When testing GUI, use `xdotool` at `:11` too.

When the current method does not work in the application, do not automatically fall back to another method. Always show an error prompt and let the user choose whether to fall back.

# Linux Computer Use

First get current screenshot, then control Linux via `xdotool`. Only use the following `xdotool` commands to avoid misuse.

## First Get Screen Info

```sh
xdotool getdisplaygeometry
```

## Allowed Commands

Do not put any other command after `type`; only put text. It only accepts text.

```sh
xdotool type "text"
```

Type keys at the same time:

```sh
xdotool key ctrl+shift+a
```

Always put `keyup` after `keydown`:

```sh
xdotool keydown shift a keyup shift
```

Always put `mouseup` after `mousedown`:

```sh
xdotool mousemove 200 300
xdotool mousemove 200 220 click 1
```

Use this for mouse drag. It needs `sleep 1` to drag correctly:

```sh
xdotool mousedown 1 sleep 1 mousemove 300 100 mouseup 1
```

Right mouse:

```sh
xdotool mousedown 3 mouseup 3
```

Reset script if keys get stuck. Always reset after finishing a step:

```sh
xdotool keyup super keyup ctrl keyup alt keyup shift mouseup 1 mouseup 2
```
