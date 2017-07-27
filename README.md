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

To add your new shell script to the boot sequence you need to input the following command in the terminal

````bash
sudo update-rc.d filename.sh defaults
```

Now the only thing that need to be done is to add the permissions to our shell script to be allowed to launch in boot

```bash
chmod +x /etc/init.d/filename.sh
```

And this should conclude it, you will get a warning though for missing headers in the shell script. The warning doesnt stop the process though and it should be running after the next reboot.
