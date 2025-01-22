
---
layout: post
title: bandit levels 0-20
---


Level 0: must type SSH into the terminal to use the bandit environment

$ ssh bandit0@bandit.labs.overthewire.org -p 2220

Then it asks for a password type 

$bandit0

Level 1:
First, I typed $ ls to make sure the file existed

Then I used $ cat readme

Then I got the password:

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If 

Then sign out using [exit]



























Level 2:
Once signed into bandit1 using 

$ssh bandit1@bandit.labs.overthewire.org -p 2220

Then it will ask for a password type from the previous password found in the prior level 

ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If (passwords will vary won't be the same as mine)

Then once in you will know because a message that says you have gained access will show up and to confirm type whoami and it should say bandit1

Then ls to see the file

To see what is inside file type 
Cat ./-

The ./- is necessary because otherwise, you will enter a platform that will not take commands. If you type (cat -) to exit type control D, not command D.

Then after typing the function with the correct syntax the new password for the next level should appear. 

263JGJPfgU6LtdEvgfWU1XP5yac29mFx(yours will most likely be different)
Sign out using [exit]

















Level 3:

To enter the lab for level 3 type in

ssh bandit2@bandit.labs.overthewire.org -p 2220

Then it will ask for the password type in what you got from the previous level 

263JGJPfgU6LtdEvgfWU1XP5yac29mFx(yours will most likely be different)

Once in type the ls function to be able to know the name of the file we need to get into 

Once we know the name (spaces in this filename) we use the following syntax

Cat “spaces in this filename”

This will allow cat to read out the filename with spaces because normally files dont have spaces in the and “” helps us fix the problem of the spaces.

Then the password should print 

MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx (yours will most likely be different)

Sign out using [exit]

$ exit


















Level 4
Sign in using 

$ssh bandit3@bandit.labs.overthewire.org -p 2220

It will ask for the password input that you got from old-level

MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx (yours will most likely be different)

Once in use [cd] to enter the directory in here

$cd inhere

Then you will be in the inhere directory to make sure type [pwd] and it will print what directory you are in you should see /home/bandit3/inhere indicating you are in the inhere directory
Once in the directory type:

$ls -a

The [-a] will show all files including hidden ones

That should print:

.  ..  ...Hiding-From-You
 
Then you can use:

$cat ...Hiding-From-You

And that should print your password

2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ (yours will most likely be different)

Then sign out using [exit]

$ exit









Level 5

Sign in using 

$ssh bandit4@bandit.labs.overthewire.org -p 2220

Use password found in previous challenge

Once in use [cd] to go to the in here directory:

$cd inhere
Once in the directory type:

$ ls

Ten files should show up 

You can cat each file one by one and since each file starts with a [-] use ./-(filename)


4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw






















Level 6:
Sign in using 

$ ssh bandit5@bandit.labs.overthewire.org -p 2220

Then once in change directories to inhere

$ cd inhere

Once in you can ls to see all the possible directories 

$ls

There are too many options to go through each one by one. So to narrow it down use the [find] function to narrow it down. The elements after the find are the requirements of the file the function will find like the size [-size 1033c], whether it is executable or not[-executable], and if it is a normal file[-type f]

$  find -type f -size 1033c ! -executable

This should output 

./maybehere07/.file2

Then i did:

$ cd maybehere07

Then i did:

$find -type f -size 1033c ! -executable

Then it output 

./.file2

Then i did:

$cat ./.file2

Then it will output the password:

HWasnPhtq9AVKe0dmk45nxy20cvUa6EG (yours will be different)

Then you can exit using the exit function: $ exit

Level 7:
Once signed in using
$ ssh bandit6@bandit.labs.overthewire.org -p 2220

The requirements form the following command

$ find / -user bandit7 -group bandit6 -size 33c>/dev/null

The dev/null is to get rid of all the extra outputs the terminal gives out so it can isolate the path to the file bandit7.password 

Once the path is output use 

$ cd /var/lib/dpkg/info

Once in the directory 

$ cat bandit7.password

Then you will get your password:

morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj (yours will be different)

Then you can exit using the exit function: $ exit




















Level 8:
Sign in using 

$ ssh bandit7@bandit.labs.overthewire.org -p 2220

Well to cat data.txt would output tons of passwords so to isolate the password next to the world millionth use

$ cat data.txt | grep millionth

Then the output will be:

millionth	dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc

Then your password will be 

dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc (yours will be different)

Then you can exit using the exit function: $ exit























Level 9:

Sign in using 

$ ssh bandit8@bandit.labs.overthewire.org -p 2220

Then to find the password that shows up once there is a function by sorting them and then using a uniq function like the following:

$ sort data.txt | uniq -u

Then the password will be output:

4CKMh1JI91bUIZZPXDqGanal4xvAg0JM yours will be different

Then you can exit using the exit function: $ exit

























Level 10:

Sign in using 

$ ssh bandit9@bandit.labs.overthewire.org -p 2220

Use:

$ cat data.txt | strings

Then there will be a good amount of outputs but there will be a bunch of == and within that output there will be the password:

FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey (yours will be different)


Then you can exit using the exit function: $ exit



























Level 11:

Sign in using:

$ ssh bandit10@bandit.labs.overthewire.org -p 2220

Then use cat data.txt | base64 --decode

The base64 –decode decodes the message in the data.txt file

The output will be:

The password is dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr (your password will be different)

Then you can exit using the exit function: $ exit

























Level 12:

Sign in using 

$ ssh bandit11@bandit.labs.overthewire.org -p 2220

The password is scrambled by every 13th letter and to be able to decode that the following function can be used 

cat data.txt | tr '[A-Za-z]' '[N-ZA-Mn-za-m]'

This will decode the password

The original output was

Gur cnffjbeq vf 7k16JArUVv5LxVuJfsSVdbbtaHGlw9D4

After the function: 

The password is 7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4 (yours will be different)

Then you can exit using the exit function: $ exit



















Level 13:

Sign in using 

$ ssh bandit12@bandit.labs.overthewire.org -p 2220
Create a working directory in /tmp:
Run mkdir /tmp/jrr(any name).
Copy and rename the file:
Copy data.txt to the new directory: cp data.txt /tmp/jrr
Navigate to the directory: cd /tmp/jrr.
Reverse the hexdump:
Run xxd -r data.txt > bandit to convert the hexdump back into a binary file.
Determine the compression method:
Run file bandit to identify the file type and compression method.
Decompress the file:
If the file is gzip compressed:
Add the .gz extension: mv bandit bandit.gz.
Decompress it: gunzip bandit.gz.
Check the file type again using file bandit.
If the file is bzip2 compressed:
Add the .bz2 extension: mv bandit bandit.bz2.
Decompress it: bzip2 -d bandit.bz2.
If the file is a tar archive:
Add the .tar extension: mv bandit bandit.tar.
Extract it: tar -xf bandit.tar.
Repeat the above steps:
Continuously identify the file type using file.
Update the file extension and decompress according to the identified method (gzip, bzip2, or tar).
Continue decompressing until the file contains ASCII text:
After decompressing, the file type will indicate ASCII text.
Run cat <filename> to read the file contents.
Retrieve the password:
The password will be displayed in the output of the cat command.
Example: The password is FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn (yours will be different)
Then you can exit using the exit function: $ exit














Level 14:
Sign in using 
$ ssh bandit13@bandit.labs.overthewire.org -p 2220

Then use ls 

That should print 

Sshkey.password

A file with nonsense

Then to enter the other user use 

ssh -i sshkey.private bandit14@localhost -p 2220

You must specify port 2220 or else wont work

Then use:

 $ cd /etc/bandit_pass/

Once in the directory use cat bandit14

Then you will get your password:

MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS (yours will be different)

Dont sign out






Level 15:

Still signed in form the past level use:

$ nc localhost 30000

Then there will be an empty area where you will paste the password you got earlier 

Then it will print 

Correct!
8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo (yours will be different)

Dont sign out






























Level 16:
Sign in using 
$ ssh bandit16@bandit.labs.overthewire.org -p 2220

kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx

Then once in run an nmap scan:

$ nmap -v -A -T4 -p 31000-32000 localhost

Then look for a port that runs only ssl not ssl and echo

That should be port 31790

Confirm that by looking for a port that is open and says ssl/unknown

To entor that port use 

openssl s_client -connect localhost:31790 -quiet

Then put in the password 

It will give you an rsa key which you should copy and past into a folder i named it bandit17.key:

$ nano bandit17.key

Then once nano’ed in i pasted the key then ran:

$ Chmod 600 bandit17.key

Then ran:

$ ssh -i bandit17.key bandit17@localhost -p 2220

Once in i used the path to get the password for the level:

$cd /etc/bandit_pass

Then did:

$ cat bandit17

Then i got the password

EReVavePLFHtFlFsjn3hyzMlvSuSAcRD (yours will be different)

































Level 18

Sign in using 

ssh bandit17@bandit.labs.overthewire.org -p 2220

Then used the password from before

Then once inside used 

$ diff passwords.old passwords.new

Then it pasted two passwords

< ktfgBvpMzWKR5ENj26IbLGSblgUG9CzB
---
> x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO


Used one didnt work used the other and it pasted out byebye and kicked me out which is the clue that that is the correct password.

x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO (yours will be different)




















Level 19:

No need to sign in to anything just use 

$ ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme

This command will automatically output thefile readme and will output the password

cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8






























Level 20:
Sign in using:

$ ssh bandit19@bandit.labs.overthewire.org -p 2220

Then once in run:

$ ls

This will show 

Bandit20-do 

So to be assemble to see the pass word we know that the only person allowed to see this is bandit20 so you can run this to get the printed password. You write the path to where the password would be and you will get the output.

$ ./bandit20-do cat /etc/bandit_pass/bandit20
0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO (yours will be different)

























Level 20:




 














