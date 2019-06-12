#!/bin/sh

# Set environment
export BSPWM_CONFIG="${XDG_CONFIG_HOME:-$HOME/.config}/bspwm"

# Function to kill programs
killprogs() {
	# Kill udisks-glue
	pkill -x udisks-glue
	# Kill panel
	pkill -x panel
	# Kill Redshift
	pkill -x redshift
}

# Restart function
# shellcheck source=/dev/null
restart() {
	# Save session status
	. "$BSPWM_CONFIG/restore.cfg"
	bspc wm --dump-state > "$BSPWM_STATE"
	# Kill programs
	killprogs
	# Quit bspwm
	bspc quit 0
}

# Logout function
logout() {
	# For each opened window
	bspc query --nodes | while read -r winid; do
		# Close it
		xdotool windowkill "$winid"
	done
	# Kill programs
	killprogs
	# Quit bspwm
	bspc quit 1
}

# Load dmenu config
# shellcheck source=/dev/null
[ -f "$HOME/.dmenurc" ] && . "$HOME/.dmenurc" || DMENU='dmenu -i'

# Menu items
items="restart
logout
hibernate
suspend
reboot
poweroff"

# Open menu
selection=$(printf '%s' "$items" | $DMENU)

case $selection in
	restart)
		restart
		;;
	logout)
		logout
		;;
	hibernate)
		systemctl hibernate
		;;
	suspend)
		systemctl suspend
		;;
	reboot)
		logout
		systemctl reboot
		;;
	halt|poweroff|shutdown)
		logout
		systemctl poweroff
		;;
esac

exit
