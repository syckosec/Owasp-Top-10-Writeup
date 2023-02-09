# Owasp Top 10 Final Machine

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled.png)

Upon opening the module, a prompt alerts you of the machine's vulnerability, indicating that all necessary information for exploitation can be found online. Directly before this module, you have gained knowlegde on the OWASP Top 10 vulnerabilities, including topics such as Cross-Site Scripting, SQL Injection, and Remote Code Execution, thus providing a general understanding of the exploitation process. To start the process, a thorough Nmap scan was conducted to assess the machine's running services.

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%201.png)

nothing unusual, just an ssh and an apache hosted website. Next thing I did was visit the website and look around.

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%202.png)

I take note of the fact that the site is made using PHP with MYSQL. 

Earlier in the module we were taught that a lot of previously discovered exploits can be found on a website called Exploit-db

[Offensive Security's Exploit Database Archive](https://www.exploit-db.com/)

I search for “bookstore exploit db” in firefox and am met with multiple exploit db links. 

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%203.png)

Clicking on the first one im met with a couple of links, and a whole lot of code.

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%204.png)

looking at the first URL we can already tell that this exploit is affecting the website that we looked at before. This is most likely the exploit were looking for!

next we check out the code and find out that its a python script that takes a payload and injects it into a fake image that can be run on the website. This will get us our web shell!

We can download the script and run it in our terminal by using the command pyhton3 <name of file> <URL>

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%205.png)

Perfect, we have a web shell that allows us to execute commands on the machine that hosts the website.  I start by checking where I am and what I have access to 

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%206.png)

Next I check if I am able to read /etc/passwd and I am. The THM module asked me to provide the number of characters in the /etc/passewd file. I can easily count them using the command wc -c /etc/passwd

![Untitled](Owasp%20Top%2010%20Final%20Machine%20b5f68afa85a74c9e935e1a7663887402/Untitled%207.png)

Perfect we now have our answer to the THM module and a better understanding of how to exploit webpages!