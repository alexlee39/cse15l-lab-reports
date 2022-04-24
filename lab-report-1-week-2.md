# Lab Report 1 #


# 1) Install *VSCode* from the [Visual Studio code website](https://code.visualstudio.com/) for your respective Operating System(Windows/Mac/Linux,etc) #

![Screenshot](/screenshots/vscodeinstallation.png)


After installing *VSCode*, it would look something like this: 


![Screenshot](/screenshots/vscodegettingstarted.png)

After installing *VSCode*, you would need to search and download the java extension package to code in *Java*. 
![Screenshot](/screenshots/vscodejavaextensions.png)

# 2. To *Remotely Connect* to other server computers such as the ieng6 server computers, you would first need to open a new terminal in *VSCode*. #

**Important Notice:** If you are running a Windows computer/laptop make you sure you follow these additional instructions to download the necessary [Open SSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) files before trying to remote connect to a server.


![Screenshot](/screenshots/vscodeopeningterminal.png)

After you opened the terminal you would need to type a command to connect to the ieng6 server: ssh `cs15lsp22zz@ieng6.ucsd.edu` with the zz being interchangeable with the your own account (in my case `cs15lsp22acx@ieng6.ucsd.edu`). 
It will prompt a message similar to the image below since it's the first time you connect to the server.
![Screenshot](/screenshots/sshfirsttimeloggingin.png)

*Congrats, you have entered the ieng6 server with your own personalized account!*

# 3. Other commands in the server #
After being in the terminal, and connecting to the server, there are multiple commands to use and test out!

Some include but aren't limited to:
![Screenshot](/screenshots/commands.png)

# 4. Moving files with scp #
After learning how to connect remotely, it's important to learn how to transfer or copies files locally to a remote server. The scp, securely copies command, does exactly this and copies a local file from your computer or laptop to the remote server. 

*Extra tip*: When creating a new file on your computer, you can use split terminal to access your local computer's terminal while still being on the server

![Screenshot](/screenshots/wow.png)

To copy the `file` to the remote server type: scp `filename.txt` cs15lsp22zz@ieng6.ucsd.edu:~/

![Screenshot](/screenshots/dam.png)

# 5. Setting SSH key
As you may have noticed, everytime you logged in or tried to run a command, it always prompted for a password which got really repetitive. As such, there is a way to bypass a password, which is to set a SSH key. 

Start in your local computer's terminal and type in `ssh-keygen`.

**If your using Windows, type in `ssh-keygen -t ed25519` instead.**

You would get something like this without the override line as I have already created a public key. 

**Note**: When it prompts you to enter a file or enter a passphrase, you can simply hit enter and basically skip those statements, and it would run perfectly fine.

![SS](/screenshots/sshkeygen.png)

After copying your public key onto your local computer, we need to copy the public key to the server.

We first would log back into the server by using the ssh cs15lsp22zz@ieng6.ucsd.edu, to type the command: `mkdir.ssh` to copy this public key on the server

After typing that command, we go back to our local computer's terminal by pressing Ctrl-D or typing "exit".

We then continue by copying our public key on our local computer to the server account by typing in this command:

`scp /Users/user-name/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`

**For windows**: `scp C:\Users\user-name\.shh\id_ed25519.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys`

It would look like:

---

![SS](/screenshots/tooktoolong.png)

---

After typing in your password once last time, you should be able to log in to your server account without typing your password in. **Try it out!**

## 6. How to Optimize Remote Running ##
After learning how to implement SSH keys to bypass writing your password in multiple times, there are some other potential ways to optimize how to type/run tests/code on a server through your remote computer.

 One main way is through typing all your commands on one line. This method says some more time, as the computer would run the commands at once, instead of running the commands one by one. In the long run, this may be more effective for longer-processes such as if you are trying to copy 100+ files from your local computer to the server. 

 ![SS](/screenshots/a.png)

 Other ways to optimizine remote running is just to practice short-cut commands on the terminal. For instance, one very and simple command is pretty the up-arrow key to get the previous command.