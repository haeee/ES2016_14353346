# DOL实例分析
14353346	 许瑶婷
***
##  产生死锁的四个必要条件
+  **互斥条件**  
一个资源每次只能被一个进程使用

+ **占有并等待条件**   
一个进程因请求资源而阻塞时，对已获得的资源保持不放

+ **非抢占条件**  
进程已获得的资源，在末使用完之前，不能强行剥夺

+  **循环等待条件**  
若干进程之间形成一种头尾相接的循环等待资源关系
>这四个条件是死锁的必要条件，只要系统发生死锁，这些条件必然成立，而只要上述条件之一不满足，就不会发生死锁。


## 死锁发生的截图  
+ 为了证明死锁发生是随机的，截了同一代码下（count=10000）的两次死锁：  
第一次：  
&emsp;![](http://yotuku.cn/link?url=NyaqfpRgM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111122)  
第二次：  
&emsp;![](http://yotuku.cn/link?url=N1ENXTClG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111122)  


## 产生死锁分析
### 当一个线程访问object的一个synchronized(this)同步代码块时，其他线程对object中所有其它synchronized(this)同步代码块的访问将被阻塞。  
+ 当main函数里生成一个Deadlock的时候，会**调用其构造函数里的a.methodA(b)**，也会**运行run()函数里的b.methodB(a)**：  
![](http://yotuku.cn/link?url=EJNZKTAxz&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111122)  

+ 执行a.methodA(b)时，加了关键字synchronized的a.last()被阻塞；  
  又由于a.methodA(b)里调用了b.last()函数，加了关键字synchronized的b.method()也被阻塞。  
  执行b.methodB(a)也是如此：  
  ![](http://yotuku.cn/link?url=VJ4EjTAef&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111122)  
  
+ 若a.methodA(b)先于b.methodB(a)执行完毕，则先打印`Inside B.last()`。需要把count调大，使a.methodA(b)不要那么快执行，才能产生死锁。如图（count=2000）：  
  ![](http://yotuku.cn/link?url=4JXF260lM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)  
  
+ 反之，若b.methodB(a)先于a.methodA(b)执行完毕，则先打印`Inside A.last()`。需要把count调小，使a.methodA(b)快点执行，才能产生死锁。如图（count=20000）：  
![](http://yotuku.cn/link?url=VJDR3aClG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111123)   

+ 当a.methodA(b)和b.methodB(a)执行的时间很接近时，即一个没有执行完毕，另一个就开始执行，就会产生死锁。  
> **以此为例**  
> 执行a.methodA(b)
> a.last()被阻塞
> 调用b.last()函数
> b.method()被阻塞
> 执行b.methodB(a)，发现其被阻塞，程序无法继续执行，产生死锁