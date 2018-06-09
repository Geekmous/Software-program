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
