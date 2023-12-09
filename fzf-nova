#!/usr/bin/env sh
# author: gotbletu (@youtube|github|odysee)
#         https://www.youtube.com/user/gotbletu
# desc:   terminal emulator + fzf to launch scripts, a replacement for dmenu or rofi
# demo:   https://youtu.be/8SqakfCSzQk
# depend: fzf findutils coreutils util-linux
# reff:   xterm config https://www.youtube.com/watch?v=mAUQsNUnk9I
# note:   to add your own, just drop in a script in the same folder as fzf-nova.
#         name it e.g: _myamazingscript,--.a.cool.description

#### source shellrc to get $PATH and $EDITOR variable
#### if fzf-nova is already in your $PATH then you dont have to put point /path/to/...etc.
#### pick a terminal command to bind to a hotkey (e.g super+space):
 
## if fzf-nova is NOT in your $PATH then include the script location
# xterm -T fzf-nova -geometry 120x20+300+300 -fs 14 -e bash -c "source ~/.bashrc &>/dev/null && /path/to/fzf-nova"
# xfce4-terminal --title fzf-nova --geometry 120x20+350+300 --font 14 --execute bash -c "source ~/.bashrc &>/dev/null && /path/to/fzf-nova"
# alacritty -T fzf-nova -o "window.dimensions.columns=90" "window.dimensions.lines=20" "window.position.x=350" "window.position.y=200" -e bash -c "source ~/.bashrc &>/dev/null && /path/to/fzf-nova"

## if fzf-nova is already in your bash $PATH
# xterm -T fzf-nova -geometry 120x20+300+300 -fs 14 -e bash -c "source ~/.bashrc &>/dev/null && fzf-nova"
# xfce4-terminal --title fzf-nova --geometry 120x20+350+300 --font 14 --execute bash -c "source ~/.bashrc &>/dev/null && fzf-nova"
# alacritty -T fzf-nova -o "window.dimensions.columns=90" "window.dimensions.lines=20" "window.position.x=350" "window.position.y=200" -e bash -c "source ~/.bashrc &>/dev/null && fzf-nova"

## for TMUX users (prefix + TAB to activate popup)
# bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "fzf-nova"
# or
# bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "/path/to/fzf-nova"

export FZF_DEFAULT_OPTS="-e -i -d '_' --with-nth 2.. --info=hidden --layout=reverse --scroll-off=5 --tiebreak=index --bind 'home:first,end:last,tab:down,shift-tab:up'"
mydir="${0%/*}"
selected="$(
  find "$mydir" -type f -name '_*' -exec basename {} \; \
  | sort | sed 's@\.@ @g' | column -t -s ',' \
  | fzf --prompt='fzf-nova: ' | cut -d ' ' -f1
  )"
[ -z "$selected" ] && exit
eval "${mydir}/${selected},*"
