## **showmount** 👉 NFS server এ কোন কোন folder share করা আছে সেটা দেখার টুল

## Example Flow

---

```jsx
showmount -e 192.168.1.10   # share খুঁজলাম
mkdir /tmp/nfs              # folder বানালাম
mount -t nfs 192.168.1.10:/share /tmp/nfs   # mount করলাম
এখন ভিতরের file access করতে পারবা
```

## সব flag একসাথে

---

```jsx
showmount -e <IP>      # server এ কোন কোন export (share) আছে দেখায়
showmount -a <IP>      # কে কে mount করছে দেখায়
showmount -d <IP>      # কোন directory mount করা আছে দেখায়
showmount -h           # help দেখায়
showmount -v           # version দেখায়
```

## Basic Syntax

---

```jsx
showmount [option] <target_IP>
```

## Export (share) দেখার জন্য

---

```jsx
showmount -e 192.168.1.10

server কোন folder share করছে দেখাব

```

## কে কে connect করছে দেখার জন্য

---

```jsx
showmount -a 192.168.1.10

কোন user/IP already mount করছে
```

## কোন directory use হচ্ছে দেখার জন্য

---

```jsx
showmount -d 192.168.1.10
```