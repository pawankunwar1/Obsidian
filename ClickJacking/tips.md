-> sometime there is clickjacking bug in email functionality but we cannot pre fillled the form -> we can do my that /my-account?email_paramter=viper@gmail.com and in GET requests

-> some webiste uses frame buster for the protection of clickjacking we can bypass by using like this -> `<iframe sandbox="allow-forms"`

-> if there is self xss or other xss -> try to escalate with clickjacking


-> sometimes webserver try to prevent Clickjacking attack by using mulit-action process but that can be alos bypassed