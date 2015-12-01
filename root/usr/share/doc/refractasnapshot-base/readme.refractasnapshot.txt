v. 9.0.9
Refracta Snapshot creates a bootable live-CD image which is a copy of
your running system. Any changes you make to the running system, 
including desktop preferences, configuration changes, or added software
will be copied to the snapshot and will be present when you run that
snapshot as a live system.

See the config file, /etc/refractasnapshot.conf for setting options.

See the excludes file, /usr/lib/refractasnapshot/snapshot_exclude.list
to examine which files and directories will not be copied to the 
snapshot. Edit the file as needed, either by adding items or commenting
out listed items that you want copied.

As of version 9.0.8, you can edit the config and excludes files from
within the gui program by choosing "Setup".

To run the script:

	refractasnapshot
or
	refractasnapshot-gui
	
or use the full path if needed:
	/usr/bin/refractasnapshot(-gui)
	
	
COMMAND LINE OPTIONS

	-h, --help		show help
	-v, --version	display the version information
	-n, --nocopy	don't re-copy a saved filesystem copy (bypass rsync)
	-c, --config	specify a different config file
					(file name must be next argument)

Note: The nocopy option is NOT the same as setting save_work="yes" in 
the config file. $save_work will allow rsync to update the saved copy 
with any recent changes without having to copy the entire system again. 
Its purpose is to save time when making a snapshot.

The nocopy option will prevent rsync from updating the saved copy of the
filesystem. Any system changes or updates that occurred after the copy 
was made will not be included in the final image.

The nocopy option is for special purposes (for example, you made changes
to the saved copy of the filesystem after a previous snapshot, and you 
don't want those changes overwritten by the running system.) 
However, you must have save_work=yes and have a previously saved copy of
the filesystem for nocopy to work.

