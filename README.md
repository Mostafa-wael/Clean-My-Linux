# Clean-My-Linux
A script to clean-up your Linux work enviroment.

1. Clone the repo.
2. Add the script into your Home.
3. Run `sudo ./clean`

Check the storage before and after!

![Script](https://user-images.githubusercontent.com/56788883/146991100-f4741c68-3769-42bc-9542-bc72a312b603.png)


The script does the following: 
- Clean all the log file.
- Clear systemd journal logs.
- Clean the thumbnail cache.
- Free up space by cleanning out the cached packages.
- Getting rid of partial packages.
- Getting rid of no longer required packages.
- Getting rid of orphaned packages.
- Remove the Trash.
- Remove Man.
- Delete all .gz and rotated file.
- Cleaning the old kernels.
- Removes old revisions of snaps(leaves only 2 versions).
- Remove Any Automatic Dependencies that are No Longer Needed with all of the associated configuration files from the dependencies.
