`dig +nocmd flaws.cloud any +multiline +noall +answer ` -> command to look for info about dns server

-> to see bucket files -->` aws s3 ls s3://flaws.cloud/ --no-sign-request --region us-west-2`




1) Leaked credentials
2) Instance misconfiguration
3) S3 misconfiguration
4) Access control misconfiguration
5) Explosure of resources via firewall
6) Network security misconfiguration
7) Insecure custom applications


1) Leaked Credentials -> 
  a) Look for hardcorded credentials stored in js file or client side(IKIA keyword)
  b) AWS Cognito credentials in response
  c) Vulnerabilities in AWS hosted applications like SSRF and LFI
  d) Code repositories such as Bitbucket and Github
  e) AWS error message such as access denied
  f) Public EBS snapshots (EC2 -> Snapshots -> Public Snapshots)
  g) Public AMIs (EC2 -> AMIs -> Public images)
  h) S3 Bucket
  i) RDS public snapshots (RDS-> Snapshots -> All Public Snapshots)
  j) People looking for help online and end up copy-pasting complete info
  
