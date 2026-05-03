# Introduction
Performs a hourly scan and scan on boot for any conflict files in multiple syncthing shared directories.
Sends a desktop push notification when a conflict has been found.

## Manual installation instructions
Ensure `notify-send` is installed with `notify-send -v` and install it if necessary (e.g. `sudo apt install libnotify-bin`).
Place the timer and service units in `~/.config/systemd/user/` and create that directory if needed\
Edit script and provide root directories of syncthing folders that need to be tracked\
For example: `SYNCTHING_DIRS=("~/my-syncthing-default-folder" "~/my-syncthing-special-folder")`\
Ensure that script has executable rights (chmod +x)\
Place the shell script in /usr/local/bin/\
Reload systemd with systemctl daemon-reload\
Start the timer with systemctl --user start syncthing-conflict-notifier.timer\
Or enable it by default with systemctl --user enable syncthing-conflict-notifier.timer\
