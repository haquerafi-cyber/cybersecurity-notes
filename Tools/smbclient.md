- Information
    
    <aside>
    💡
    
    ## 🔹 smbclient কী?
    
    **smbclient** হলো একটা টুল, যেটা দিয়ে তুমি **SMB share করা ফোল্ডারে ঢুকতে পারো**।
    
    </aside>
    
    <aside>
    💡
    
    ## 🎯 এটা কী কাজে লাগে?
    
    ✔ শেয়ার করা ফোল্ডার লিস্ট দেখতে
    
    ✔ ফাইল ডাউনলোড করতে
    
    ✔ ফাইল আপলোড করতে
    
    ✔ SMB সার্ভারে লগইন করতে
    
    </aside>
    

# Basic usage

---

```jsx
smbclient //IP/share [options]
```

# Options/Flags

---

```jsx
-L → Share list দেখায়

smbclient -L //192.168.1.10 -N
```

```jsx
-U → Username দেওয়া

smbclient //192.168.1.10/share -U admin
```

```jsx
-N → No password (anonymous login)

smbclient //192.168.1.10/share -N
```

```jsx
-p → Port change করা (default 445)

smbclient //192.168.1.10/share -p 445
```

```jsx
-W → Workgroup/Domain দেওয়া

smbclient //192.168.1.10/share -U user -W WORKGROUP
```

```jsx
-I → Direct IP specify

smbclient //SERVER/share -I 192.168.1.10
```

```jsx
-c → এক লাইনে command চালানো

smbclient //192.168.1.10/share -U user -c "ls"
```

```jsx
--option= → Custom config option

smbclient //192.168.1.10/share --option='client min protocol=NT1'
```

```jsx
-m → SMB version নির্ধারণ

smbclient //192.168.1.10/share -m SMB2
```

```jsx
-d → Debug level

smbclient //192.168.1.10/share -d 3
```

```jsx

```