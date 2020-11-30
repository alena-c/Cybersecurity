# Honeypot Assignment

**Time spent:** **10** hours spent in total

**Objective:** Create a honeynet using MHN-Admin. Present your findings as if you were requested to give a brief report of the current state of Internet security. Assume that your audience is a current employer who is questioning why the company should allocate anymore resources to the IT security team.

### MHN-Admin Deployment (Required)

**Summary:** How did you deploy it? Did you use GCP, AWS, Azure, Vagrant, VirtualBox, etc.?
I used GCP which was super easy and user-friendly! 

<img src="mhn-admin.gif">

### Dionaea Honeypot Deployment (Required)

**Summary:** Briefly in your own words, what does dionaea do?

Dionaea is used to collect and store information about all different kinds of malicious traffic/attacks from all over the world.

<img src="dionaea-honeypot.gif">

### Database Backup (Required) 

**Summary:** What is the RDBMS that MHN-Admin uses? What information does the exported JSON file record?
  
 The command that is given to us to extract the db content into json file gives a hint that MHN-Admin uses MongoDB database system:
       
    $ mongod --version
    db version v3.6.3
    ...
    
Although, MongoDB is a NoSQL database. Hence, I could suppose that Google Cloud SQL is used based on MySQL database. Scanning with Nmap of several honeypot VM's revealed open ports used by mysql database. But regarding the mhn-admin I can't tell for sure.
  
The __session.json__ file, however, is a typical output dumb of the mongodb. It shows the ID of the attack, attack PROTOCOL, the PORT used for that attack, TIMESTAMP, DATE, SOURCE_IP address and SOURCE_PORT (an IP and port of an attacker), DESTINATION_PORT, IDENTIFIER hash, and the sensor HONEYPOT name.
    
MHN-Admin
*Be sure to upload session.json directly to this GitHub repo/branch in order to get full credit.*

### Deploying Additional Honeypot(s) (Optional)

#### Shockpot Honeypot

**Summary:** What does this honeypot simulate and do for a security researcher?

<img src="shockpot-honeypot.gif">

#### Snort Honeypot

**Summary:** What does this honeypot simulate and do for a security researcher?
Snort sensor is open source IPS (intrusion prevention system). It can analyse network traffic in real-time. It also logs the packets.

<img src="snort-honeypot.gif">

#### p0f Honeypot

**Summary:** What does this honeypot simulate and do for a security researcher?

<img src="p0f-honeypot.gif">

#### Cowrie Honeypot

**Summary:** What does this honeypot simulate and do for a security researcher?

<img src="cowrie-honeypot.gif">


### Malware Capture and Identification (Optional)

I run both ClamAV on the dionaea honeypot and used VirusTotal site, because there were several malware whch were not caught by the antivirus. For VirusTotal, I used MD5 hashes found at mhn-admin webserver in 
__Payloads Report__.

#### CVE-2017-0147 Malware

Caught by the 

**Summary:** How did you find it? Which honeypot captured it? What does each malware do?

It was captured by Dionaea. This malware is a trojan that was used in WannaCry Ransomware. It's a SMBv1 server that allows remote attackers to obtain sensitive information from process memory via crafted packets, aka "Windows SMB Information Disclosure Vulnerability." 

MD5 Hash: 6567e663303386b7152d5fcab1f06cac
SHA1 Hash: fc2ce59f87aa3688e20880d68b6bbb5cbffa2080

<img src="x-malware.gif">

## Notes
Describe any challenges encountered while doing the assignment.
I also included the log of infected files (report_clamav_dionaea.txt), that was discovered with ClamAV

