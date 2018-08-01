# supervosor--configuration

Creating a Configuration File

first change system on root 

Once the Supervisor installation has completed, run echo_supervisord_conf. This will print a “sample” Supervisor configuration file to your terminal’s stdout.

Once you see the file echoed to your terminal, reinvoke the command as echo_supervisord_conf > /etc/supervisord.conf. This won’t work if you do not have root access.

If you don’t have root access, or you’d rather not put the supervisord.conf file in /etc/supervisord.conf, you can place it in the current directory (echo_supervisord_conf > supervisord.conf) and start supervisord with the -c flag in order to specify the configuration file location.

For example, supervisord -c supervisord.conf. Using the -c flag actually is redundant in this case, because supervisord searches the current directory for a supervisord.conf before it searches any other locations for the file, but it will work. See Running Supervisor for more information about the -c flag.

also uncomment  this section in supervisor.conf 

    [include]
    files = relative/directory/*.ini
    
    
and make files with *.ini  in(relative/directory/) and put task in them.
after taht 

    service supervisord restart
and 

     supervisorctl reread
     supervisorctl reload
     supervisorctl
     
