# Snake in Ak

A small Snake game written in [Ak](https://github.com/notyourbusinessss/AI-codinglanguage-), drawn in Ak's own window: its pure-Ak X11 client and software canvas, no GUI library and no browser.

## Run it
You need `ak` 0.6.0 or newer (Linux x86-64) and an X11 or XWayland display.

    ak snake.aklang

| Key | Action |
| --- | --- |
| arrows or WASD | steer (turning back onto yourself is ignored) |
| space | pause / continue |
| enter or n | start over |
| q or esc | quit |

The snake speeds up as it eats. The best score is kept while the window is open.

## Layout
- `snake.aklang`: the window, drawing and input loop (idle and paused cost 0 CPU: the loop sleeps in `gui_event`).
- `snake/logic.aklang`: the rules as pure functions (`fresh`, `turn`, `step`, `place`), no window and no randomness of their own.
- `snake/logic.test.aklang`: tests for the rules, run with `ak test .`
- `lib/`: Ak's `x11.aklang`, `canvas.aklang` and font data, copied unchanged from the Ak repository (font licence in `lib/FONT-LICENSE.txt`).
