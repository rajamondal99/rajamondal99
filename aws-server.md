## check which port is open in the server

```
sudo nmap -sT -O localhost
```

- if 'nmap' is not installed.
- ``` sudo apt install nmap ```

## To chek all the running service in the server
```
systemctl list-units --type=service --state=running
```
