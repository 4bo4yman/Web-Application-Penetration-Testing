<h1>$${\color{red}Cookie} \space {\color{Goldenrod}Values}$$</h1>
 

#### Some WAF systems reveal their presence through cookies. They release their own cookie during the HTTP communications.

### 1. Ctrix Netscaler
uses some different cookies in the HTTP responses like ```ns_af``` or ```citrix_ns_id``` or ```NSC_``` Is common, example:

```
Cookie: NSC_TASS=xyz7890mnopqrst; Path=/; HttpOnly
```

### 2. F5-IP ASM (Application Security Manager)
uses cookies starting with ```TS``` , example:

```
Cookie: TS0123456789abcdef=0987654321abcdef0987654321abcdef; Path=/; HttpOnly; Secure
```

### 3. Barracuda
uses two ```cookies barra_counter_session``` and ```BNI__BARRACUDA_LB_COOKIE``` Is common , example:

```
Cookie: BNI__BARRACUDA_LB_COOKIE=abcdefgh12345678; Path=/; HttpOnly; Secure
```
![image](https://github.com/user-attachments/assets/178eb80b-c752-4fe0-b2fa-468b41887540)




