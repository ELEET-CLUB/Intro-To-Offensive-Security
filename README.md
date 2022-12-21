# Intro-To-Offensive-Security
Understand what Offensive Security entails, and practice breaking into computer systems by exploiting applications and networks.

Try hack me free rooms link

https://sm4rty.medium.com/free-350-tryhackme-rooms-f3b7b2954b8d


Web Application Security

Introduction

Learn about web applications and explore some of their common security issues.

Every one of us uses different programs on our computers. Generally speaking, programs run on our computers, using our computerâ€™s processing power and storage. Moreover, to use a program, we need to install it first. What if we can use any program without installation?


![image](https://user-images.githubusercontent.com/114279584/208975488-aa15609e-e75e-41f0-8532-dbdfc6aea939.png)


A web application is like a “program” that we can use without installation as long as we have a modern standard web browser, such as Firefox, Safari, or Chrome. Consequently, instead of installing every program you need, you only need to browse the related page. The following are some examples of web applications:


• Webmail such as Tutanota, Protonmail, Outlook, and Gmail

• Online office suites such as Microsoft Office 365 (Word, Excel, and PowerPoint), Google Drive (Docs, Sheets, and Slides), and Zoho Office (Writer, Sheet, and Show)

• Online shopping such as Amazon.com, AliExpress, and Etsy

Thousands more examples provide a myriad of services. Other examples include online banking, money transfer, weather forecast, and social media.


![image](https://user-images.githubusercontent.com/114279584/208975538-a4ce6c55-c755-40c8-bb79-e1b098718124.png)


The idea of a web application is that it is a program running on a remote server. A server refers to a computer system running continuously to “serve” the clients. In this case, the server will run a specific type of program that can be accessed by web browsers.
Consider an online shopping application. The web application will read the data about the products and their details from a database server. A database is used to store information in an organized way. Examples include information about products, customers, and invoices. A database server is responsible for many functions, including reading, searching, and writing to the database. The online shopping web application might need more than one database to access, for example:

◇ Products database: This database contains details about the products, such as name, images, specifications, and price.

◇ Customers database: It contains all details related to customers, such as name, address, email, and phone number.

◇ Sales database: We expect to see what each customer has purchased and how they paid in this database.

We can already see the amount of information stored in any online shopping system. Suppose an attacker manages to exploit (hack) the web application and steal the customers’ database. In that case, this will lead to a significant loss for the company and its customers.
The image below shows searching for an item on an online shopping site. In the simplest version, the search will take four steps:

1. The user enters an item name or related keywords in the search field. The web browser sends the search keyword(s) to the online shopping web application.

2. The web application queries (searches) the products database for the submitted keywords.

3. The product database returns the search results matching the provided keywords to the web application.

4. The web application formats the results as a friendly web page and returns them to the user.



From the user’s perspective, they will only access an elegant online shop where all the technical infrastructure 
is hidden.


![image](https://user-images.githubusercontent.com/114279584/208975576-e15a944e-bb5d-452d-aa00-6f02feaa6e51.png)


Many companies offer bug bounty programs. A bug bounty program allows the company to offer a reward for anyone who discovers a security vulnerability (weakness) in the company’s systems. The main condition is that the found vulnerability is within the bug bounty scope and rules. Among many others, Google, Microsoft, and Facebook have bug bounty programs. Discovering a bug can earn you from a few hundred USD to tens of thousands of USD, depending on the severity of the vulnerability, i.e., the weakness you discovered.


Web Application Security Risk

Let’s say that you want to buy an item from an online shop. There are certain functions that you would expect to be able to do on this web application. Most straightforwardly, the online order might go as follows:

![image](https://user-images.githubusercontent.com/114279584/208975614-600fe08b-271f-4d89-9944-2ce282955f7d.png)


There are a few main categories of common attacks against web applications. Consider the following steps and related attacks.

• Log in at the website: The attacker can try to discover the password by trying many words. The attacker would use a long list of passwords with an automated tool to test them against the login page.

• Search for the product: The attacker can attempt to breach the system by adding specific characters and codes to the search term. The attacker’s objective is for the target system to return data it should not or execute a program it should not.

• Provide payment details: The attacker would check if the payment details are sent in cleartext or using weak encryption. Encryption refers to making the data unreadable without knowing the secret key or password.

We cannot cover everything, but we will present a few formal categories from OWASP Top Ten. Don’t worry if these techniques sound alien to you; TryHackMe walks you through each vulnerability.

Identification and Authentication Failure
Identification refers to the ability to identify a user uniquely. In contrast, authentication refers to the ability to prove that the user is whom they claims to be. The online shop must confirm the user’s identity and authenticate them before they can use the system. However, this step is prone to different types of weaknesses. Example weaknesses include:

◇ Allowing the attacker to use brute force, i.e., try many passwords, usually using automated tools, to find valid login credentials.

◇ Allowing the user to choose a weak password. A weak password is usually easy to guess.

◇ Storing the users’ passwords in plain text. If the attacker manages to read the file containing the passwords, we don’t want them to be able to learn the stored password.



![image](https://user-images.githubusercontent.com/114279584/208975700-04ff9b81-0f83-4438-8a8b-f94878a9e0ba.png)

Broken Access Control
Access control ensures that each user can only access files (documents, images, etc.) related to their role or work. For example, you don’t want someone in the marketing department to access (read) the finance department’s documents. Example vulnerabilities related to access control include:

◇ Failing to apply the principle of the least privilege and giving users more access permissions than they need. For example, an online customer should be able to view the prices of the items, but they should not be able to change them.

◇ Being able to view or modify someone else’s account by using its unique identifier. For example, you don’t want one bank client to be able to view the transactions of another client.

◇ Being able to browse pages that require authentication (logging in) as an unauthenticated user. For example, we cannot let anyone view the webmail before logging in.


Injection
An injection attack refers to a vulnerability in the web application where the user can insert malicious code as part of their input. One cause of this vulnerability is the lack of proper validation and sanitization of the user’s input.

Cryptographic Failures
This category refers to the failures related to cryptography. Cryptography focuses on the processes of encryption and decryption of data. Encryption scrambles cleartext into ciphertext, which should be gibberish to anyone who does not have the secret key to decrypt it. In other words, encryption ensures that no one can read the data without knowing the secret key. Decryption converts the ciphertext back into the original cleartext using the secret key. Examples of cryptographic failures include:

◇ Sending sensitive data in clear text, for example, using HTTP instead of HTTPS. HTTP is the protocol used to access the web, while HTTPS is the secure version of HTTP. Others can read everything you send over HTTP, but not HTTPS.

◇ Relying on a weak cryptographic algorithm. One old cryptographic algorithm is to shift each letter by one. For instance, “TRY HACK ME” becomes “USZ IBDL NF.” This cryptographic algorithm is trivial to break.

◇ Using default or weak keys for cryptographic functions. It won’t be challenging to break the encryption that used 1234 as the secret key.


![image](https://user-images.githubusercontent.com/114279584/208975752-b85d8212-6130-4444-a67e-229be0ad177d.png)



Don’t worry if these techniques look challenging or sophisticated at first. TryHackMe has dedicated in-depth rooms to help you understand and experiment with the various attacks against web applications.




Operating System SECURITY

This room introduces users to operating system security and demonstrates SSH authentication on Linux.


Every day you use a smartphone or a laptop or almost any type of computer, you interact directly or indirectly with an operating system. Operating systems include MS Windows, macOS, iOS, Android, Chrome OS, and Linux. But what is an operating system? To define an operating system, we need to visit one computer term: hardware.

![image](https://user-images.githubusercontent.com/114279584/208977407-825a3bae-a5d5-4b6f-a510-bd1d08456eff.png)


Computer hardware refers to all the computer parts and peripherals that you can touch with your hand. Hardware includes the screen, the keyboard, the printer, the USB flash memory, and the desktop board. As shown in the figure below, the desktop board contains many components, in particular, a central processing unit (CPU) and memory chips (RAM). Although not shown in the image below, the desktop board is usually connected to a storage device (HDD or SSD).

![image](https://user-images.githubusercontent.com/114279584/208977437-625059e9-4921-4111-a125-b072a2531e7d.png)


The desktop board is the main part of a computer, and all the other pieces of hardware from keyboard and mouse to screen and printer connect to it. However, hardware components by themselves are useless if you want to run your favorite programs and applications. We need an Operating System to control and “drive” them.

![image](https://user-images.githubusercontent.com/114279584/208977455-900df31f-dceb-4560-889e-41874868494f.png)


The Operating System (OS) is the layer sitting between the hardware and the applications and programs you are running. Example programs you would use daily might include a web browser, such as Firefox, Safari, and Chrome, and a messaging app, such as Signal, WhatsApp, and Telegram. All the programs and applications cannot run directly on the computer hardware; however, they run on top of the operating system. The operating system allows these programs to access the hardware according to specific rules.
Some operating systems are designed to run on laptops and personal desktops, such as MS Windows 11 and macOS. Other operating systems are designed specifically for smartphones, such as Android and iOS. There are also operating systems intended for servers; examples include MS Windows Server 2022, IBM AIX, and Oracle Solaris. Finally, there are operating systems that you can use on a personal computer and server; one example is Linux. The image below shows the popularity of the different operating systems used to browse the Internet according to Statcounter based on the data collected during January 2022.

![image](https://user-images.githubusercontent.com/114279584/208977956-da9934cd-1526-4a23-98df-6856bef8e76f.png)


Your smartphone might be running Android or iOS, and you might have plenty of private data on it. Examples include:

1. Private conversations with your family and friends

2. Private photos with family and friends

3. Email client that you use for personal and work communications

4. Passwords saved in the web browser (or even in notes)

5. E-banking apps


The list of confidential and private data goes on. You don’t want someone you don’t trust to open your phone and go through your photos, conversations, and apps. Hence, you need to secure your phone and its operating system.
The same goes for your laptop or computer running MS Windows, macOS, or Linux. Your computer will most likely contain plenty of information such as:

1. Confidential files related to your work or university

2. Private personal files, such as a copy of your ID or passport

3. Email programs, such as MS Outlook and Mozilla Thunderbird

4. Passwords saved in web browsers and other apps

5. Copy of digital camera and smartphone photos



The list can get very long, depending on the type of user. And considering the nature of the saved data, you want to ensure that your data is secure. When we talk about security, we should think of protecting three things:

• Confidentiality: You want to ensure that secret and private files and information are only available to intended persons.

• Integrity: It is crucial that no one can tamper with the files stored on your system or while being transferred on the network.

• Availability: You want your laptop or smartphone to be available to use anytime you decide to use it.

In the next task, we will discuss common attacks against these security pillars.



Common example of OS Security

As we mentioned in the previous task, security is concerned with attacks against:


1. Confidentiality

2. Integrity

3. Availability

In this room, we will focus on three weaknesses targeted by malicious users:

1. Authentication and Weak Passwords

2. Weak File Permissions

3. Malicious Programs

Authentication and Weak Passwords
Authentication is the act of verifying your identity, be it a local or a remote system. Authentication can be achieved via three main ways:

• Something you know, such as a password or a PIN code.

• Something you are, such as a fingerprint.

• Something you have, such as a phone number via which you can receive an SMS message.

Since passwords are the most common form of authentication, they are also the most attacked. Many users tend to use easy-to-guess passwords or the same password on many websites. Moreover, some users rely on personal details such as date of birth and name of their pet, thinking that this is easy to remember and unknown to attackers. However, attackers are aware of this tendency among users.
The National Cyber Security Centre (NCSC) has published a list of the 100,000 most common passwords. Let’s look at the top 20 passwords in the table below.

| Rank | Password |
| 1 | 123456 |
| 2 | 123456789 |
| 3 | qwerty |
| 4 | password |
| 5 | 111111 |
| 6 | 12345678 |
| 7 | abc123 |
| 8 | 1234567 |
| 9 | password1 |
| 10 | 12345 |
| 11 | 1234567890 |
| 12 | 123123 |
| 13 | 000000 |
| 14 | iloveyou |
| 15 | 1234 |
| 16 | 1q2w3e4r5t |
| 17 | qwertyuiop |
| 18 | 123 |
| 19 | monkey |
| 20 | dragon |

We can see that 123, 1234, 12345, …, 123456789, and 1234567890 are on the list. Dictionary words such as password, iloveyou, monkey, and dragon are commonly used. Words not in the dictionary include qwerty, qwertyuiop, and 1q2w3e4r5t; these seemingly complex passwords are very predictable as they follow the keyboard layout.

![image](https://user-images.githubusercontent.com/114279584/208977293-51e35b25-13d8-4325-93f9-81a7bfc4b73f.png)



In brief, if the attacker can guess the password of any of your online accounts, such as your email or social media account, they will be able to gain access to your private data. Therefore, it is vital that you choose complex passwords and use different passwords with different accounts.

Weak File Permissions
Proper security dictates the principle of least privilege. In a work environment, you want any file accessible only by those who need to access it to get work done. On a personal level, if you are planning a trip with family or friends, you might want to share all the files related to the trip plan with those going on that trip; you don’t want to share such files publicly. That’s the principle of least privilege, or in simpler terms, “who can access what?”
Weak file permissions make it easy for the adversary to attack confidentiality and integrity. They can attack confidentiality as weak permissions allow them to access files they should not be able to access. Moreover, they can attack integrity as they might modify files that they should not be able to edit.

Access to Malicious Programs
The last example we will consider is the case of malicious programs. Depending on the type of malicious program, it can attack confidentiality, integrity, and availability.

![image](https://user-images.githubusercontent.com/114279584/208977328-f83f33e0-eae5-4dc6-9544-33f8474d6ace.png)


Some types of malicious programs, such as Trojan horses, give the attacker access to your system. Consequently, the attacker would be able to read your files or even modify them.
Some types of malicious programs attack availability. One such example is ransomware. Ransomware is a malicious program that encrypts the user's files. Encryption makes the file(s) unreadable without knowing the encryption password; in other words, the files become gibberish without decryption (reversing the encryption). The attacker offers the user the ability to restore availability, i.e., regain access to their original files: they would give them the encryption password if the user is willing to pay the “ransom.”



Network Security

Learn about network security, understand attack methodology, and practice hacking into a target server.


your system, or it is a program that you install on your system. For instance, MS Windows includes Windows Defender Firewall, and Apple macOS includes an application firewall; both are host firewalls.

![image](https://user-images.githubusercontent.com/114279584/208977236-4cf32978-dcdc-40e1-a3b8-f082ae5a3abb.png)


According to the Cost of a Data Breach Report 2021 by IBM Security, a data breach in 2021 cost a company $4.24 million per incident on average, in comparison with $3.86 million in 2020. The average cost changes with the sector and the country. For example, the average total cost for a data breach was $9.23 million for the healthcare sector, while $3.79 million for the education sector.

Methodology

Every “operation” requires some form of planning to achieve success. If you are interested in wildlife photography, you cannot just grab a camera and head to the jungle unless you don’t care about the outcome. For a safe and successful wildlife photography tour, you would need to learn more about the animals you want to shoot with your camera. This includes the habits of the animals and the dangers to avoid. The same would apply to a military operation against a target or breaking into a target network.

![image](https://user-images.githubusercontent.com/114279584/208977166-db5ea91f-c6b7-477d-8892-4d83074e3609.png)


Breaking into a target network usually includes a number of steps. According to Lockheed Martin, the Cyber Kill Chain has seven steps:

1. Recon: Recon, short for reconnaissance, refers to the step where the attacker tries to learn as much as possible about the target. Information such as the types of servers, operating system, IP addresses, names of users, and email addresses, can help the attack’s success.

2. Weaponization: This step refers to preparing a file with a malicious component, for example, to provide the attacker with remote access.

3. Delivery: Delivery means delivering the “weaponized” file to the target via any feasible method, such as email or USB flash memory.

4. Exploitation: When the user opens the malicious file, their system executes the malicious component.

5. Installation: The previous step should install the malware on the target system.

6. Command & Control (C2): The successful installation of the malware provides the attacker with a command and control ability over the target system.

7. Actions on Objectives: After gaining control over one target system, the attacker has achieved their objectives. One example objective is Data Exfiltration (stealing target’s data).

![image](https://user-images.githubusercontent.com/114279584/208977190-09ecab81-2276-440a-87bd-5408a77e3d80.png)


Another analogy would be a thief interested in a target house. The thief will spend some time learning about the target house, who lives there, when they leave, and when they return home. The thief will determine whether they have security cameras and alarm systems. Once enough information has been gathered, the thief will plan the best entrance strategy. Physical theft planning and execution resemble, in a way, the malicious attack that aims to break into a network and steal data.
In the next task, we will carry out a practical example of the Cyber Kill Chain.

























