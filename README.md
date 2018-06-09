# Software-program
两步移动搜索法  
输入：服务设施数据<a href="https://www.codecogs.com/eqnedit.php?latex=$\{S_1,&space;S_2,&space;S_3...,&space;S_n&space;\}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\{S_1,&space;S_2,&space;S_3...,&space;S_n&space;\}$" title="$\{S_1, S_2, S_3..., S_n \}$" /></a>（如服务设施的服务能力值）和居名点数据<a href="https://www.codecogs.com/eqnedit.php?latex=$\{C_1,&space;C_2,&space;C_3...,&space;C_n&space;\}$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$\{C_1,&space;C_2,&space;C_3...,&space;C_n&space;\}$" title="$\{C_1, C_2, C_3..., C_n \}$" /></a>(如居民人数)  
输出：居民点的可达性
计算方法：  
（1）给定一个空间距离阈值d_0，对于每一个服务设施计算服务设施的供需比：  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$R_i&space;=&space;\frac{S_i}{&space;\sum_{k&space;=&space;\{&space;d_k&space;<&space;d_0&space;\}}&space;C_k&space;}&space;$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$R_i&space;=&space;\frac{S_i}{&space;\sum_{k&space;=&space;\{&space;d_k&space;<&space;d_0&space;\}}&space;C_k&space;}&space;$$" title="$$R_i = \frac{S_i}{ \sum_{k = \{ d_k < d_0 \}} C_k } $$" /></a>  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$R_i&space;$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$R_i&space;$$" title="$$R_i $$" /></a>为服务设施点i的供需比  

<a href="https://www.codecogs.com/eqnedit.php?latex=$$d_k$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$d_k$$" title="$$d_k$$" /></a>为服务设施点i与居民点k之间的欧氏距离  

（2）在给定空间距离阈值d_0，对于每一个居民点，计算服务设施相应的可达性：  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$A_j&space;=&space;\sum_{k&space;=&space;\{&space;d_k&space;<&space;d_0&space;\}}&space;R_k&space;$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$A_j&space;=&space;\sum_{k&space;=&space;\{&space;d_k&space;<&space;d_0&space;\}}&space;R_k&space;$$" title="$$A_j = \sum_{k = \{ d_k < d_0 \}} R_k $$" /></a>  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$A_j$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$A_j$$" title="$$A_j$$" /></a>为居民点j的可达性值。  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$d_k$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$d_k$$" title="$$d_k$$" /></a>为居民点j到服务设施点k的欧式距离.  


点要素核密度估计  
输入：点要素类(至少含有x，y坐标，和需要估计的population数值)  
输出：该点要素的核密度估计栅格数据。
计算方法：点要素类中的点集为<a href="https://www.codecogs.com/eqnedit.php?latex=$$\{X_1,&space;X_2,&space;......,&space;X_n\}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$\{X_1,&space;X_2,&space;......,&space;X_n\}$$" title="$$\{X_1, X_2, ......, X_n\}$$" /></a>(坐标向量)，值集为<a href="https://www.codecogs.com/eqnedit.php?latex=$$\{P_1,&space;P_2,&space;......,&space;P_n\}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$\{P_1,&space;P_2,&space;......,&space;P_n\}$$" title="$$\{P_1, P_2, ......, P_n\}$$" /></a>.  
核密度估计函数为:  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$f(x)&space;=&space;\frac{1}{nh^d}\sum_{i&space;=&space;1}^n&space;(P_i&space;*&space;K(\frac{x&space;-&space;X_i}{h}))$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$f(x)&space;=&space;\frac{1}{nh^d}\sum_{i&space;=&space;1}^n&space;(P_i&space;*&space;K(\frac{x&space;-&space;X_i}{h}))$$" title="$$f(x) = \frac{1}{nh^d}\sum_{i = 1}^n (P_i * K(\frac{x - X_i}{h}))$$" /></a>  
其中h为带宽，d为x向量的维数.K(x)为核函数。<a href="https://www.codecogs.com/eqnedit.php?latex=$$P_i$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$P_i$$" title="$$P_i$$" /></a>为第i个点的population值  
该处使用的核函数为：  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$&space;K(x)&space;=&space;\left\{&space;\begin{array}{lr}&space;3\pi(1&space;-&space;x^Tx)^2,&space;&&space;x^Tx&space;<&space;1&space;\\&space;0,&space;&&space;otherwise.\\&space;\end{array}&space;\right.&space;$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$&space;K(x)&space;=&space;\left\{&space;\begin{array}{lr}&space;3\pi(1&space;-&space;x^Tx)^2,&space;&&space;x^Tx&space;<&space;1&space;\\&space;0,&space;&&space;otherwise.\\&space;\end{array}&space;\right.&space;$$" title="$$ K(x) = \left\{ \begin{array}{lr} 3\pi(1 - x^Tx)^2, & x^Tx < 1 \\ 0, & otherwise.\\ \end{array} \right. $$" /></a>   
带宽的计算如下：  
默认带宽算法（ArcGIS中的描述）  
输入：坐标向量点集<a href="https://www.codecogs.com/eqnedit.php?latex=$$\{X_1,&space;X_2,&space;\ldots,&space;X_n\}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$\{X_1,&space;X_2,&space;\ldots,&space;X_n\}$$" title="$$\{X_1, X_2, \ldots, X_n\}$$" /></a>(注意为向量表示，下同)    
输出：带宽h  
计算方法：  
计算点集的平均中心  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$\overline&space;X&space;=&space;\frac{1}{n}\sum_{i&space;=&space;1}^nX_i$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$\overline&space;X&space;=&space;\frac{1}{n}\sum_{i&space;=&space;1}^nX_i$$" title="$$\overline X = \frac{1}{n}\sum_{i = 1}^nX_i$$" /></a>  
计算与所有点的平均中心之间的距离。  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$D_i&space;=&space;\sqrt{(X_i&space;-&space;\overline&space;X)^T(X_i&space;-&space;\overline&space;X)}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$D_i&space;=&space;\sqrt{(X_i&space;-&space;\overline&space;X)^T(X_i&space;-&space;\overline&space;X)}$$" title="$$D_i = \sqrt{(X_i - \overline X)^T(X_i - \overline X)}$$" /></a>   
计算这些距离的中值<a href="https://www.codecogs.com/eqnedit.php?latex=$$D_m$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$D_m$$" title="$$D_m$$" /></a>  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$D_m&space;=&space;Mid(D_i)$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$D_m&space;=&space;Mid(D_i)$$" title="$$D_m = Mid(D_i)$$" /></a>
计算标准距离SD。  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$SD&space;=&space;\sqrt{&space;\frac{1}{n}&space;\sum_{i&space;=&space;1}^n&space;(X_i&space;-&space;\overline&space;X)^T(X_i&space;-&space;\overline&space;X)}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$SD&space;=&space;\sqrt{&space;\frac{1}{n}&space;\sum_{i&space;=&space;1}^n&space;(X_i&space;-&space;\overline&space;X)^T(X_i&space;-&space;\overline&space;X)}$$" title="$$SD = \sqrt{ \frac{1}{n} \sum_{i = 1}^n (X_i - \overline X)^T(X_i - \overline X)}$$" /></a>   
使用以下公式计算带宽  
<a href="https://www.codecogs.com/eqnedit.php?latex=$$h&space;=&space;0.9&space;*&space;min(SD,&space;\sqrt{\frac{1}{ln(2)}})&space;*&space;n^{-0.2}$$" target="_blank"><img src="https://latex.codecogs.com/gif.latex?$$h&space;=&space;0.9&space;*&space;min(SD,&space;\sqrt{\frac{1}{ln(2)}})&space;*&space;n^{-0.2}$$" title="$$h = 0.9 * min(SD, \sqrt{\frac{1}{ln(2)}}) * n^{-0.2}$$" /></a>  

