# Lab 1 Report
How to set up remote access

## Installing VSCode
Google Visual Studio Code or click on this link [https://code.visualstudio.com/](https://code.visualstudio.com/) to download VSCode onto your computer. Once downloaded, you should see something similar to this when opening VSCode:
![vscode](https://user-images.githubusercontent.com/103166380/162598144-348a32a0-1dbb-4777-9514-1397fd9eb13a.png)

## Remotely Connecting
**Windows only:** Check and see if your computer has [OpenSSH](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_install_firstuse) installed, if not install it. OpenSSH is what allows you to connect to other computers.

Open a terminal in VSCode (Ctrl+Shift+` or use the Terminal tab)

Type in your terminal: `ssh cs15lsp22zz@ieng5.ucsd.edu`

Replace **zz** with the **letters** in your [course specific account](https://sdacs.ucsd.edu/~icc/index.php).

To look up your course specific account, in the link above, type in your Username and Student ID then click "Submit". It should pull up your account and any additional accounts.

![image](https://user-images.githubusercontent.com/103166380/162598592-00d223bb-1fa5-4912-a76b-8fc08ae74e7b.png)

If this is your first time connecting to this server, you will probably get a message like this asking:
```
Are you sure you want to continue connecting
(yes/no/[fingerprint])?
```
Type yes, hit enter, and provide your password.

Once you are logged in, you should see something like this:
![image](https://user-images.githubusercontent.com/103166380/162598767-c4213cf7-9de4-4003-83b5-412a309b7f48.png)

This means your terminal is connected to the server.

## Trying Some Commands
Try running a few commands in both on your computer and on the remote computer after ssh-ing.

Ways to log out of the remote server:
- Ctrl+D
- Type `exit` and hit enter

Some commands:

pwd `print working directory`

ls `list files`

cp `copy`

mv `move or rename`

cd `change directory`

mkdir `make directory`

rm `remove`

cat `view or create a file`

touch `create a file`

man `display command manual`

Example:
![image](https://user-images.githubusercontent.com/103166380/162599071-d5c76d7b-b493-445b-90da-fb53b20caebb.png)

## Moving Files with *scp*
`scp` is a command to copy files from your computer to a remote computer. You will always run it from your own computer (not logged into the server).

Let's say you had a file called WhereAmI.java 

In the terminal from the directory where this file was made, run the command (using your username) 

`scp WhereAmi.java cs15lsp22zz@ieng6.ucsd.edu~/`

![image](https://user-images.githubusercontent.com/103166380/162599454-47d7944a-b108-4f90-815b-38dbf1a935cc.png)

It should ask you for a password to log in. Just use the same password when you ssh-ed. (Mine didn't because I used SSH keys which will be covered after this.)

If you log into ieng6 with ssh again and run `ls`. you should see the file you just added in your directory.

## Setting an SSH Key
To avoid having to type in your password everytime you ssh, we can set up `ssh` keys. A program called `ssh-keygen`, creates a pair of files called the *public key* and the *private key*. By copying the public key to a particular location on the server and the private key to a particular location on the client (your personal computer), you can automatically connect to the server with ssh without having to type in your password everytime.

On client in your terminal, type:

`ssh-keygen`

![image](https://user-images.githubusercontent.com/103166380/162602280-fa839000-4545-4cdb-aad0-c918c943a14c.png)

Copy whatever is in the paraenthesis, and paste it to the right of the colon. After you hit enter you should see:

`Enter passphrase (empty for no passphrase):`

**Do not add a passphrase**

**Window's only: extra `ssh-add` step [https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation](https://docs.microsoft.com/en-us/windows-server/administration/openssh/openssh_keymanagement#user-key-generation)

Two files should be created; the private key and the public key (`.pub`), stored in the `.ssh` directory on your computer. Copy the *public* key to the `.ssh` directory on the server:
```
ssh cs15lsp22zz@ieng6.ucsd.edu
<Enter Password>

mkdir .ssh
exit

scp /Users/<user-name>/.ssh/id_rsa.pub cs15lsp22zz@ieng6.ucsd.edu:~/.ssh/authorized_keys
```
For the last command, use your username and the path you saw in the parathesis earlier.

After this, you should be able to ssh without having to enter your password.

## Optimizing Remote Running
You can write multiple commands on one line to save some time by using quotation marks for any commands after ssh or semi-colons.

Example:

![image](https://user-images.githubusercontent.com/103166380/162604052-06fd20f8-93ba-46ba-9266-a14f694c8dc2.png)

