# WWM
Watermelon Window Manager - A fork of the InstantWM, A refreshing window manager, fast, tiled, and Vim-inspired.

InstantWM is a very excellent window manager. To me, it is the best in terms of functionality. However, I have a very short memory and key combinations involving Shift, Alt, Super, and Ctrl are just so easy to forget. So I decided to change them to be as close to vim workflow which is almost second nature to me.Windows will be treated like letters in vim, with window titles treated like words that could be searched. Since I also use windows a lot, I decided to use similar mouse gestures.  With the mouse, windows will be treated like a file system where you use Ctrl-Select to select several non-adjacent windows. And of course, many of InstantOS characteristics will be retained as well.

## Design Principles


Do not touch the vim/tmux key bindings. Anything that is directed to the window manager will be preceeded with the windows (Super) key, followed by nearest vim equivalent.

I am vim user. The combination of vim and tmux is indespensable in my coding work. Therefore usage/navigation will revolve on that and will be the starting point. When you are inside tmux/vim, you have split screen and moving around is handled by Ctrl-hjkl. (See my tmux and vim dot files here). It does not matter whether you are inside vim or tmux. You use the same key combination to move around. Now, we will extend that to other windows. Once you reach the edge of tmux/vim window, Ctrl-hjkl will jump the focus on the adjacent window (and in "insert" mode; see below).

The watermelon window manager has 2 modes, just like in vim. Since ESC is being used by vim, Win-Esc will bring it to "Normal" mode. when in normal mode, all windows and grouped windows will show up (just like expose). Other users replaced Esc with "jj"; Win-jj and Win-\[ would work too. You jump or navigate from one open window to another via hjkl (one adjacent window at a time) or gg (the first) or G (the last) or H (top line) or M (middle line) or L (lowest line) or w (skip 2 adjacent window) or /word (window containing "word" in title) - similar to vim!. Once you are focused on the window that you like, any of the following actions are possible:

    -  press "i" or "a" or Enter to go to "insert" mode, which allows you to work on that window (or grouped window), and would occupy the entire display real estate.
    -  press "x" and that "deletes" or exits that window (or grouped window).
    -  press "m"(followed by another letter, except hjkl or gg or G or H or M or L or w, which will move the focus somewhere else, nor i or a which meant you are done marking and would like the marked windows to be on the foreground) to mark that window, with the intention to mark another one, forming a grouped window. They are now grouped together and tiled to occupy the entire screen real estate. To clarify, use "m" on a focused window to mark it, to to another window and mark it as well, and go to yet another window to mark that too. When you hit "i", or "a" or Enter (which brings you to the "insert" mode), you will be promped for a name for that window group to make it searchable with "/word". If you don't input anything on the prompt and simply hit enter, the window manager will assign something for you.
    -  type ":sp" to split the grouped windows (previously grouped via the "m" action) into their individual windows
    -  type "/word" to search a particular window with "word" in its title or named grouped window. Tab will move it to pre-filtered search result.

Window resizing is possible only when in "insert" mode and there is 2 or more windows tiled. A single window will simply be maximized. A window that is part of a tiled display may be maximized by pressing Win-z while focused. Pressing Win-z again will unmaximize it and returned to it's former position in the tile.

