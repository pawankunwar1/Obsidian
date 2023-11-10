restartcd --> sudo chown author_name directory(/html) (changing /var/www/html directory  permissions to author) 
--> `service httpd start` ito start web server
-> to view server status `systemctl status apache2
-> to enable apache server sudo systemctl enable apache2

--> httpd and apache2 are same but use in different os.

File name                       Desciption
/usr/sbin/httpd     -->   server binary
/etc/httpd             --> directory containing server configuration files.
/etc/httpd/conf     --> directory containing main configuration files
/etc/httpd/conf.d  --> directory containing configuration files for 
                                     individually packaged modules like ssl, php, perl etc.
 /etc/httpd/logs  -->  symbolic link to /var/log/httpd
 /etc/httpd/modules --> symbolic link to /usr/lib/httpd/modules
 /etc/httpd/run          --> symbolic link to /var/run
 /usr/lib/httpd/modules --> server modules
 /var/run/httpd              --> server log
 /var/run                         --> runtime variables
 /var/run/httpd.pid       --> server process ID 
 /var/www/html            --> public html files



 1) Main configuration files:- The main configuration file for the Apache Web Server is: `/etc/httpd/conf/httpd.conf`.  or for apache2 -> `/etc/apache2/apache2.conf`
   a) SeverRoot :- ServerRoot is the path to the servers configuration, error and log files. It is possible to change this path, provided all the necessary files are copied to the new location accordingly. The default location is `/etc/httpd` or `etc/apache2`
   b) ServerName :- This is the setting where we declare the name of the website.
   c) DocumentRoot :- DocumentRoot tells you where your web documents(html files, images etc) should be located. It is possible to references files i other directories using aliases and symbolic links. The default directory is /var/www/html
   d) ErrorLog :- ErrorLog tells you where the log containing all server errors is located. This file is critical for debgging and solving server mis-configuration problem and for proper traffic shapping. By default, all messages with the value of warning(warn) and higher will be logged. The defalut location is /logs/error_log. This is relative to the ServerRoot . So, our log file is /etc/httpd/logs/error_log.  However, /etc/httpd/logs is a symbolic link to /var/log/httpd. Thus, finally the actual error log is /var/httpd/error_log.
   e) Listen :- The Listen command tells the Web server what ports to use for incoming conenctions. 


2) Directory tags :- Directory tags allow you to specify the configurations separately for each directory serving the web pages.  `<Directory/> 
                       `Options FollowSYmLinks
                       `AllowOverride none`
                       `</Directory>`
   here `<Directory/>` declares the block for he root(/)     directory and all sub-directories.
   -> `Options FollowSymLinks` The Options directive declares which server features are valid for the specified directory. `FollowSymLinks` is one of the possible options - it allows webpages to use symbolic links to point to the files located anywhere on the root(/) directory. Please note this is not the best configuration for the security point of view. 
   -> `AllowOverride none` :- The AllowOverride directive governs the behavior of .htaccess files. It tells whether the restrictions imposed
by the Options can be overridden by specific settings inside the
.htaccess files. The default behavior is set to none and should remain that way. This will prevent security breaches or nuisances
due to misconfiguration. 
-> `</Directory>` :- This tag closes the block.

3) Order(allow, deny)(this is used in Apache version 2.2 , now after Apache 2.4 `Require all granted` command are used) :- Allow and Deny directives govern the access to the directory declares(via the Directory tags). The Order directive specifies how the allow and deny directives are treated. The Order of allow, deny can be looked upon as default-allow or blacklist; only "bad" hosts or IPS are disallowd. The Order of deny , allow can be looked upon as default-deny or whitelist; only "good" hots or IPs are allowed.
     Possible declaration of allowed or denied clients can be via host
name, domain name, IP address, partial IP address, and more.
Here, we’ll restrict access to the directory (or rather, the server)
by denying access from all - and only permitting access from a
single IP address, that of another machine on the LAN (in this
case, 192.168.1.129).

4) Indexes :- The Indexes directive tell the server whether to display the directory listing when asked. The behaviour of this directive depends on another directive -the DirectoryIndex. The `DirecotryIndex` directive tells the server the name of defalut page that is should server when user request the listing of a directory.
     --> like if user visit www.example.com , it should give index.html page to the user. We can do it  by adding index.html in /var/www/html directory + `<Directory /var/www/html> Options Indexes</Directory>` but if there is not index.html page there it will display all the files under that directory.
 5) DirectoryMatch :- 
 6) Files tags:- The Files tags are very similar to the Directory tags. The major difference is that while the Directory tags govern the scope of permissions (or restrictions) of the enclosed directives by directory name, the Files tags do the same on the file name level. In other words, the Files tags can be used to configure the behavior of a single file - or a set of files that match a regular expression. Here’s an example, showing the restrictions applied to .htaccess and .htpasswd files, the files usually used in restricting access to certain directories (and/or files) by requiring users to authenticate before viewing the content: `<FilesMatch "^\.ht">
	`Deny from all</FilesMatch>``
7)  Location tags:- Again, the Location tags are quite similar to the two mentioned above. The major difference is that the Location tags are used to limit the scope of enclosed directives by URLs. In other words, the Directory and Files should be used to control  content that resides on the system(like various files and images within their sub-directories), while the `Location tags` should be used to control content that is located outside the system like databases. `<Location /server-status> Sethandler server-status </Location>`
8) Redirect :- The Redirect setting allows you to map an old webpage to a new URL> `Redirect permanent /foo.html http://www.example.com`

9) Virtual Hosts:- Virtual Hosts is an important, powerful feature that allows you to run several websites from a single computer. Virtual Hosts can be IP-based or named-based, offering a high level of customization(and flexibility) `<VirtualHost *.80> 
                                            `DocumnetRoot /var/www/html/ninga`
                                            `ServerName www.ninja.com`
                                            `</VirtualHost>`
--> here `<VirtualHost *.80>`, this declares the name or the IP address of the site(server) that should be served using the directives inside the VirtualHost block on port 80. If no port number is used , the default one specified under the `Listen` option is used. The default port is 80(standard convention). Asterisk(`*`) can be replaced with any name(for e.x , www.ninja.com) of IP address(for ex. 192.168.1.128) depending on your needs and requirements.
     • ``<VirtualHost 192.168.1.128:80>`` will apply the directives listed in the
block below to all incoming connections aimed at 192.168.1.128 on port
80.
• <VirtualHost 192.168.1.128> will apply the directives listed in the
block below to all incoming connections aimed at 192.168.1.128 on the
default port (as specified in the Listen directive). If this port is 80,
then this option is identical to the one above
• <`VirtualHost planck.matter.com> `will apply the directives listed in the
block below to all incoming connections aimed at planck.matter.com on
the default port (which can be 80, 8080 or any other).
• <VirtualHost ninja.com:8777> will apply the directives listed in the
block below to all incoming connections aimed at our site ninja.com on
port 8777. This port must be specified under the Listen directive.


--> Single IP . two website :- We will create two websites
- www.ninja-father.com and www.ninja-son.com. Both will reside
on our server, which has the IP address 192.168.1.128. In order to
make them both accessible to the world, we will create two Virtu-
alHost blocks and declare their DocumentRoot and ServerName
separately.
Here’s what we need to do:
• Create directories inside /var/www/html called ninja-father and ninja-
son.
• Create simple index.html files for each.
• Edit httpd.conf and create our two VirtualHost blocks.


