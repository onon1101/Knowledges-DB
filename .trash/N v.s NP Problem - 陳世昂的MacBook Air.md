### 要怎麼分類問題的難度?

### [[Big(O) notation]]
用來評估演算法的效率
例如：排序演算法
```txt
排序：n (n-1) ... 3 2 1 => 1 2 3 ... (n-1) n
因此排序的次數為:n(n-1)/2
```

複雜度：$$\frac{n^2-n}{2} = Big(n^2)$$
大致上等於 Ｏ(n^2) 的複雜度, 為什麼要忽略常數？
Ａ：在不同電腦上執行演算法的效率都不同, 常數項會放大效能的誤差
所以Big(O) 主要是查看每個演算法**困難性的增長幅度**


---
### 什麼是簡單的問題
*科學家對此還是有些爭論關於簡單問題的定義*

**Easy** : Polynomial time algorithm (多項式時間演算法)
e.g. $O(n^{100})$ - 日常生活中 這樣的複雜度很少出現
很好的封閉性：多項式＋多項式= 多項式

e.g. 判斷是不是質數 - [[A.K.S test]]

---
### 難度比較
$$A \subseteq B$$
專有名詞：**[[reducible]]** 可歸約
說明：Ａ的難度不會難於Ｂ的難度（Ａ的難度可能小於或等於Ｂ的難度）

e.g. 對陣矩陣乘法 v.s. 任意矩陣乘法

$$SymM \subseteq AbrM$$
能解決任意矩陣乘法的程序 一定可以解決對稱矩陣, 
反之不行

e.g. 一元一次 v.s. 一元二次
何者較難？一元二次

假設有兩演算法Ａ，Ｂ
如果$A \subseteq B$ 且不知道Ａ的解法，就可以先將它轉成Ｂ的input，經過Ｂ的運算後，在從Ｂ的輸出轉換成Ａ的輸出，當然所有過程都在多項式時間內完成

---
### NP
> def:decision problem that can be verified in Polynomial time
- 為什麼是決策問題
	在所有問題中，決策問題是比較簡單的，只需要回答yes/no就好
	但如果是要回答最大值或者最小值之類的問題，問題難度就會很大
	並且所有的問題都能轉換成決策問題，例如：如果要回答最小值，可以問說是否最小值在1~10之內，以此類推

	因此才會選用決策問題

- 為什麼要驗證並選用多項式時間
	如果光驗證這個問題的解都很難了，就更不用說要解決此問題了

1971 Cook P = NP?

---
### NP-complete
如果Ａ是NP-complete
那麼必須符合兩種狀態
1. A在NP的集合裡面
2. A是所有NP集合裡面難度最高的
![[Pasted image 20230825142449.png]]

因此只要解決NP-complete就能解決所有的NP問題

### [[SAT]]
intro: Cook's Theorem, SAT $\in$ NPC
SAT是一個問題的縮寫, 如果存在一個多項式時間的解法的話, SAT$\in$ P
那麼所有NP就有解答($P=NP$)

Karp 提出21NPC 問題=>證明一個問題比SAT難

已知 上千個

全稱The satisfiability Problem
給定一組布林函數,求函數是否為真
e.g. 
$$X \land (Y \ \lor \bar{Z})\rightarrow X \land Z$$
假設給定所有X Y Z 的結果那麼請問這組代數是否成立, 而且如果把代數擴展到10000多得話, 難度就會上升

---
### Reference
-[youtube-1](https://youtu.be/YmjBElBiEzI?si=UugNORgMAnQKGa_t)

