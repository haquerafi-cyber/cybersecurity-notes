# ওয়েবসাইটে লুকানো **folder, file, subdomain** খুঁজে বের করে।

## Important Flags

---

```jsx
-u          # target URL দিবে
-w          # wordlist file path দিবে
-t          # কত thread এ scan হবে
-x          # file extension brute force করবে
-o          # output file এ result save করবে
-s          # কোন status code show করবে
-b          # কোন status code hide করবে
-k          # SSL certificate ignore করবে
-e          # full URL show করবে
-r          # redirect follow করবে
-q          # quiet mode (কম output)
-a          # custom user-agent set করবে
-c          # cookie add করবে
-H          # custom header add করবে
-p          # proxy use করবে
-d          # DNS domain দিবে
-i          # wildcard DNS ignore করবে
--delay     # request এর মাঝে delay দিবে
```

## Basic Syntax

---

```jsx
gobuster MODE -u URL -w WORDLIST

MODE = dir / dns / vhost
```

## **Directory Bruteforce**

---

```jsx
gobuster dir -u http://target.com -w /usr/share/wordlists/dirb/common.txt

extension scan:
gobuster dir -u http://target.com -w wordlist.txt -x php,html,txt
```

## Specific Status Code

---

```jsx
gobuster dir -u http://target.com -w wordlist.txt -s 200,301,302
```

## Hide Status Code

---

```jsx
gobuster dir -u http://target.com -w wordlist.txt -b 404
```

## DNS Subdomain Scan

---

```jsx
gobuster dns -d target.com -w subdomain.txt

-d     # domain name
```

## Virtual Host Scan

---

```jsx
gobuster vhost -u http://target.com -w subdomain.txt
```

## Proxy Use

---

```jsx
gobuster dir -u http://target.com -w wordlist.txt -p http://127.0.0.1:8080

-p     # proxy use
```