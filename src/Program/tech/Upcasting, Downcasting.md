```java
class Animal

class Cat

class Dog
```

### 向上轉型

暫時被隱藏起來。

```java
Cat c = new Cat();
Animal a = (Animal) c;
```
### 向下轉型

會失去屬性

```java
Animal a = new Animal;
Dog d = (Dog) a;
```