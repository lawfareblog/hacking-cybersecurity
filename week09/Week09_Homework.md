# Week 9 - Supplementary Materials 
[Markdown](https://github.com/lawfareblog/hacking-cybersecurity/blob/main/week09/Week_09_Homework.md) | [PDF](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week09/Week_09_Homework.pdf) | [MS Word DOCX](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week09/Week_09_Homework.docx) | [Libre ODT](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week09/Week_09_Homework.odt) | [HTML](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week09/Week_09_Homework.html)

## Metasploit &amp; Metasploitable

[Metasploit](https://docs.metasploit.com/) is a suite of exploits and penetration testing tools that is installed by default on Kali Linux. We demonstrate Metasploit via the `msfconsole` command throughout this course and it's one of the most important tools at your displosal as an ethical hacker. Real-world exploits such as [EternalBlue](https://en.wikipedia.org/wiki/EternalBlue), the exploit behind waves of ransomware, are merged into Metasploit as they become well-known and utilized in-the-wild.

[Metasploitable](https://docs.rapid7.com/metasploit/metasploitable-2/) (Metasploitable-2) is a purposefully vulnerable operating system. It is a secure place to perform penetration testing and security research, notably by attacking it with Metasploit. To follow along with our live hacks in class, this virtual machine will be required. Additionally, it provides a good basis for your final hacks (though it is not required for your final project).

### Download &amp; Install Metasploitable

[CLICK HERE](https://sourceforge.net/projects/metasploitable/) and download a 64-bit pre-built virtual machine (VM) image of Metasploitable. You will add this VM image to VirtualBox to boot into Metasploitable inside your host operating system.

[<img src="images/08metasploitable.png" width="600" />](https://sourceforge.net/projects/metasploitable/)

Metasploitable setup tutorials: 

* [Video 01](https://www.youtube.com/watch?v=g1JnLIfTjzM)
* [Video 02](https://www.youtube.com/watch?v=qSPT-YlIZAc)
* [Video 03](https://www.youtube.com/watch?v=pre9yWxjjrk)

#### Extracting the Zip File

The [Metasploitable VM](https://sourceforge.net/projects/metasploitable/) is distributed in a compressed Zip .zip format. All modern desktop operating systems (Windows, macOS, and most GNU/Linux variants) will extract Zip files. Please make sure you extract the VM image somewhere that you can find it. Though it is in VMware .vmdk format, you will be able to import it into VirtualBox.

#### Log In to Metasploitable

Once you can boot Metasploitable, the default credentials are: 

* username: `msfadmin`
* password: `msfadmin`

You don't have to change this password even though it is very weak because Metasploitable is _supposed_ to be insecure.

#### Find the Metasploitable Network Address

Use the `ifconfig` command to find the IP address for the Metasploitable VM. Remember this address because it will be the one that you attack with Kali Linux using Metasploit `msfconsole`.

<img src="images/09metasploitable.png" width="600" />

### Starting Metasploit

Metasploit utilizes a database of exploits that must be initialized the first time `msfconsole` is run.

* Restart the PostgreSQL database service: 

`sudo service postgresql restart`

* Initialize the Metasploit database: 

`sudo msfdb init`

* Start `msfconsole`: 

`sudo msfconsole`

Now you can follow along with our hacks using Metasploit and try some of your own. Here are some examples you can try online: 

* [Step-By-Step Getting Started with Metasploit](https://www.golinuxcloud.com/metasploit-tutorial/)
* [SMB/Samba EternalBlue exploit](https://www.ceos3c.com/security/metasploit-tutorial-the-complete-beginner-guide/#vulnerability-exploitation)
* [FTP exploit](https://www.tutorialspoint.com/metasploit/metasploit_exploit.htm)
* [Delivering a Payload](https://www.tutorialspoint.com/metasploit/metasploit_payload.htm)

### Meterpreter

Metasploit is not limited to `msfconsole` and we will also demonstrate the Meterpreter command to, for example, capture microphone audio on a vulnerable machine.

* [Get started with Meterpreter](https://www.offensive-security.com/metasploit-unleashed/meterpreter-basics/)

