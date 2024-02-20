
```js
var str = 'global';  
  
function printStr() {  
    console.log(str);  
}  
  
function testScope() {  
    var str = 'local';  
    printStr();  
}

testScope(); // global
printStr(); // global
```

在有些語言中呼叫`testScope()`會輸出`local`的資訊。

- [[variable]] 變量
- [[value]] 值
- [[variable scope]], 為 [[Name binding（static  or dynamic binding）]]的作用域。這邊所代表的意思是有可能`x`在不同的function 會合不同的值做聯繫，因此在不同的作用域會有不同的值。

[[scope]] 代表的是...


static scope 與 dynamic scope的差別在於，Name binding 的時機不同。前者是early binding，後者是late binding。

而python/java/cpp都是static scope。lisp是late binding。因為選擇前者有個好處是，執行階段會比較快。
### static scope
```js

var str = 'global';  
  
function printStr() {  
    console.log(str);  
}  
  
function testScope() {  
    var str = 'local';  
    printStr();  
}

testScope(); // global
printStr(); // global
```

在這個例子中，因為`Name binding`在編譯器階段就已經做完，因此在 `printStr`中的`str`變數就只能與全域變數中的做連接。

### dynamic scope
```js
var str = 'global';  
  
function printStr() {  
    console.log(str);  
}  
  
function testScope() {  
    var str = 'local';  
    printStr();  
}

testScope(); // global
printStr(); // local
```
而`Name binding`的階段是在執行的時候，因此`printStr`就會訪問到最近的變數，就是`testScope`裡面的 `str`。所以其實可以把`str`當作一個`stack`。只要離開函數，就會被釋放。
