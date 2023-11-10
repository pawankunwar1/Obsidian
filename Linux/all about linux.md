|1) <mark style="background: #FF5582A6;">BInaries </mark>:- This term refers to files that can be executed, similar to executables in Wndows. Binaries generally reside in the `/usr/bin ` or `/usr/sbin` directory and include utilities such as `ps, cat, ls, and ifconfig`.
2) <mark style="background: #FF5582A6;">Shell</mark>:- This is an environment and interpreter for running commands in Linux. The most widely used shells is `bash`, which stands for `Bourneagain shell`.
3) <mark style="background: #FF5582A6;">Terminal</mark>:- This is a command line interface(CLI).
4) <mark style="background: #FF5582A6;">Script:</mark>- This is a series of commands run in an interpretive environment that converts each line to source code. Many hacking tools are simply scripts. Scripts can run with the bash interpreter or any of the other scripting language interpreters, such as Python, Perl, or Ruby. Python is currently the most popular interpreter among hackers.



<mark style="background: #FF5582A6;">THE LINUX FILESYSTEM</mark>
-> At the very top of the file system structure is `/`, which is often referred as the `root` of the file system.![[Screenshot from 2023-08-19 09-20-13.png]]  --> The root(/) of the file system is at the top of the tree, and the following are the most important subdirectories to know:
a) `/root` -> The home directory of the all-powerful root user.
b) `/etc` -> Generally, contains the Linux configuration files-< files that control when and how programs start up.
c) `/home` -> The user's home directory.
d) `/mnt` -> Wher other filesystems are attached or mounted to the filesystem.
e) `/bin` -> Where application `binaries` (the equivalent of executables in Microsoft Windows or applications in macOS) reside
f) `/lib` -> Where you will find `libaries`(shared programs that are similar to WIndows DLLs).
g) `/media` -> Where CDs and USB devices are usually attached or mounted to the filesystem.

->(pwd->print working directory)(cd->change directory)
->(ls /directory from any other direcotry is also possible)
->(to find hidden files and directory `ls -a`) and (to find directory and file permissions and info `ls -l`) (both combine `ls -la`)
->(we can use `man nmap` or `nmap -h` or `nmap --help` to know how to use)
->(to find the stuff we can use `locate nmap` , it disadvantages is that it uses database that is usually only updated once a day, so if you just created a file a few minute or few hours ago, it might not appear. )
-->(to find Binaries we can use `whereis` command like `whereis nmap`)


-> FINDING BINARIES IN THE PATH VARIABLE WITH `which`
The which command is even more specific; it only returns the location of the binaries in the PATH variable in Linux. PATH variable holds the directories in which operating system looks for the commands you execute at the command line. For ex:- when enter aircrack-ng on the command line, the os looks to the PATH variable to see in which directories it should look for aircrack-ng, where it find the binary file for aircrack-ng.


