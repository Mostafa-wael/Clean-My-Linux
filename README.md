# Clean-My-Linux
A script to clean-up your Linux work enviroment.

1. Clone the repo.
2. If you used the download options:
  - Go to the downloads: `cd ~/Downloads/`
  - Unzip the file: `unzip Clean-My-Linux-main.zip`
3. Go to the script: `cd Clean-My-Linux-main`
4. Give the script the required permissions: `chmod u+x clean`
5. Add it to your binaries: `sudo cp ./clean /usr/local/bin`
6. To solve some permission issues: `sudo chown -R $(whoami) /usr/local/bin/clean`
7. Finally, run: `sudo clean`

Check the storage before and after!

![Script](https://user-images.githubusercontent.com/56788883/146991100-f4741c68-3769-42bc-9542-bc72a312b603.png)


The script does the following: 
- Clean all the log files.
- Clean systemd journal logs.
- Clean the thumbnail cache.
- Free up space by cleaning out the cached packages.
- Getting rid of partial packages.
- Getting rid of no longer required packages.
- Getting rid of orphaned packages.
- Remove the Trash.
- Remove Man.
- Delete all .gz and rotated file.
- Cleaning the old kernels.
- Removes old revisions of snaps(leaves only 2 versions).
- Remove Any Automatic Dependencies that are No Longer Needed with all of the associated configuration files from the dependencies.
