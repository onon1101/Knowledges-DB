
### 終端
```
ssh-keygen

ssh-copy-id -i ~/.ssh/id_rsa.pub <USER>@<IP>

vim ~/.ssh/config
```

*config*
```
Host <name>
	HostName <IP>
	User <USER>
	IdentityFile <id_rsa>
```

```
ssh <name>
```




