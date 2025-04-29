# My Research

* * *

## [Python Dirty Arbitrary File Write to RCE via Writing Shared Object Files Or Overwriting Bytecode Files](https://siunam321.github.io/research/python-dirty-arbitrary-file-write-to-rce-via-writing-shared-object-files-or-overwriting-bytecode-files)

<div class="page_information">
  <p>April 29, 2025</p>
</div>

> In web security, it has a vulnerability class called "arbitrary file write" (AFW), where the attacker can create or overwrite files on the server, which potentially lead to RCE (Remote Code Execution). For instance, if a web application that uses PHP and Apache, an attacker could create a new `.htaccess` file to gain RCE (A real-world example can be seen in [one of my bug bounty findings](https://siunam321.github.io/ctf/Bug-Bounty/Wordfence/how-i-found-my-first-vulnerabilities-in-6-different-wordpress-plugins-part-2/#flawedmissing-filename-validation---advanced-file-manager-with-premium-add-on-advanced-file-manager-shortcodes)). In Apache, the `.htaccess` file is to make configuration changes on a per-directory basis. However, with the help of AFW vulnerability, attack can add the following rules to tell Apache to treat files with `.txt` extension as a PHP script: [...]

Tags: Arbitrary File Write, Python

## [Attempted Research in PHP Class Pollution](https://siunam321.github.io/research/attempted-research-in-php-class-pollution)

<div class="page_information">
  <p>February 19, 2025</p>
</div>

> After reading the Ruby class pollution research from Doyensec and re-read the blog post about class pollution in Python, I started to think this research question:
>   
> - If class pollution is possible in Python and Ruby, does that mean other programming languages that support OOP (Object-Oriented Programming) is inherently vulnerable to class pollution?[...]

Tags: Class pollution, PHP