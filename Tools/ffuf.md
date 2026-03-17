## লুকানো **URL, directory, file, parameter** খুঁজে বের করা।

# Basic Syntax

---

```jsx
ffuf -u URL -w WORDLIST

example:
ffuf -u http://site.com/FUZZ -w wordlist.txt
```

# Flags

---

```jsx
সবচেয়ে বেশি ব্যবহার হয়

-u → target url       //target URL দেয়।

-w → wordlist        //wordlist দেয়।

-mc → match code      //কোন status code দেখাবে।

-fc → filter code    //কোন status code লুকাবে।

-fs  → filter size   //একই size response লুকায়।

-e → extension        //extension যোগ করে।

-t → threads         //speed control করে।

-o → output          //result save।
```