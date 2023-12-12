---
tag: #Linux 
---

# Problem
---
	先學習編譯器，此[項目](https://www.youtube.com/watch?v=AuPStbaM1cY&t=589s)暫停
- 1:09:09 - 大量使用環狀雙重link
- 1:27:15 - hash table
- 

---
linux 基金會會長期維護一些linux 版本
提交程序碼的話在 linux-next -> mainline -> stable

1997 年 linux kernal 程式碼 70萬行
現在 3000萬行

[[context switch]](上下文切換) 在linux 到了 奈秒等級

[[posix]]
[[ebpf]]

linux kernal 大量用到巨集（[[macro]]）

c 語言 [[Struct]] 順序可能會變換
[[Struct Padding]]

元數據 = 描述資料的資料

需要從struct 成員回推struct 的起始位置

[[container_of]]
### 大量使用 [[circular doubly-linked list]]
> 3,2,1,0 0,1,2,3
- 0 節點時，頭尾就等於自己
- 相比線性單向的，不用null作為特殊判斷，避免拜訪NULL的記憶體位置
- 可以保留第一次存取的指標，當目前的指標與第一次相同就表示已經繞完一個圈了
- null 在特定條件是可以存取的
	- arm cortex-m interrupt vector
	![[Pasted image 20230827175343.png]]
	可以看到他的`0x00000`是可以被存取的
>如果mmu 在剛開始的時候存取到記憶體0時，會觸發page fault
### Hash table
gnu gperf hash
webkit 有用到 上面的工具(gperf)
很多方式可以避免碰撞

[[Clustering]]

[[jump table]]
> switch v.s if else-if


1:41:19
### Reference
---
[youtube]
[hackmd](https://hackmd.io/@sysprog/SkmKiSfh2)