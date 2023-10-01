# Clean-My-Linux
A script to clean-up your Linux work enviroment.

1. Clone the repo: `git clone https://github.com/Mostafa-wael/Clean-My-Linux.git`
2. Go to the script: `cd Clean-My-Linux/`
3. Give the script the required permissions: `chmod u+x clean`
4. Add it to your binaries: `sudo cp ./clean /usr/local/bin`
5. To solve some permission issues: `sudo chown -R $(whoami) /usr/local/bin/clean`
6. Finally, run: `sudo clean`

Check the storage before and after!

![Script](https://user-images.githubusercontent.com/56788883/146991100-f4741c68-3769-42bc-9542-bc72a312b603.png)
![Updated Version](https://github.com/Mostafa-wael/Clean-My-Linux/assets/56788883/6dc556cc-afe0-483d-b003-cdd00781d55d)


The script does the following: 
- Clean all the log files.
- Clean systemd journal logs.
- Clean the thumbnail cache.
- Free up space by cleaning out the cached packages.
- Getting rid of partial packages.
- Getting rid of no longer required packages.
- Remove Any Automatic Dependencies that are No Longer Needed with all of the associated configuration files from the dependencies.
- Getting rid of orphaned packages.
- Remove the Trash.
- Remove Man.
- Delete all .gz and rotated file.
- Cleaning the old kernels.
- Removes old revisions of snaps(leaves only 2 versions).

Enjoy the free space!
