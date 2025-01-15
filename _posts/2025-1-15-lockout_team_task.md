---
layout: post
title: lockout team task
---

ifconfig
found the netmask to narrow down the number of computers on that network
Sudo nmap -O 10.0.140.3/22 
this output all the computers on that network and it gave us 13 IP addresses 
Wrote down all the IP's we found
Checked all the other computers on the network to narrow down iIPaddresses to 3
We shut down two of the three to determine each of the IP's
Found our IP it was 10.0.140.5
Asked Corey for a hint
hint was Hail Hydra which hydra is a password cracker and we downloaded it using 
sudo apt install  hydra
and we got it installed on our computers
Asked Corey for a hint
Corey told us somewhere in his computer there was a file called rockyou.txt
we used to find -H and it spat out all the files in the computer thewn we used command f to find rockyou.txt 
once we found the path to rockyou.txt we used the cd to get to the directory where the file lived and the file was archived so we used 
gzip -d file.gz to unarchive the file then we used scp [source file] [username]@[destination server]:. to download the rockyou file onto our own terminal not coreys. then once in we used 
Hydra -l user -P rockyou.txt ftp://10.0.140.5
And then Hydra told us the password was iloveyou
