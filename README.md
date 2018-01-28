# wordpress-perms

Sets some sensible permissions on a wordpress install. 

Makes a couple of assumptions:

* Apache runs as `www-data`
* Site is hosted in `/home/<user>/*/`, where '<user>' needs local write access.

By default, doesn't do anything, just prints a series of commands.

    root@host:/home/avi/wordpress# wordpress-perms .
    # Not running commands, just printing
    # use -r to run the commands
    mkdir /home/avi/wordpress/./wp-content/uploads
    chown avi:www-data /home/avi/wordpress/. -R
    find /home/avi/wordpress/. -type f -exec chmod 740 {} \;
    find /home/avi/wordpress/. -type d -exec chmod 750 {} \;
    chmod u+s,g+rws /home/avi/wordpress/./wp-content/uploads -R
    chmod a+x,g+x /home/avi/wordpress/.
    root@host:/home/avi/wordpress# 
