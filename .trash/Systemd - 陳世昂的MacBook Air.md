---
tag: #Linux
---

在[[Linux]]的一個子程序, [[init]]進程
OS 啟動時, 作為第一個[[進程]]所啟動, [[PID]]為1

可以管理服務, 用unit的方法管理

有依賴的管理，在不同的進程之間管理依賴

在[[htop]] 裡面按下T鍵 可以看到PID 為1 的
![[Pasted image 20230825075037.png]]

後面就都是他的[[子進程]]

在[[pstree]]裡面可以看到進程樹
![[Pasted image 20230825075428.png]]

使用[[Systemd]]的命令可以用[[systemctl]]

### 創建systemd 的進程

需要編寫systemd 的配置檔案
在[[systemctl]]裡面可以查看當前的配置文件

三個地方的儲存位置
```txt
/etc/systemd/system/ 自定義的系統文件（自己創建的）
/lib/systemd/system/ 標準內的系統文件
/usr/lib/systemd/system/ 通過包管理器創建的文件
```

^69919d

必須包含三部分
[unit]
[install]
[service]

查看logs可以用[[journalctl]]
```bash
journalctl -u <unit-name>
```

![[Pasted image 20230825121615.png]]