# **Setup and Use a Firewall on Windows/Linux**

![](https://miro.medium.com/v2/resize:fit:259/1*MdAfK_ZzLkF6xQQpmsAINQ.jpeg)

**Objective:** Configure and test basic firewall rules to allow or block traffic.

1. **Open firewall configuration tool (Windows Firewa l or terminal for UFW).**

**First Open Run**

> shortcut key: Windows Key + R
> 

write firewall.cpl and click on ok to open firewall

![](https://miro.medium.com/v2/resize:fit:614/1*T3UqElV9jSsBDqebKGYpfQ.png)

click on advance settings to see firewall rules

![](https://miro.medium.com/v2/resize:fit:700/1*fJhx2nuDce2YvsdveCbQPQ.png)

**2.List current firewall rules**

click on inbound rules

![](https://miro.medium.com/v2/resize:fit:700/1*WceMLQBCiHT09NOd7P9jxw.png)

You can see the all rules here

![](https://miro.medium.com/v2/resize:fit:700/1*R4dCA8p08jLcqcSt8YcU6w.png)

**3. Block Inbound Traffic on Port 23 (Telnet)**

On the right, click New Rule….

![](https://miro.medium.com/v2/resize:fit:700/1*5jbEIk6MpWZCY7YBAmGxCQ.png)

Choose Port → Click Next.

![](https://miro.medium.com/v2/resize:fit:700/1*hv3oaoAUroRyuWOxPiIWwQ.png)

Select TCP → Specify Specific local ports: type 23 → Click Next.

![](https://miro.medium.com/v2/resize:fit:700/1*-_UIvlsf5ujnuykZSJ9rUg.png)

Choose Block the connection → Click Next.

![](https://miro.medium.com/v2/resize:fit:700/1*J9AZMViSaTO8a3NNqaQKHw.png)

Apply to Domain, Private, and Public → Click Next.

![](https://miro.medium.com/v2/resize:fit:700/1*sxAiUUTGDzLrTTkUXO-PhQ.png)

Name it something like Block Telnet Port 23 → Click Finish.

![](https://miro.medium.com/v2/resize:fit:700/1*KWhofwpRP2yPacs0MYjrSw.png)

**4.Test the rule by attempting to connect to that port localy or remotely.**

To simulate this:

Open Command Prompt and type:

telnet 127.0.0.1 23 but error comes because telnet is not recignized

![](https://miro.medium.com/v2/resize:fit:700/1*HlmeL2Q0PxyUmhvNfCs05A.png)

Here I go to the Control panel to enable telnet and click on program

![](https://miro.medium.com/v2/resize:fit:700/1*VczcNyaI71oNrw5DWjTwsg.png)

and click on turn windows features on or off

![](https://miro.medium.com/v2/resize:fit:700/1*-Y6eQL9m7JiDBCbgrXx9nA.png)

select telnet and click on ok

![](https://miro.medium.com/v2/resize:fit:700/1*8PgYNQ2GV9HYgP3MQ2GknA.png)

click on close

![](https://miro.medium.com/v2/resize:fit:700/1*ImbM6AMp0AJCYntrTAATGQ.png)

go to command prompt run this command and here you see can this telnet is trying to connect

> telnet 127.0.0.1 23
> 

![](https://miro.medium.com/v2/resize:fit:700/1*aUZmBafWZ-5FWT32nrBv9w.png)

**5.Add rule to allow SSH (port 22) if on Linux.**

> From the Linux VM terminal:
> 
> 
> **sudo ufw enable**
> 
> ***sudo ufw allow ssh***
> 
> ***sudo ufw status***
> 

![](https://miro.medium.com/v2/resize:fit:504/1*sL6n0SMpKMs4gfTawxbNhQ.png)

**6.Remove the test block rule to restore original state.**

Back on Windows Firewall:

Go to Inbound Rules again.

Find your Block Telnet Port 23 rule.

![](https://miro.medium.com/v2/resize:fit:700/1*ypyxcnkOWdU1385I6IWwKQ.png)

Right-click it → Click Delete.

![](https://miro.medium.com/v2/resize:fit:700/1*bBnyG36nntw7CvL3_233bQ.png)

**7.Summarize How Firewalls Filter Traffic**

“A firewall acts as a barrier between a trusted and untrusted network. It filters incoming and outgoing traffic based on defined rules. In this task, we created a rule to block Telnet on port 23, tested it using the Telnet client, and confirmed it was blocked. We also allowed SSH (port 22) on Linux using UFW.”
