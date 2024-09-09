# Symfony server issue

**_WARNING_ Web Server log file cannot be tailed: unable to watch log file: no space left on device**

To solve above issue on Ubuntu run below command.
```
sudo sysctl fs.inotify.max_user_watches=99999
```
