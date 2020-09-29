# WWM
Watermelon Window Manager (WWM) - A fork of the InstantWM, A refreshing window manager, fast, tiled, and Vim-inspired.

InstantWM is a very excellent window manager. To me, it is the best in terms of functionality. However, I have a very short memory and key combinations involving Shift, Alt, Super, and Ctrl are just so easy to forget. Of course I have also some idea of my own on how window managers should be.

# Two Modes of Operation
Just like Vim, WatermelonWM has 2 modes of operation - Normal and Insert. Under Normal, there is also the ex mode.

# Normal Mode
You enter the Normal mode via **Win-Esc**,or **Win-\[** (similar to vim when going to normal mode) or even **Win-j**. You want to easily go into this mode and hence, we want key combinations that are easy to type.

You use this mode to navigate among various windows. **Alt-Tab** still works, but it will be limited to last 3 chosen windows or window groups. Vim navigation keys **hjkl** as well as **up**, **down**, **left**, **right** arrows allows you to go from one window to the next adjacent window. **G** gets you to the last line, **gg**, to the first line, **w** to skip 2 windows, **^** or **B** to go to first window in the line, **$** or **E** to the last window on the line. **Ctrl-F** let you jump 4 lines at a time. **H**, **L**, **M** also works as expected.

When you enter the normal mode, all windows are made visible and tiled  like a grid to show them all. A row correspond to the line mentioned in the previous paragraph.

When in normal mode, you could "mark" windows via m and upon hitting Enter or i or a those marked windows are grouped together and tiled. The rest goes to the background. This would allow you to mix and match windows together. You will also be promped for a name for this window group.

A window could be grouped with other windows repeatedly.

Pressing **x** closes the focused window or all marked windows

**/wordx** will search for the windows with **wordx** in its name. You could also seach grouped windows this way.

While in normal mode, typing **:command** will let you do some more things. 

**:sp** will split grouped windows into their individual windows

# Insert Mode
You get into insert mode when you hit **enter** while in normal mode or hit **i** or **a** (again just like in vim)

You could still go from one window to the next while in insert mode via **Ctrl-hjkl**. If you are in tmux+vim teminal, it will only jump to the next window if you are at the edge of the pane; otherwise, it will just move around the panes.

When several windows are tiled, pressing **Win--** (i.e. **Win** and **minus** pressed together) will detach the focused window from the group and place it in the background. Pressing **Win-+** will allow you to add more windows to the current tiles. **Win-+** will get you to normal mode to allow you to select another window (individually or as a group via **m**) and add it to the current tiles after pressing **Enter** or **i** or **a**. Of course, if the application is not yet running, you just have to run it and it will automatically tiled to your current visible windows.



Window resizing is possible only when in "insert" mode and there is 2 or more windows tiled. A single window will simply be maximized. A window that is part of a tiled display may be maximized by pressing Win-z while focused. Pressing Win-z again will unmaximize it and returned to it's former position in the tile.

