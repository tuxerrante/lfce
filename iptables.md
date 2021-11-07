
```sh
iptables -L -nv --line-numbers 

# Allow traffic from host X only on port Y ...


# Redirect IN traffic to other network
iptables -t nat -A PREROUTING -i eth0 -p tcp --dport 80 -j DNAT \
	    --to-destination 10.0.4.2:80

# Redirect local IN traffic port
iptables -t nat -I PREROUTING -i lo -p tcp --dport 8888 -j REDIRECT --to-port 9999

# 
iptables -A INPUT -p tcp --dport 432 -m physdev --uid-owner charles


# Log and DROP
iptables -A INPUT -i eth1 -s 10.0.0.0/8 -j LOG --log-prefix "IP_SPOOF A: "
iptables -A INPUT -i eth1 -s 10.0.0.0/8 -j DROP


# Allow out traffic from established connections:
iptables -A FORWARD -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A OUTPUT -m state --state ESTABLISHED,RELATED -j ACCEPT

```


## References: 
- http://web.mit.edu/rhel-doc/4/RH-DOCS/rhel-sg-it-4/ch-fw.html
- https://www.cyberciti.biz/tips/linux-iptables-examples.html
