# Manipulating the WebSocket handshake to exploit vulnerabilities | Dec 19, 2022

## Introduction

Welcome to my another writeup! In this Portswigger Labs [lab](https://portswigger.net/web-security/websockets/lab-manipulating-handshake-to-exploit-vulnerabilities), you'll learn: Manipulating the WebSocket handshake to exploit vulnerabilities! Without further ado, let's dive in.

- Overall difficulty for me (From 1-10 stars): ★★★☆☆☆☆☆☆☆

## Background

This online shop has a live chat feature implemented using [WebSockets](https://portswigger.net/web-security/websockets).

It has an aggressive but flawed XSS filter.

To solve the lab, use a WebSocket message to trigger an `alert()` popup in the support agent's browser.

## Exploitation

**Home page:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012019.png)

**Live chat:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012033.png)

**To intercept WebSocket traffics, we can use Burp Suite.**

In the previous lab, we found that the `message` in **WebSocket is vulnerable to XSS(Cross-Site Scripting).**

**Now, let's try to send a test message:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012402.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012411.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012419.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012438.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012449.png)

**In here, we can try to send a XSS payload:**
```html
<img src=error onerror='alert(document.domain)'>
```

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012635.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012646.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012655.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012746.png)

Hmm... `Attack detected`... Maybe the web application has a filter that filters XSS payload.

**Let's refresh the page and try again:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219012922.png)

Ah... It even blacklisted my IP address!

**To bypass that, we can try to use the `X-Forwarded-For` HTTP header:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219013110.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219013130.png)

**We've successfully bypassed the IP address blacklist!**

**In Burp Suite, we can add an option that every requests will add a custom header:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219013243.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219013316.png)

Now, we need to bypass the XSS filter.

**Since the error says `Event handler`, we can bypass that via this payload:
```html
<img src=1 OnErRoR=alert(document.domain)>
```

**Let's try that:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219014100.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219014113.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219014655.png)

Again, it detected the `alert()`.

**To bypass that, we can use \` to replace the `()`:**
```html
<img src=1 OnErRoR=alert`document.domain`>
```

**Also, we should change our `X-Forwared-For` IP address, as it's blacklisted:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219014925.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219014936.png)

**Finally, we can send our XSS payload:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219015432.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219015440.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219015447.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219015518.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/Portswigger-Labs/WebSockets/WS-2/images/Pasted%20image%2020221219015525.png)

Nice! We've successfully triggered it!

# What we've learned:

1. Manipulating the WebSocket handshake to exploit vulnerabilities