---
tag: #Linux 
---
```bash
systemctl list-units
```
> 枚舉所有unit

---
```bash
systemctl list-units-files
```
> 枚舉所有配置文件

---
```bash
systemctl cat <unit-name>
```
> 查看配置文件
---
```bash
systemctl edit <unit-name>
```
> 編譯配置文件

---
```bash
systemctl daemon-reload
```