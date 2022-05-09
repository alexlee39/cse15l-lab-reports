# Lab Report 3 :Github and Remote Server Conveniency

For this lab report, we showcase multiple tasks that allow us to have more access to github commands, as well as working on some more git commands.
## Number 1: SSH Configurations
For this part of the lab, we did some configurations to make our lives easier everytime we log into the ieng6 server. To do this, we first had to create a config folder located on our .ssh directory on our local computer.
![SS](/labrep3ss/labrep3sshdirectory.png)

After finding that directory, I created config using the Notepad application and got rid of the txt extension. Using the notepad application, I added a Host, and Host name with the username of the host. 

![SS](/labrep3ss/labrep3-ssh.png)

After creating the config file with the host ieng6, with the host name(server name) and my username for the ieng6 server, I was able to log in the ieng6 server with only *ssh ieng6*.

![SS](/labrep3ss/labrep3ssh2.png)


## Number 2: Github Access with Ieng6 Server

Using the git commands we learned in class, we want to figure out ways to commit changes on our remote server on a repo we might have on our github account. However, when we try to push a change we commited on our remote server, we can't without setting up a SSH key on the actual github website.

Hence, I had to create a new public and private key pair on the ieng6 server. From there I copied the public key from the id_ed25519.pub file and pasted in the SSH keys which is in your settings in your github account which is shown below.
![SS](/labrep3ss/labrep3sshkeys.png)

We can see the the private and public key on the ieng6 server in the hidden directory, *.ssh*. The public keys have a .pub extension, while the private keys don't, as seen below.

![SS](/labrep3ss/labrepp2.png)

After creating and linking the ssh keys to our github account, we can successful push origin main, any changes we have of our repo on our ieng6 server and push them directly onto the repo on the github server/website.

So what I did was added a change using echo, which is seen below.
![SS](/labrep3ss/labrep3p2-3.png)

Afterwards, I used git add, commit, and push origin main to successfully add,commit, and push these changes on the remote repo(the github repo version).

![SS](/labrep3ss/labrep3p2-4.png)

Here is the 
[link to commit changes](https://github.com/alexlee39/markdown-parse-clone/commit/6414deaa6d824ba436dc928049ba8fe392d45bee).

## Number 3: Copying Whole Directories to Ieng6 Server (scp -r)

In this section we want to show how you can copy why whole directories(folders containing many files) into our ieng6 server. We can do using the scp -r command which recursively copies all the files of a directory to whatever destination we set it to be (in this case, the ieng6 server).

As mentioned we can use the scp -r command to copies files from the current directory to the ieng6 server. To simplify things, and not copy every file, including hidden files, we can use certain extensions to this such as (*.java, *.md, lib/ ) which allows us to copy only the files ending with .java , .md, and the files in the lib folder.
![SS](/labrep3ss/labrep3p3.1.png)

As we can see after runnning the scp-r command, when I log into the ieng6 server, all the files are there.
![SS](/labrep3ss/labrep3p3.2.png)

To copy the files from markdown-Parse, and ssh into your account, you need a very long command that I ran in the screenshot below, to ssh into my account and run the corresponding compiling and runnning command for MarkdownParseTest.

![SS](/labrep3ss/labrep3p3.3.png)

For the convenience of your eyes, the command is: 

(scp -r *.java *.md lib/ ieng6:markdownParse; ssh ieng6 "cd markdownParse; /software/CSE/oracle-java-17/jdk-17.0.1/bin/javac -cp 
.:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar MarkdownParseTest.java; /software/CSE/oracle-java-17/jdk-17.0.1/bin/java -cp .:lib/junit-4.13.2.jar:lib/hamcrest-core-1.3.jar org.junit.runner.JUnitCore MarkdownParseTest")

Basically, it copies all the files into the ieng6 server in the markdownParse Directory and runs the javac compiling command and java command to run the jUnit Tests.