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
Files placed in init.d require a header, the header part is from ### BEGIN INIT INFO untill ### END INIT INFO.
The header file can be copied from the README file that is also located in the init.d folder.
My python file is located directly in the root folder so then you make a file that looks something like this: 

```bash
#!/bin/sh
### BEGIN INIT INFO
# Provides:          filename
# Required-Start:    
# Required-Stop:     
# Should-Start:      
# Should-Stop:       
# X-Start-Before:    
# X-Stop-After:      
# Default-Start:     
# Default-Stop:      
# X-Interactive:     
# Short-Description: 
# Description:        
#                    
### END INIT INFO

cd /
cd root/
sudo python filenamepython.py
cd /

```

To add your new shell script to the boot sequence you need to input the following command in the terminal

```bash
sudo update-rc.d filename.sh defaults
```

Now the only thing that need to be done is to add the permissions to our shell script to be allowed to launch in boot

```bash
sudo chmod +x /etc/init.d/filename.sh
```

And this should conclude it. The python file should be running after next reboot.
