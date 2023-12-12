採用[[Reactor]]的設計方法。

並且最重要的是，他會建立事件循環。只不過從解析主程式碼到事件循環的部分都是由單線程的處理方式。其中處理異步IO採用的是[[LIBUV]]的函式庫。

每次在解析主函數時，事件循環就會暫停。直至解析完成。

[[Event Demultiplexer]] 這我還不知道他舉體在架構的哪一部分，但他是一個抽象概念，實作的部分在MS, linux, MacOS都不一樣。
- 這是linux 的實作方法：[[epoll]]
### Reference
- [1.](https://www.google.com/search?q=Reactor+nodejs&sca_esv=590053957&sxsrf=AM9HkKnmyZK6k5eD4AiFQDrHjsd5_cebjg:1702363402564&ei=CgF4ZfSKIrDM1e8PyrWHuAE&ved=0ahUKEwj0t43vpYmDAxUwZvUHHcraARcQ4dUDCBA&uact=5&oq=Reactor+nodejs&gs_lp=Egxnd3Mtd2l6LXNlcnAiDlJlYWN0b3Igbm9kZWpzMgQQIxgnMggQABgIGB4YDTIGEAAYCBgeSMcJUIEBWNMIcAF4AZABAJgBWaAB3AOqAQE3uAEDyAEA-AEBwgIHECMYsAMYJ8ICChAAGEcY1gQYsAPCAgUQABiABMICChAAGIAEGIoFGEPCAgkQABgeGPEEGArCAgQQABgewgIGEAAYBRgewgILEAAYCBgeGPEEGArCAggQABgIGB4YD8ICBxAAGIAEGA3CAggQABgFGB4YDcICChAAGAgYHhgNGA_iAwQYACBBiAYBkAYK&sclient=gws-wiz-serp)
- [2.](https://zhuanlan.zhihu.com/p/424829677)
- [執行順序](https://www.laitimes.com/article/5ackl_5qtnu.html)
- 