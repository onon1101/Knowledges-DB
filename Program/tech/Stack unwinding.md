當出現例外處理的時候，並且必須要將錯誤的stack 往上回朔直到找到能接住例外的程式碼的整個過程。稱為`Stack unwinding`
```js
fn a() {
 throw error();
}
fn b() {
	a()
}
fn c() {
	b()
}

fn main() {
	try {
		c()
	} catch (error)
		println(error)
	}
}
```

