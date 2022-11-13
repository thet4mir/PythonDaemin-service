# Daemon Server
A daemon services are utility programs that run silently in the background to monitor and take care of certain subsystems to ensure that the operating system runs properly. A printer daemon monitors and takes care of printing services. A network daemon monitors and maintains network communications, and so on.

# Instatlation
```
  #all daemon service file stored in /lib/systemd/system folder  
  # Create symbolic link than directly copying the service file, in order to prevent access system folder when change the service file
  sudo ln -s sensorService.service /lib/systemd/system/sensorService.service

  # need to tell daemon-service reload all the configuration file. we need to every time we add new file or change the configuration file
  sudo systemctl daemon-reload

  #now you can start your own service
  sudo systemctl start sensorService.service
```

# File structure
```
  Type: type must be simple because we just run basic python script.
  User: we can run any script as root permission or any other users.
  WorkingDirectory: our script working with file so WorkingDirectory must be point the path that you defined in your script.
  ExecStart: first argumemnt must be executer, you can change /bin/sh then run shell script, second argument location of script that you need to run.
  other parameter not important you can look at from document.

  [Install]
  WantedBy: that directive must be in your service file, basically that section help us to create symbolic link in /etc/systemd/system.
```
