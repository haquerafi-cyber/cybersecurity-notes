# How to run in the terminal

```jsx
msfconsole   // [with banner]
msfconsole -q // [without banner]
```

# Advanced search

```jsx
search name:ms08-067                                      //[Search by module name]

search type: exploit, auxiliary, post, payload            //[Filter by module type]

search platform:windows                                  // [ Target platform]

search author:rafi                                       // [Modules by author]

search cve:2021-45046                                    // [Search by CVE ID]

search path:scada                                      // [Search within module paths]
 
search app:client                                   // [ Client or server attacks]ackground a session
```

# How to set

```jsx
set [payload]
set [auxiliary]
set [rhost]
set [rport]
set [path of the file] //for password crackg or bruteforce
```

# Start the attack

```jsx
exploit or run
```

# Background a Session

```jsx
background 

ctrl+z
```