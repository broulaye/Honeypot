# Project 10 - Honeypot

Time spent: **X** hours spent in total

> Objective: Setup a honeypot and provide a working demonstration of its features.

### Required: Overview & Setup

- [x] A basic writeup (250-500 words) on the `README.md` desribing the overall approach, resources/tools used, findings
- [x] A specific, reproducible honeypot setup, ideally automated. There are several possibilities for this:
	- A Vagrantfile or Dockerfile which provisions the honeypot as a VM or container
	- A bash script that installs and configures the honeypot for a specific OS
	- Alternatively, **detailed** notes added to the `README.md` regarding the setup, requirements, features, etc.
  
  The Modern Honey Network was used to set up this honeypot. A local setup of an MHN sever and honeypot using vagrant was done. 
  Two Virtual machines were installed and launched. The first is the honeypot itself that will act as the target, the second is
  a server that will be monitoring data collected by the honeypot. To set these up the user will first have to clone the github
  repo containing the source code of the MHN at https://github.com/threatstream/mhn.git. After doing so, the user will have to 
  launch the Virtual machines via vagrant. After launching the virtual machine the user will have to ssh into the server and 
  clone the same MHN repo again in order to run scripts in that server that will allow it to monitor data collected by the 
  honeypot. During the run of the various script the user will setup the server environment including the url of the honeymap 
  the server will be monitoring. After setting up the server, the user will now have access to that server and can access it 
  through the url that was assign to it during the setup. Now the user will have to exit the server and ssh into the honeypot. 
  After accessing the honeypot, the user will have to go to its browser and connect to the server previously set up and copy 
  the deploy command that will then be past and used in the honeypot. After doing so the honeypot is now ready. The user can 
  test it by running a simple nmap command on the honeypot url from its host machine. After running this command the proof 
  should be available under the attack on the server console. 


### Required: Demonstration

- [x] A basic writeup of the attack (what offensive tools were used, what specifically was detected by the honeypot)
  By running the nmap command on the url of the honeypot the server capture the evidence of the scan: 
  nmap -sV -P0 10.254.254.101
- [x] An example of the data captured by the honeypot (example: IDS logs including IP, request paths, alerts triggered)
   2017-04-15 21:30:40      mhn-honeypot	10.254.254.1	25	pcap	     Dionaea
   this data contain the date the attack was conducted, the source ip, the destination port, the protocol use and the honeypot 
   attacked.
- [x] A screen-cap of the attack being conducted
  
    
### Optional: Features
- Honeypot
	- [ ] HTTPS enabled (self-signed SSL cert)
	- [ ] A web application with both authenticated and unauthenticated footprint
	- [ ] Database back-end
	- [ ] Custom exploits (example: intentionally added SQLI vulnerabilities)
	- [ ] Custom traps (example: modified version of known vulnerability to prevent full exploitation)
	- [ ] Custom IDS alert (example: email sent when footprinting detected)
	- [ ] Custom incident response (example: IDS alert triggers added firewall rule to block an IP)
- Demonstration
	- [ ] Additional attack demos/writeups
	- [ ] Captured malicious payload
	- [ ] Enhanced logging of exploit post-exploit activity (example: attacker-initiated commands captured and logged)
