1) try to bypass Content-Type restriction
2) try `image.php%00.png` and try to access `image.php` file
3) try to change the directory rules like in .htaccess
4) Tip -> sometime web server check content of the file to check for malicious payload we can bypass using/adding comment payload in the image.
5) if there is resticted file upload then try using Race conditions