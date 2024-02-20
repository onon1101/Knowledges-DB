


使用`tor`啟動之後，就可以開始使用`tor proxy`代理。

但以下兩個工具對於獲取公網ip來說好像有問題，因為有時候沒辦法輸出ip。
[[torsock]]
[[torify]]

但在使用python 就能獲取`ip`
```python

import socks
import socket
socks.setdefaultproxy(proxy_type=socks.PROXY_TYPE_SOCKS5, addr="127.0.0.1", port=9050)
socket.socket = socks.socksocket

import requests
print(requests.get("http://icanhazip.com").text)

```

https://stem.torproject.org/faq.html#how-do-i-request-a-new-identity-from-tor

https://gist.github.com/NullPointerMaker/b863e817634a2c308012bee7ee1b12f2

- [有多少tor 節點](https://metrics.torproject.org/relayflags.html?start=2023-10-06&end=2024-01-04&flag=Running&flag=Exit&flag=Fast&flag=Guard&flag=Stable)

https://blog.gslin.org/archives/2022/03/10/10589/%E4%BD%BF%E7%94%A8-tor-%E7%9A%84-onion-%E4%BD%8D%E7%BD%AE%EF%BC%8C%E8%80%8C%E9%9D%9E%E9%80%8F%E9%81%8E-exit-node-%E5%AD%98%E5%8F%96%E7%B6%B2%E7%AB%99%E7%9A%84%E5%A5%BD%E8%99%95/