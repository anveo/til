
# Synology


### Crashplan

    $ ssh admin@ecto
    $ cat /var/lib/crashplan/.ui_info; echo

On desktop:

    $ sudo vim /Library/Application\ Support/CrashPlan/.ui_info

Replace with output from above, adjust IP address to be address of the Synology server.
