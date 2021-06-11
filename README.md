# DevOps Bootcamp

# Introduction to DevOps and why DevOps/benfits
-
-
-
-
-
-

## Permissions

Linux permissions dictate 3 things you may do with a file, read, write and execute. They are referred to in Linux by a single letter each.

__r__ (read) - you may view the contents of the file.
__w__ (write) - you may change the contents of the file.
__x__ (execute) - you may execute or run the file if it is a program or script.


For every file we define 3 sets of people for whom we may specify permissions.

#### Owner

The user who owns the file. Typically the person who created the file but ownership can be changed.

#### Group

Every file belongs to a single group. Groups can have many users in it so you can give access to multiple people.

#### Others

Everyone else who is not in the group or the owner.

Three persmissions and three groups of people. That's about all there is to permissions really. Now let's see how we can view and change them.

### View Permissions

To view permissions for a file we use the long listing option for the command ls.

ls -l [path]

### Change Permissions

To change permissions on a file or directory we use a command called "chmod" It stands for change file mode bits which is a bit of a mouthfull but think of the mode bits as the permission indicators.

```
chmod [permissions] [path]
```

chmod has permission arguments that are made up of 3 components

There are two ways you can use chmod and you will see both used. One is shorter and one is more descriptive.

[Reference](https://phoenixnap.com/kb/linux-file-permissions)

## Environment Variables
- To create a envi

`~/.bashrc`, `~/.profile`, `~/.bash_profile`

#### List Environment Variables
To display the value of the HOME environment variable you would run:
```
printenv HOME
```
If you run the `printenv` or `env` command without any arguments it will show a list of all environment variables

#### Setting Environment Variables
To create a new shell variable with the name `MY_VAR` and value `Linuxize` simply type:
```
MY_VAR='Linuxize'
```
You can verify that the variable is set by using either `echo $MY_VAR` of filtering the output of the set command with grep `set | grep MY_VAR`:
```
echo $MY_VAR
```
```
Output
Linuxize
```
The `export` command is used to set Environment variables.
```
export MY_NEW_VAR="My New Var"
```

#### Persistent Environment Variables
To make Environment variables persistent you need to define those variables in the bash configuration files.
- Per-user shell specific configuration files. For example, if you are using Bash, you can declare the variables in the `~/.bashrc`:
```
export PATH="$HOME/bin:$PATH"
```
To load the new environment variables into the current shell session use the `source` command:
```
source ~/.bashrc
```

## Manually generating your SSH key in macOS
To generate SSH keys in macOS, follow these steps:

1. Enter the following command in the Terminal window.
 ```
 ssh-keygen -t rsa
 ```
2. Press the ENTER key to accept the default location. The ssh-keygen utility prompts you for a passphrase. 
3. Type in a passphrase. You can also hit the ENTER key to accept the default (no passphrase). However, this is not recommended.

After you confirm the passphrase, the system generates the key pair.
```
Your identification has been saved in /Users/myname/.ssh/id_rsa.
Your public key has been saved in /Users/myname/.ssh/id_rsa.pub.
The key fingerprint is:
ae:89:72:0b:85:da:5a:f4:7c:1f:c2:43:fd:c6:44:38 myname@mymac.local
The key's randomart image is:
+--[ RSA 2048]----+
|                 |
|         .       |
|        E .      |
|   .   . o       |
|  o . . S .      |
| + + o . +       |
|. + o = o +      |
| o...o * o       |
|.  oo.o .        |
+-----------------+
```
Your private key is saved to the id_rsa file in the .ssh directory and is used to verify the public key you use belongs to the same github account.

**Never share your private key with anyone!**

- go to your GitHub profile and go to Settings
- go to the SSH keys
- Click Add SSH key, enter the contents of the id_rsa.pub file
- Enter GitHub password when prompted


