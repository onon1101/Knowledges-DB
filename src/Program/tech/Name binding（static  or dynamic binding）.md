有兩種binding 的方式
- static binding(early binding)
- dynamic binding(late binding)



其中 他們最大的感官差別是在使用虛擬函數的時候，因為是在編譯的時候才將 變數與值聯繫起來。
```java
class Animal {  
    void eat() {  
        System.out.println("animal is eating...");  
    }  
}  
  
class Dog extends Animal {  
    void eat() {  
        System.out.println("dog is eating...");  
    }  
  
    public static void main(String args[]) {  
        Animal d1 = new Dog();
        d1.eat();  
        // $ dog is eating...
    }  
}
```


https://yuehhua.github.io/2019/12/01/name-binding-and-dispatch/