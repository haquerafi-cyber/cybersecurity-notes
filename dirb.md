- 🔎 DIRB কি?
    
    DIRB হলো ওয়েব ডিরেক্টরি brute-force টুল। এটা hidden directory/file খুঁজে বের করে (যেমন: `/admin`, `/backup`, `/config.php` ইত্যাদি)।
    
- Important Tips
    
    ✔️ Dirb slow tool
    ✔️ বড় wordlist দিলে সময় বেশি লাগবে
    ✔️ WAF থাকলে detect করতে পারে
    ✔️ Reporting এর জন্য screenshot রাখবে
    

# কাজ

---

Hidden directory ও file brute-force করে বের করা।

# Basic Structure

---

```jsx
dirb <URL> <WORDLIST> [OPTIONS]
```

# Basic Scan

---

```jsx
dirb http://target.com   [Default wordlist দিয়ে scan করবে।]
```

# Custom Wordlist

---

```jsx
dirb [target] wordlist/wordlist-location
```

# **📂 ২️⃣ Wordlist Location (Kali Linux)**

```jsx
/usr/share/wordlists/dirb/
```

# 🚩 DIRB Flags

---

## **-X  → Extension Specify**

---

### নির্দিষ্ট extension খুঁজতে।

```jsx
dirb http://target.com -X .php [single extention]

dirb http://target.com -X .php,.html,.txt [multiple extension]
```

## -o → Output File Save

---

Result file এ save করবে।

```jsx
dirb http://target.com -o result.txt
```

## -f → Fine Tuning (False Positive কমানো)
DIRB মাঝে মাঝে 404 page কে valid ধরে। -f দিলে better filtering করে।

---

```jsx
dirb http://target.com -f
```

## -c → Cookie Add (Authenticated Scan)

---

Login করার পর session cookie দিয়ে hidden area scan।

```jsx
dirb http://target.com -c "PHPSESSID=your_session_id"

👉 Browser → Inspect → Application → Cookies থেকে session নেবে।
```

## -H → Custom Header Add

---

Custom header পাঠাতে।

```jsx
single header,
dirb http://target.com -H "User-Agent: Mozilla/5.0"

Multiple header:
dirb http://target.com -H "X-Forwarded-For: 127.0.0.1"

👉 WAF bypass testing এ কাজে লাগে।
```

## -a → User-Agent Change

---

```jsx
dirb [http://target.com](http://target.com/) -a "Mozilla/5.0"
```

## -u → Basic Authentication

---

যদি site basic auth protected হয়।

```jsx
dirb http://target.com -u username:password
```

## -r → Recursive Scan Disable

---

DIRB default recursive যায়।

-r দিলে recursion বন্ধ।

```jsx
dirb http://target.com -r
```

## -S → Silent Mode

---

কম output দেখাবে।

```jsx
dirb http://target.com -S
```

# status code

```jsx
200	Valid	Open করে দেখবে

301/302	Redirect	                 Important হতে পারে

403	Forbidden                      	Bypass চেষ্টা করবে

401	Unauthorized	                   Auth দরকার

500	Server Error	                  Vulnerable হতে পারে
```