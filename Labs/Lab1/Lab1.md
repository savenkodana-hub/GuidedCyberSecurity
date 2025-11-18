Lab work no. 1
-	Name: Dana Savenko

-	Link: https://cloud.google.com/blog/topics/threat-intelligence/dprk-adopts-etherhiding

-	The description and the schema of the attack:
A North Korean hacking group targeted software developers by pretending to be recruiters or legitimate companies. They convinced the victims to run a small “test” file. That file secretly connected to the blockchain, downloaded hidden malicious code stored inside a smart contract, and installed a backdoor on the victim’s computer. With this backdoor, the attackers were able to steal cryptocurrency wallet keys, passwords, and other sensitive data. Because the malicious code was stored on the blockchain instead of a normal server, it was much harder for security systems to detect or remove it.

The schema:

1.Attackers pose as recruiters and convince developers to run a “test” file.
2.Victim downloads/executes a small JavaScript loader (or installs a malicious package).
3. The loader queries a smart contract (via blockchain API/RPC) and retrieves encoded payload data.
4. The loader decodes the on-chain data and runs the second-stage payload (backdoor/stealer).
5. The malware collects wallet keys/passwords, sends data to the attacker, and installs persistence; blockchain storage gives the attackers a resilient delivery/update channel.

-	Behaviors/ Tactics/ Technics used:

1. Initial Access:
 T1566-Phishing/Spearphishing - The attackers pretended to be recruiters and contacted developers through online platforms. This social engineering trick made the victims trust them and follow their instructions.

2. Execution:
T1204-User Execution - The infection started only when the victim manually opened or ran the “test” JavaScript file provided by the fake recruiter.

3. Command and Control:
 T1102-Use of Web Service - Instead of a normal command-and-control server, the malware used blockchain smart contracts as a hidden storage channel. The loader called blockchain APIs to retrieve the payload, which worked like a remote command service.


 4. Defense Evasion:
 T1027-Obfuscated Files or Information - The malicious code stored on the blockchain was encoded so that it would not be recognized as malware. 

5. Impact:
 T1486-Data Encrypted for Impact - The main goal of the operation was to steal cryptocurrency and sensitive information for profit and intelligence purposes.

6. Credential Access and Collection:
T1056- Input Capture - The backdoor and info-stealer collected browser passwords, cryptocurrency wallet keys, and other private data from the user’s system.

7. Persistence:
 T1078- Valid Accounts or Autostart Mechanisms - The second-stage malware installed a backdoor on the infected machine to keep long-term access even after reboots.

8. Initial Access:
 T1195-Supply Chain Compromise - In some cases, the attackers used malicious npm packages or compromised websites to deliver the first-stage code.


The attackers gained persistent access to victims machines by installing a backdoor delivered via an on-chain payload. They stole sensitive data including cryptocurrency wallet keys, browser passwords, and other credentials. The campaign allowed the operators to update and re-deliver malware via smart contracts, making removal and takedown difficult. Overall, the operation resulted in financial loss for some victims and long-term covert access useful for i
