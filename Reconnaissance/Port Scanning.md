1) Rust Scan --> Fastest 
2) Nabuu 
3) nMap --> 
                   a) Host DIscovery -> To find that host is active(`-sn` is for host discovery if not given namp does default). Two  ways:- i)ROOT(here nmap sends -TCMP ECHO Request -TCP SYN 443 -TCP ACK -80 -TCMP Time Stamp Request) and if get any response from anyof them it know host is active and do further scanning. ii) LOCAL(-SYN -443 -ACK -80) and same as ROOT.
                   b) IP Scanning -> i) Single IP -> `nmap 192.168.1.1`
                                            ii) Subnet Range -> `nmap 192.168.1.1/8`
                                            iii) Specific Ip -> `nmap 192.168.1.1-10` -> It will scan ip from 192.168.1.1 to 192.168.1.10
                                            iv) Text File --> nmap -iL host.txt 
                                            v) Domain --> namp domain.com
                    c) Port Scanning -> i) Single Port --> `nmap 1.2.3.4 -p80`
                                            ii) Sequential Port --> `nmap 1.2.3.4 -p20-30` (Port 20 to 30)
                                            iii) DIstributed only --> `nmap 1.2.3.4 -p80,22,111`
                                            iv) Service Specific --> `nmap 1.2.3.4 -p T:22, U:53`
                                            v) ALL Ports --> `nmap 1.2.3.4 -p- `(65535 PORTS)
                                            vi) TOP PORTS SCAN --> `nmap 1.2.3.4 --top-ports` 100(here scan to 100 ports)
                    d) Scan Techiques -> i) TCP Connection Scan `-sT`
                                            ii) TCP SYN SCAN -sS
                                            iii) FIN SCAN -sF
                                            iv) XMAS SCAN -sX
                                            v) NULL Scan -sN
                                            vi) Ping Scan -sP
                                            viii) UDP Scan -sU
                                            ix) ACK Scan -SA
                    e) SCAN TIMINGS --> i) `TO`(PARANOID -->TOO SLOW)
                                            ii) `T1`(SNEAKY)
                                            iii) `T2`(POLITE)
                                            iv) `T3`(NORMAL)
                                            v) `T4`(AGGRESSIVE)
                                            vI) `TV`(INSANCE)
                    f) SCAN RESULTS --> i) OPEN
                                            ii) CLOSE
                                            iii) FILTERED -->means there is firewaall or some packet dropper mechanisnms that drop then SYN flag without reaching the host.
                                            iv) UNFILTERED -->means the response is not known and nmap doesnt know it is open or not .
                                            v)OPEN FILTERED -->
                                            vi)CLOSE FILTERED
                    g) HOST TIMEPOU --> IF YOU KNOW HOST IS TAKING TIME TO RESPOND THEN WE CAN USE --> nmap --host-timeout 500ms ip. 
                     h) SCAN DELAY --> `nmap --scan-delay 1s 1.2.3.4`
                     i)  OUTPUT TYPES i)`-ON `--> NORMAL TEXT OUTPUT
                     ii) `ox` -->XML FORMAT
                     iii) `oG` --> GREAPABLE FORM
                     iv) `oS` -->SCRIPT KIDDLE FORMAT
                     I) NSE(Nmap Script Engine) --> `nmap domain.com --script http-headers`  --> we can find script directory lsit in /usr/shre/namp/scripts/. It is used for firewall bypass, FTP enum , HTTP enum etc.
                    J) TO FIND SERVICE VERISON --> `nmap -sV IP`
                    k) TO FIND OS --> `nmap -O IP`
                    l) VERBOSITY --> `nmap -v IP`
                    m) SERVICE+OS DETECTION + SCANNING+ TRAEROUTE --> `nmap -A IP`
                    n) SCAN IP6 --> `nmap -6 IP
                    `
        -->check this command -> nmap -p- --min-rate 5000 -sV 10.129.139.144
                     
                     
                     
                   
                
          

