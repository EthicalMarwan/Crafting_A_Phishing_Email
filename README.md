# Deploying False Login Page for Phishing Attacks

## Background
Phishing is a prevalent form of cyber attack today. Nearly everyone with an email address has received phishing emails, which can range from social engineering attacks to malware attachments. In this repository, I'll focus on a tool called Blackeye, which is specifically designed for spear phishing attacks, particularly credential harvesting. Spear phishing is similar to regular phishing, but it targets a specific individual. Credential harvesting, a common type of cyber attack, aims to obtain someone's credentials. Almost half of all phishing attacks are, in fact, credential harvesting attempts.

### What is Blackeye?
Blackeye is an open-source pen-testing tool designed to simulate credential harvesting phishing attacks. Once Blackeye is installed, it allows users to quickly create and launch a fake login page using its various templates. When the fake site is live, it generates a URL. When someone accesses the URL in any browser, the site captures their IP address and user agent. If they enter their login information, it also captures that data and sends it back to the attacker.

<div>
    <img src= "https://github.com/user-attachments/assets/1674df10-baaa-44a6-8d37-d7f35496b50c" />
</div>

### Steps
- To begin, I used a VM running the recent Linux distribution called "Ubuntu". Next, I cloned the repository for Blackeye. Once cloned, I made sure to run the command "chmod +x ./blackeye.sh" to allow execution of the tool. Once the tool is executed, you will see the screenshot below. This screenshot shows all the website template options the attacker has when running the tool.

<div>
    <img src= "https://github.com/user-attachments/assets/0240833c-2a3c-4626-aad9-8c9ee347f69a" />
</div>

- For this scenario, I chose the Amazon template, option #34. The tool then launched the website, and once it was up and running, it returned a URL and listened for incoming connections. 

<div>
    <img src= "https://github.com/user-attachments/assets/efeace95-6366-41ec-80b1-a951dc22ec26" />
</div>

- At this point, the attacker crafts the link in a way that would not raise suspicion, making it appear as a legitimate email. As illustrated in the screenshots below.

<div>
    <img src= "https://github.com/user-attachments/assets/6bcc2b1e-9381-4ec6-ab65-3d272fc5a92d" />
</div>

<div>
    <img src= "https://github.com/user-attachments/assets/e6484cf9-819d-43fb-aeb2-f3b8bda26bae" />
</div>

- Once the victim clicks the link, their IP address and user agent are immediately sent to the attacker, as shown in the screenshot below.

<div>
    <img src= "https://github.com/user-attachments/assets/dbd2967e-e777-4df3-8f8f-16509a6d3b0f" />
</div>

- The tool then waits for the victim to enter their login information on the fake site. If the victim does enter their information, the fake site relays the login info to the attacker and then redirects the victim to the actual version of the fake website. The screenshot below shows the example output of the program when the victim enters their credentials.

<div>
    <img src= "https://github.com/user-attachments/assets/a3aa93a3-b271-4965-804a-1c8504bf660f" />
</div>

### Example of the Amazon Template Option
This is the main reason why this tool is easy for anyone to use. You can run it from any network with an internet connection and do not need a public-facing IP address. Additionally, it does not require you to register a domain name. In the case of pen testing, this works great, but if this was used for a real phishing campaign, then it can be assumed that ngrok would flag the traffic and take down the fake website. Below is the example of the fake and the real counterparts. (fake on top, real on bottom)

<div>
    <img src= "https://github.com/user-attachments/assets/b761be0c-bdef-47c8-b5bc-7f93e7dbd4cd" />
</div>

<div>
    <img src= "https://github.com/user-attachments/assets/0863d47a-ca33-40e6-abd5-1fda51f8120c" />
</div>

## Conclusion 
Executing a phishing link is surprisingly easy, as tools like Blackeye can enable even those with minimal technical skills to craft convincing fake websites and deceptive emails. This simplicity highlights the crucial importance of never clicking on suspicious links. Falling for such a scam can lead to compromised personal information, financial loss, and other severe consequences. Always be vigilant and skeptical towards unexpected or unsolicited links to protect yourself from these pervasive cyber threats.
