### 阻塞與非阻塞
- 阻塞：代表著當前的任務正在等待其他任務的完成，只不過這樣的等待是非常浪費系統資源的。
- 非阻塞：代表任務並不會有毫無意義的等待發生，因為只要一發生等待，就切換任務項目。

# 進程與進程池

進程是一個運行程序的單位，他會有獨立的記憶體。而進程池是為了解決大量的進程創建問題，成千上百的進程如果要創建，就會很麻煩，因此就有了進程池。


## 目錄
### 單進程
- [ ] 單進程阻塞
- [ ] 單進程不阻塞

### 多進程
- [ ] 多進程的錯誤阻塞
- [ ] 多進程的正確阻塞
- [ ] 多進程不阻塞

### 守護進程
- [ ] 守護進程阻塞
- [ ] 守護進程不阻塞

### 進程池
- [ ] 進程池阻塞 
- [ ] 進程池不阻塞
- [ ] 進程池異步
- [ ] 進程池同步

## 程式說明
```python
process.start() # 生成進程
process.join() # 使主進程阻塞等待子進程結束

```

### 單進程阻塞
```python
import multiprocessing  
  
def worker(name):  
    print('%s: %s start...' % (time.strftime('%X'), name))  
    time.sleep(2)  
    print('%s: %s done...' % (time.strftime('%X'), name))  
  
# 單進程阻塞  
def block():  
    t = multiprocessing.Process(target=worker, args=('张三',))  
    t.start()  
  
    # 阻塞中  
    t.join()  
    print('Finished')  
  
if __name__ == "__main__":  
    block()
```

### 單進程不阻塞
```python
import multiprocessing  
  
def worker(name):  
    print('%s: %s start...' % (time.strftime('%X'), name))  
    time.sleep(2)  
    print('%s: %s done...' % (time.strftime('%X'), name))  
  
# 單進程不阻塞  
def block():  
    t = multiprocessing.Process(target=worker, args=('张三',))  
    t.start()  
  
    print('Finished')  
  
if __name__ == "__main__":  
    block()
```

### 多進程錯誤阻塞
> 這樣會導致 `t1` 執行完成後，才會創建 `t2`進程。使得原本想要阻塞主進程的任務時間大幅增加，`Time : t1 + t2`

```python
import multiprocessing  
  
def worker(name):  
    print('%s: %s start...' % (time.strftime('%X'), name))  
    time.sleep(2)  
    print('%s: %s done...' % (time.strftime('%X'), name))  
  
# 單進程不阻塞  
def block():  
    t1 = multiprocessing.Process(target=worker, args=('张三',))  
    t1.start()
    t1.join()
    t2 = multprocessing.Process(target=worker, args=('李四',))
    t2.start()
    t2.join()
    print('Finished')  
  
if __name__ == "__main__":  
    block()
```

### 多進程的正確阻塞
```python
import multiprocessing  
  
def worker(name):  
    print('%s: %s start...' % (time.strftime('%X'), name))  
    time.sleep(2)  
    print('%s: %s done...' % (time.strftime('%X'), name))  
  
# 單進程不阻塞  
def block():  
    t1 = multiprocessing.Process(target=worker, args=('张三',))
		t2 = multprocessing.Process(target=worker, args=('李四',))
    t1.start()
    t2.start()
    t1.join()
    t2.join()
    print('Finished')  
  
if __name__ == "__main__":  
    block()
```

### 多進程不阻塞
```python
import multiprocessing  
  
def worker(name):  
    print('%s: %s start...' % (time.strftime('%X'), name))  
    time.sleep(2)  
    print('%s: %s done...' % (time.strftime('%X'), name))  
  
# 單進程不阻塞  
def block():  
    t1 = multiprocessing.Process(target=worker, args=('张三',))
		t2 = multprocessing.Process(target=worker, args=('李四',))
    t1.start()
    t2.start()
    t1.join()
    t2.join()
    print('Finished')  
  
if __name__ == "__main__":  
    block()
```

### 守護進程
守護進程的特點就是會在主程序死掉之後，也跟著一起死掉

...

# Reference
- [1.](https://www.cnblogs.com/tujia/p/13686684.html)
- [2. 同步異步、阻塞與非阻塞](http://www.pulpcode.cn/2017/03/18/block-non-block-and-syn-asyn/)