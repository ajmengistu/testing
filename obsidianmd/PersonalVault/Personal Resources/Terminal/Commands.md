# Terminal Commands
- Search for a specific string in all the files in computer
	- `rg -i "hello world"`
	- https://github.com/BurntSushi/ripgrep/blob/master/GUIDE.md
- Open gnome-terminal inside tmux
	- `gnome-terminal`
- Check if an apt-get package is installed
`dpkg -s <package-name>`
- extract tar file
````
tar –xvzf documents.tar.gz
````
-   **`x`** – instructs tar to extract the files from the zipped file
-   **`v`** – means verbose, or to list out the files it’s extracting
-   **`z`** – instructs **tar** to decompress the files – without this, you’d have a folder full of compressed files
-   **`f`** – tells **tar** the filename you want it to work on

- find a process by name
	- via GUI
		- Open System Monitor app and search name of process, ex: copyq or firefox, under the Processes tab
	- via Terminal
		- ``` pgrep firefox or copyq - list all processes whose command match firefox ```
		- ``` pidof firefox or copyq - list all processes whose command match firefox BUT list all ids in one line```
- Kill multiple processes by name
	- `kill $(pgrep copyq)`

- Run Chron Cron jobs
	- Open Cron tab to write Cron jobs
		- `Crontab -e`  and follow commented directions in the file.
	- View Cron job log by running system log and highlighting logs that ran cron jobs
		- `grep CRON /var/log/syslog`
		- https://crontab.guru/examples.html