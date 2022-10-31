# Deprecated

## Overview

- Overall difficulty for me: Medium

**In this challenge, we can spawn a docker instance:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221028232846.png)

## Find the flag

**Home page:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221028232920.png)

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221028233403.png)

**We can press `Ctrl + U` to view the source page:**
```html
<script src="js/app.js"></script>
```

**The `app.js` looks interesting:**
```js
function senddata() {
	var search = $("#search").val();
	var replace = $("#replace").val();
	var content = $("#content").val();

	if(search == "" || replace == "" || content == "") {
		$("#output").text("No input given!");
	}
	$.ajax({
		url: "ajax.php",
		data: {
			'search':search,
			'replace':replace,
			'content':content
		},
		method: 'post'
	}).success(function(data) {
		$("#output").text(data)
	}).fail(function(data) {
		$("#output").text("Oops, something went wrong...\n"+data)
	})
	return false;
}
```

**This JavaScript shows us how the parameters being parsed.**

**It's sending a POST request to `ajax.php`, and 3 POST parameters: `search`, `replace`, `content`.**

**Also, we can capture the POST request via developer tool:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221028233726.png)

Hmm... **`X-Powered-By: PHP/5.5.9-1ubuntu4.29`. I don't see any vulnerabilies in this PHP version.**

**Anyways, when I try to test Local File Inclusion (LFI) vulnerability, something interesting:**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221029001303.png)

`Blacklisted keywords!`?

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221029001324.png)

**Looks like it's blacklisted the `pass` word.**

**Then, I was stuck at here for a long time, until I found this [Medium blog](https://captainnoob.medium.com/command-execution-preg-replace-php-function-exploit-62d6f746bda4):**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221030050949.png)

**Let's try this payload!**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221030051006.png)

Oh!! It's vulnerable to remote code execution!

**Let's execute commands!**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221030051253.png)

Gosh! I hate filtering lul. **Looks it's filtering `system`, `shell_exec`, `exec`.**

**However, blacklisting always doesn't covered enough evil words! Like the double backticks \`\`.**

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221030051337.png)

Let's `cat` the flag!

![](https://raw.githubusercontent.com/siunam321/CTF-Writeups/main/GuidePoint-Security-Oct27-2022/images/Pasted%20image%2020221030051446.png)

# Conclusion

What we've learned:

1. Remote Code Execution in PHP `preg_replace()`