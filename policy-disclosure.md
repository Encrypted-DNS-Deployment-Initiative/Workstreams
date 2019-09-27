BRAINSTORMING!!

IMO it would be nice to have a standardized DNS data privacy policy that any org could use, in any country. 

I could maybe see the top of it being a bit of a nutritional label for simplicity, such as:

Policy Covers: [   ] DEFAULT ISP CUSTOMER USE  [   ] SPECIALIZED OPT-IN SERVICE

Protocols Supported: [    ] UDP/TCP 53 [    ] DoT TCP/853 [    ] DoH TCP/443 [    ] OTHER _____

DNSSEC Validation: [   ] YES  [   ] NO

NXDOMAIN Redirection: [   ] YES  [   ] NO

DNS Response Filtering: [   ] NO  [   ] YES, BY DEFAULT FOR ALL USERS  [   ] IN SOME CASES - FOR OPT-IN SERVICE ONLY 

DNS Query Logging: [   ] YES  [   ] NO  [    ] LIMITED TO ABUSE/MALWARE/PERFORMANCE INVESTIGATION

Query Log with Source IP Retention Period: [   ] PERMANENT  [   ] 30 DAYS  [   ] 1 WEEK  [   ] 1 DAY  [   ] LIMITED TO 

SPECIFIC CASES NOTED ABOVE  [   ] OTHER _____

Other Data Logging (e.g. query minus source IP): [   ] YES  [   ] NO   [    ] LIMITED TO ABUSE/MALWARE/PERFORMANCE INVESTIGATION

Other Data Retention Period: [   ] PERMANENT  [   ] 30 DAYS  [   ] 1 WEEK  [   ] 1 DAY  [   ] LIMITED TO SPECIFIC CASES NOTED ABOVE  [   ] OTHER _____

Logging Storage: [   ] ENCRYPTED AT REST  [   ] PLAINTEXT

Logging Access: [    ] LIMITED TO ACCESS NEED, AND ALL ACCESS LOGGED  [   ] OTHER ______

Required to Support Lawful Court Orders: [   ] YES  [   ] NO

Has Transparency Report to Disclose Legal Request Volumes: [   ] YES  [   ] NO

EDNS Client Subnet Support: [   ] YES  [   ] NO   [   ] LIMITED TO TRUSTED PARTNERS UNDER LEGAL AGREEMENT

-- For Specialized DNS Services –

Type of Service: [   ] PARENTAL CONTROLS  [   ] MALWARE / SECURITY PROTECTION [   ] LEGALLY-MANDATED FILTERING (e.g. UK)  [   ] OTHER _______

Response Re-Writing Behavior: [   ] NO ERROR  [   ] NXDOMAIN    [   ] RE-WRITTEN A/AAAA RR  [   ] RE-WRITTEN CNAME RR  [   ] OTHER ____      

Canary Domain for Testing: xxx.example.com

Contact to Report Errors/Issues: [   ] EMAIL _______  [   ] WEB TICKET _____ [   ] PHONE _____  [   ] N/A
