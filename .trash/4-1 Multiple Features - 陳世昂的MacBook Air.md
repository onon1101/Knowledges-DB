![[Pasted image 20230825221630.png]]
以上為單維度。h 函數是$h_{\theta}(x)=\theta_{0}+\theta_{1}x$

之前討論的都是單維度，也就是單個參數的預測學習，下面開始討論多維度的深度學習
![[Pasted image 20230827203021.png]]
以上為多維度。其中一個例子就是增加更多的特徵(參數)

每一筆資料都是一個向量(vector)，例如說：第二筆資料就可以寫做成$$x^{(2)}=\\
\begin{bmatrix}
1416\\
3\\
2\\
40
\end{bmatrix}$$
而每一個維度的資料稱為特徵，例如Number of bedrooms就寫作$$x_{2}=\\
\begin{bmatrix}
5\\
3\\
3\\
2
\end{bmatrix}$$

多特徵的ｈ函數為$h_{\theta}(x)=\theta_{0}+\theta_{1}x_1+\theta_{2}x_2+\theta_{3}x_3+......\theta_{n}x_n$
也可以轉為矩陣表達：$$h_\theta(x)=\theta^TＸ$$
Ｘ：代表的是特徵的矩陣，不過這邊會在多一個行列式$1$，因為如果變成$$h_\theta(x)=\theta^TＸ+\theta_0$$會很難看，所幸將後面的參數$\theta_0 \times 1$，就可以塞到矩陣了
此時矩陣大小會是$\theta^TX=m*(n+1)$。m代表樣本數量。n代表特徵數量
