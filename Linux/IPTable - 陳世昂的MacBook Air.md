連線有三種類型
- input
- forward
- output

連線模式
- accept
- drop
- reject


```
iptables -nvL
```

### 拒絕
```
// -A 建立規則
// -s 目標IP
// -j 連線模式
// -p TCP/UDP
// -dport 協議


iptables -A INPUT -s <ip> -j DROP

iptables -A INPUT -p tcp -dport ssh -j DROP
```