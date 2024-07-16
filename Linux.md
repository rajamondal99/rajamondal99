1. ==== To know os info from cli =====
```
cat /etc/os-release
```

2. ==Vs code multi-cursor setting (mint)==
```
In Linux Mint Go to settings -> windows -> In the behavior tab for resizing windows Alt will be selected, disable it. Return to VS code, in the Setting Search toggle multi-cursor modifier ensure that it is in ALT, Now, you can use Alt + select to insert multicursor.
```
3. ===To check bssid of wifi (in linux)===
```
nmcli dev wifi list
```
4.===To check bssid of wifi (in windows)====
```
netsh wlan show all
```
5. === how to set charge upto 80 percent in ubuntu 22.04 =======
```
echo '80' | sudo tee /sys/devices/platform/lg-laptop/battery_care_limit
```
6. =====Bluetooth headphones cannot connect after update to Ubuntu 22.04===
```
sudo apt install --reinstall pulseaudio-module-bluetooth
pactl unload-module module-bluetooth-discover
pactl load-module module-bluetooth-discover
```
7. To check file size
```
ls -l -h
```
8. To check which service running in the port
```
lsof -i :8080
```

9. To merge the file inside the folder during folder move. use below command
    ```
    rsync -av --progress source/* destination
    ```
