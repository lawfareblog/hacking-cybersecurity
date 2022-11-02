### Welcome to the Scavenger Hunt!

**NOTE:** These instructions can only be followed completely if you are a student in the Lawfare Hacking &amp; Cybersecurity class. Students have been sent credentials for remote servers by the instructors. Please see the activities from the previous and future classes for usage of each of these commands in a less specific context.

[Markdown](https://github.com/lawfareblog/hacking-cybersecurity/blob/main/week04/Week_04_Scavenger_Hunt.md) | [PDF](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week04/Week_04_Scavenger_Hunt.pdf) | [MS Word DOCX](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week04/Week_04_Scavenger_Hunt.docx) | [Libre ODT](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week04/Week_04_Scavenger_Hunt.odt) | [HTML](https://raw.githubusercontent.com/lawfareblog/hacking-cybersecurity/main/week04/Week_04_Scavenger_Hunt.html)

**Choose a remote machine named after your favorite season. You have already been sent the unredacted versions of these credentials.**

[Season] | [User] | [IP Address] | [Hostname] | [Password]
---|---|---|---|---
Fall | chicken1 | ---.---.---.--- | remote-computer03 | --------
Winter | chicken2 | ---.---.---.--- | remote-computer04 | --------
Spring | chicken3 | ---.---.---.--- | remote-computer01 | --------
Summer | chicken4 | ---.---.---.--- | remote-computer02 | --------


**1.** Log into your local Kali Linux machine and open the terminal CLI.

**2.** Connect to the remote machine using [User]@[Address] and the correlating [Password].

If you chose Fall, type:	`ssh chicken3@---.---.---.---`

If you chose Winter, type:	`ssh chicken4@---.---.---.---`

If you chose Spring, type:	`ssh chicken1@---.---.---.---`

If you chose Summer, type:	`ssh chicken2@---.---.---.---`

**3.** Create new user account using your favorite color plus your favorite food and a number (such as `purplepizza12`). Remember, usernames are case sensitive. We will refer to that user as [Hacker] in the following instructions.

* Example:	`sudo adduser [Hacker]`

**4.** Add the [Hacker] user to the `sudo` group.

* `sudo usermod -aG sudo [Hacker]`

**5.** Switch into that user account.

* `su - [Hacker]`

**6.** Create directory `~/goodies`

* `mkdir ~/goodies`

**7.** Navigate into directory `~/goodies`

* `cd ~/goodies`

**8.** Read the OS information and save the output into a file `osinfo.txt`
* `hostnamectl > osinfo.txt`

**9.** Check to make sure `osinfo.txt` has data in it.
* `cat osinfo.txt`

**10.** List running processes, save output into a file `processes.txt`
* `sudo pstree > processes.txt`

**11.** Check to make sure `osinfo.txt` has data in it.
* `cat processes.txt | less`

**12.** Copy system user and password information to the directory `goodies`
* `sudo cp /etc/passwd /etc/shadow ~/goodies/`

**13.** Rename files in goodies to clarify their function
* `mv passwd user-info.txt && mv shadow password-hashes.txt`

**14.** Check to make sure `user-info.txt` has data in it.
* `cat user-info.txt | less`

**15.** Check to make sure `user-info.txt` has data in it.
* `cat password-hashes.txt | less`

**For the following tasks we will not give you the commands. All of this was on the "homework" :D**

**16.** Find a file in the `/root` directory that contains email credentials for the user `legalpositivist`.

**17.** Copy the information to a file in `~/goodies/`

**18.** Locate a `.jpg` photo in the top level of the filesystem `/` and copy it to `~/goodies/`

**19.** **VERY IMPORTANT:** Create a file with your name or nickname inside of `~/goodies/`

**20.** Change permissions of `goodies` so you can read, write, and execute files in it.

**21.** Change ownership of `goodies` so that it is owned by [Hacker]

**22.** Clear your terminal CLI command history.

**These last few tasks are the most complex so far, so we'll help you out ;)**

**23.** Generate a hash from a random number (we'll call the output [HASH] below).
`echo $RANDOM | md5sum | cut -c -8`

**24.** Create compressed package of `goodies` with filename [HASH].
`tar -cvf ~/[HASH].tar.gz`

**25.** Exit the remote machine and go back to your local Kali Linux machine. 
`exit`

**26.** Download the package on your local Kali Linux machine.
`scp [Hacker]@[Address]:/home/[Hacker]/[HASH].tar.gz ~/Desktop/`

**Made it this far? Great! Now just three more steps.**

**27.** Double-check the `.tar.gz` or "tarball" file you have on `~/Desktop` of your local Kali Linux machine to see if it has the contents of the `goodies` folder in it. You can do this by double-clicking the `.tar.gz`

**NOTE: For the last step, students have been sent credentials for a remote drop box to upload their results.**

**28.** Open Firefox on your local Kali Linux machine and upload your results to the dropbox.

**Congratulations!  Your instructors will be notified when you upload.**
