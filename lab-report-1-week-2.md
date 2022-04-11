#Lab Report 1 - Week 2
##Installing VScode
The first step is to [install and run VScode.](https://code.visualstudio.com/download)

![Image](Opening VScode.png)
*Opening VScode*

##Connecting to the remote computer
The second step is to connect to the remote computer.
We do this by first opening the terminal (using Ctrl + \` or Terminal -> New Terminal).
Then we use command:

$ ssh *Username*@ieng6.ucsd.edu

Type yes on the next prompt and then enter your password.
You should now be connected to the remote computer.

![Image](Remotely Connecting.png)
*Connecting remotely to another PC*

##Trying some commands
There are many different commands we can try now that we are connected to the remote computer.
Some of these commands are cd, ls, pwd, mkdir, and cp.

![Image](Trying Some Commands.png)
*Trying Some Commands*

##Moving files with scp
To move a file, use the command:

scp *Filename* *Username*@ieng6.ucsd.edu:~/

Now, upon logging back into ieng6, you should see this file in the home directory and be able to run it on the remote computer.

![Image](Moving Files with scp.png)
*Moving Files with scp*

##Setting up an SSH key
Having to log back in each time is annoying, so we can set up an SSH key to log in for us.
Use command:

$ ssh-keygen

Do not enter a passphrase when prompted.
Log back into the remote computer using $ ssh *Username*@ieng6.ucsd.edu and enter your password again.
Then use command:

$ mkdir .ssh

Logout of the remote computer and use command:

$ scp /Users/\<user-name\>/.ssh/id_rsa.pub *Username*@ieng6.ucsd.edu:~/.ssh/authorized_keys

Now you can log in without having to type in your password each time.
  
![Image](Setting an SSH Key.png)
*Setting an SSH Key*
