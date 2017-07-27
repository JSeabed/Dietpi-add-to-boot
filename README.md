# Dietpi-add-to-boot
Explanation about adding a shell file to the boot sequence of the DietPi OS


To add a Python script to the boot sequence I used a shell script to initiate it.
I located the shell script in the init.d folder.

```bash
cd /etc/init.d/
```

Here you create the shell script that refers to your file

```bash
nano filename.sh
```

My python file is located directly in the root folder so then you make a file that looks something like this: 

```bash
#!/bin/sh

cd /
cd /root/
sudo python filename.py
cd /
```

