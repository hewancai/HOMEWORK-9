## NetworkDistribution_Homework9     

#### P3：  
      
步骤  | N'  | D(z), p(z) | D(y), p(y) |D(v), p(v)| D(w), p(w)|D(t), p(t)|D(u), p(u)
---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- 
0 | x | 8,x | 6,x |  3,x |  6,x |  ∞ |  ∞  
1 | xv | 8,x | 6,x |    |  6,x |  7,v |  6,v 
2 | xvy | 8,x |  |  |  6,x |  7,v |  6,v 
3 | xvyw | 8,x |   |    |    |  7,v |  6,v 
4 | xvywu | 8,x |   |    |    |7,v |   
5 | xvywut | 8,x |   |    |    |    |    
6 | xvywutz |  |   |    |   |    |        
        
	 
#### P5：
	初始时，节点Z的路由选择表：    
    
null  | u | v | x | y | z 
---- | ---- | ---- | ---- | ---- | ---- 
v | ∞ | ∞ | ∞ | ∞ | ∞  	
x | ∞ | ∞ | ∞ | ∞ | ∞  	
y | ∞ | 6 | 2 | ∞ | 0
     
	第一次迭代后：  
    
null | u | v | x | y | z 
---- | ---- | ---- | ---- | ---- | ---- 
v | ∞ | ∞ | ∞ | ∞ | ∞  	
x | ∞ | ∞ | ∞ | ∞ | ∞  	
y | ∞ | 6 | 2 | ∞ | 0    
     
	第二次迭代后：  
    
   | u | v | x | y | z 
---- | ---- | ---- | ---- | ---- | ---- 
v | 1 | 0 | 3 | 3 | 5  	
x | 4 | 3 | 0 | 3 | 2  	
y | 6 | 5 | 2 | 5 | 0 
     
	第三次迭代后：
   
null  | u | v | x | y | z 
---- | ---- | ---- | ---- | ---- | ---- 
v | 1 | 0 | 3 | 3 | 5  	
x | 4 | 3 | 0 | 3 | 2  	
y | 6 | 5 | 2 | 5 | 0  	

    
    
#### P9：   
	不会。
	链路开销的降低并不会导致循环的产生。
	若原本没有链路的两个节点被连接，则链路开销从无穷大降低为有限大。
	

****
#### author：2017302580217_董娜