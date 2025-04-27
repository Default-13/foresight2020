### SSH and web related commands:

wget - command that transfers a file from the web via HTTP

```bash
wget https://assets.tryhackme.com/additional/linux-fundamentals/part3/myfile.txt
```

scp (secure copy) - used to transfer files from an ssh session 

```bash
scp important.txt ubuntu@192.168.1.30:/home/ubuntu/transferred.txt
```

python3 -m http.server - provides an easy way to turn the host into a web server, allowing you to use wget to download the desired files from said host.  Note: you'll need to open another terminal window after executing the command

```bash
python3 -m http.server` 
Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...
```

### Systemd Services Management: 
The `systemctl` command is used to manage systemd units. You can use it to start, stop, restart, or check the status of a service.

Start a service:
```bash
systemctl start <service_name>`
```

Stop a service: 
```bash
systemctl stop <service_name>
````

Restart a service: 
```bash
systemctl restart <service_name>
````

Check the status of a service: 
```bash
systemctl status <service_name>
````

### apt package manager is for debian based linux distros like Ubuntu and Kali:

Add GPG key for when adding 3rd party apps not included in default repos:
```bash
wget -qO - https://download.sublimetext.com/sublimehq-pub.gpg | sudo apt-key add - 
```

Create a file for the new repository (e.g., `sublime-text.list` in `/etc/apt/sources.list.d`): 
```bash
sudo nano /etc/apt/sources.list.d/sublime-text.list
```

Add repository information to the file: 
```bash
deb https://download.sublimetext.com/ stable main
```

Update apt to recognize the new repository: 
```bash
sudo apt update
```

Install a package (e.g., Sublime Text): 
```bash
sudo apt install sublime-text
```

Install a .deb file with apt which will auto install any dependencies:
```bash
sudo apt install ./package_name.deb
```

you can install .deb files with `sudo dpkg -i example-package.deb` but if dependencies are not present, the program will not work or run with errors.

Remove a package (e.g., Sublime Text): 
```bash
sudo apt remove sublime-text
````

Alternatively, use the `add-apt-repository` command: 
```bash
sudo add-apt-repository --remove ppa:PPA_Name/ppa
````

### Process Management:

ps - view processes running on the system. use ps aux to view processes ran by other users and the system:
```bash
ps
ps aux
```

Forcefully terminate a process: 
```bash
kill -9 <process_id>
```

Send a signal to a process: 
```bash
kill <process_id>
````

Kill all processes running under a specific user: 
```bash
pkill -9 -u <username>`
```

Kill a process by its name: 
```bash
kill <process_name>
````




#Linux #resources/linux