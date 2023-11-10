1) hostname -> to find the name of the host
2) uname -a -> Will print system information giving us additional detail about the kernel used by the system. This will be useful when searching for any potential kernel vulnerabilities that could lead to privilege escalation.(gives info about system os and hardware platform)
3) /proc/version -> this command may give information on the kernel version and additional data such as whether a compiler(eg GCC) is installed or not(it contains about linux kernel info)
4) /etc/issue -> this file contain information or text file that is displayed before the login prompt. It is typically used to display information about the system, such as the hostname, operating system version, and kernel version. The `/etc/issue` file can also be used to display warning messages or other important information.
5) ps -> The ps command is an effective way to see the running processes on a Linux System. 
6) ps -A -> it show all running processes
7) ps axjf -> VIew process tree -> it show detail list of all processes running on the system.
8) env ->The `env` command in Linux is used to display or modify environment variables. Environment variables are global variables that are used by programs to control their behavior. For example, the environment variable `PATH` tells programs where to look for executable files.
9) sudo -i ->
The `sudo -l` command in Linux is used to list the commands that a user is allowed to run with sudo privileges. The output of the `sudo -l` command includes the following information for each command:
10) sudo ls -la -> a give all files including hidden `-l` show permisiions
11) id -> The `id` command in Linux is used to print information about the current user or any other user, such as their user ID (UID), group ID (GID), and group memberships. It can also be used to print the effective UID and GID of the current user.
12) history -> Looking at earlier commands with the `history` command can give us some idea about the target system and, albeit rarely, have stored information such as passwords or usernames.
13) ifconfig
14) ip route
15) netcat
16) find