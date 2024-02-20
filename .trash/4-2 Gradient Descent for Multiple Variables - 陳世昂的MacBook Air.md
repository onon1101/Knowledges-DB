多特徵的函數：$h_{\theta}(x)=\theta_{0}+\theta_{1}x_1+\theta_{2}x_2+\theta_{3}x_3+......\theta_{n}x_n$

Cost function：$J(\theta_1,\theta_2,...\theta_n)=\frac{1}{2m}\sum_{i=1}^{m}(h_{\theta}(x^i) - y^i)^2$

---

對於每一個特徵都要做梯度下降，不過要注意的是在每一次做完後不要立即變更參數，不然會導致下個參數更新時跑掉。直到所有特徵都變更完畢後才能**更新**

每個參數的更新方法：$$\theta_j:=\theta_j-a\frac{1}{m}\sum_{i=1}^{m}((h_{\theta}(x^{(i)}) - y^{(i)})^2\times x_j^{(i)})$$
- a為超參數：學習率