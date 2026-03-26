# Zeek
an open-source, passive network security monitor (NSM) used on Linux and other Unix-like systems to analyze network traffic. Unlike a firewall that blocks traffic, Zeek "listens" to a network feed and transforms raw data into high-fidelity, structured logs for security analysis and troubleshooting.


Structured Logging: It automatically categorizes traffic into readable log files such as conn.log (connections), http.log (web activity), dns.log (queries), and ssl.log (certificates).


Passive Analysis: It operates out-of-band, meaning it doesn't slow down network performance while it observes and records activity.
Custom Scripting: Zeek uses its own Turing-complete scripting language, allowing users to write custom rules to detect specific threats or automate complex analysis.


File Extraction: It can identify and extract files (like executables or documents) directly from the network stream for further malware analysis
Common Use Cases


Threat Hunting: Security teams use Zeek's detailed metadata to find "needles in the haystack" that standard antivirus or firewalls might miss.

Forensics: After a security incident, Zeek logs provide a historical record to reconstruct exactly what happened on the network.

Performance Monitoring: It helps network engineers identify bottlenecks, misconfigured devices, or unauthorized services

How to install in Kali linux
1. Update system
sudo apt update && sudo apt upgrade -y
2. Install dependencies
   sudo apt install -y cmake make gcc g++ flex bison libpcap-dev libssl-dev python3-dev swig zlib1g-dev
  3. Add Zeek repository
      echo 'deb http://download.opensuse.org/repositories/security:/zeek/xUbuntu_22.04/ /' | sudo tee /etc/apt/sources.list.d/zeek.list
   4. Add repository key
        curl -fsSL https://download.opensuse.org/repositories/security:zeek/xUbuntu_22.04/Release.key | sudo gpg --dearmor -o /etc/apt/trusted.gpg.d/zeek.gpg

5. Install Zeek
   sudo apt update
sudo apt install zeek -y
6. Add Zeek to PATH
echo 'export PATH=$PATH:/opt/zeek/bin' >> ~/.bashrc
source ~/.bashrc
7. Verify installation
zeek --version

&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&
2: Install Zeek from Source (All Linux)


1. Install dependencies
sudo apt install -y cmake make gcc g++ flex bison libpcap-dev libssl-dev python3-dev swig zlib1g-dev git

2. Download Zeek
git clone https://github.com/zeek/zeek.git
cd zeek

3. Build and install
./configure
make -j4
sudo make install
&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&&

Run Zeek (Basic Test)
Capture traffic on interface:
sudo zeek -i eth0



      
