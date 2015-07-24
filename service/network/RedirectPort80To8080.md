Run as root:
```
# iptables -t nat -A PREROUTING -p tcp --dport 80 -j REDIRECT --to-port 8080
```
As loopback devices (like localhost) do not use the prerouting rules, if you need to use localhost, etc., add this rule as well (thanks @Francesco):
```
# iptables -t nat -I OUTPUT -p tcp -d 127.0.0.1 --dport 80 -j REDIRECT --to-ports 8080
```
NOTE: The above solution is not well suited for multi-user systems, as any user can open port 8080 (or any other high port you decide to use), thus intercepting the traffic. (Credits to CesarB).
EDIT: as per comment question - to delete the above rule:
```
# iptables -t nat --line-numbers -n -L
```
This will output something like:
Chain PREROUTING (policy ACCEPT)
num  target     prot opt source               destination         
1    REDIRECT   tcp  --  0.0.0.0/0            0.0.0.0/0           tcp dpt:8080 redir ports 8088
2    REDIRECT   tcp  --  0.0.0.0/0            0.0.0.0/0           tcp dpt:80 redir ports 8080
The rule you are interested in is nr. 2, so to delete it:
```
# iptables -t nat -D PREROUTING 2
```
References:
http://serverfault.com/questions/112795/how-can-i-run-a-server-on-linux-on-port-80-as-a-normal-user
