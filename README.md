# fzf-nova
- using terminal emulator + fzf as a script launcher, replacement for dmenu or rofi
- demo https://www.youtube.com/watch?v=8SqakfCSzQk

#### pick a terminal command to bind to a hotkey (e.g super+space):
    
    ## source bashrc to get $PATH and $EDITOR variable
    # if fzf-nova is NOT in your $PATH then include the script location
    xterm -T fzf-nova -geometry 120x20+300+300 -fs 14 -e bash -c "source ~/.bashrc &>/dev/null && /path/to/fzf-nova"
    xfce4-terminal --title fzf-nova --geometry 120x20+350+300 --font 14 --execute bash -c "source ~/.bashrc &>/dev/null && /path/to/fzf-nova"
    alacritty -T fzf-nova -o "window.dimensions.columns=90" "window.dimensions.lines=20" "window.position.x=350" "window.position.y=200" -e bash -c "source ~/.bashrc &>/dev/null && /path/to/fzf-nova"
    
    # if fzf-nova is already in your bash $PATH
    xterm -T fzf-nova -geometry 120x20+300+300 -fs 14 -e bash -c "source ~/.bashrc &>/dev/null && fzf-nova"
    xfce4-terminal --title fzf-nova --geometry 120x20+350+300 --font 14 --execute bash -c "source ~/.bashrc &>/dev/null && fzf-nova"
    alacritty -T fzf-nova -o "window.dimensions.columns=90" "window.dimensions.lines=20" "window.position.x=350" "window.position.y=200" -e bash -c "source ~/.bashrc &>/dev/null && fzf-nova"

#### for TMUX users (prefix + TAB to activate popup)
    bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "fzf-nova"
    or
    bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "/path/to/fzf-nova"

#### add your own script
- just drop in a script in the same folder as fzf-nova.
- name it e.g: _myamazingscript,--.a.cool.description

#### showcase
- radiomhysa:       https://youtu.be/yfREdXs4H5o
- clipmenu:         https://youtu.be/9-4boJ9krsY
- zinger:           https://youtu.be/YGsq4ogwmBk
- reverbeats:       https://youtu.be/eANLqIhOgWw

### author
- gotbletu (@youtube|github|odysee)
- https://www.youtube.com/user/gotbletu

