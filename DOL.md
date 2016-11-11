# DOL实例分析
14353346	 许瑶婷
***
##  TASK1：修改example2，让3个square模块变成2个
+  步骤：  
在example2.xml里，将
`<variable value="3" name="N"/>`修改为`<variable value="3" name="N"/>` ，如图：  
![](http://yotuku.cn/link?url=4keorghAgG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)  
这样，在迭代的时候，只会定义两个square进程模块：  
&emsp;&emsp;![](http://yotuku.cn/link?url=V1A1Z20lG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)  
也只会定义两个通道：  
&emsp;&emsp;![](http://yotuku.cn/link?url=VyFGZnAez&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   

+ 结果：  
1.生成的dot图：  
![](http://yotuku.cn/link?url=4kIkGnCgG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   
2.example2运行结果，只执行了两次square：   
![](http://yotuku.cn/link?url=VkYaz3Cxz&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)



##  TASK2：修改example1，使其输出3次方数
+  步骤：  
在square.c里，将
`i = i*i>`修改为`i = i*i*i` ，如图：  
![](http://yotuku.cn/link?url=Eyr7H2Agf&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)  
在example1.xml里，将关于square的命名都修改为**cubic**，如下图1-3：   
图1：![](http://yotuku.cn/link?url=4JLhB30gz&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   
图2：![](http://yotuku.cn/link?url=EyeCB30eG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   
图3：![](http://yotuku.cn/link?url=E1MJU2RlG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)

+ 结果：  
1.生成的dot图：  
![](http://yotuku.cn/link?url=VkFqVhAxz&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)    
2.example1运行结果，输入了三次方数：   
![](http://yotuku.cn/link?url=Ekmp4nRlM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   


##  实验总结
+ 本次实验修改代码的部分并不多，主要是要理解模块的定义、通道的定义和各模块如何连接。
+ 每重新编译一次`$ ant -f build_zip.xml all`，dol/build/bin/main下的**runexample.xml** 会重新生成，故215-217行需要再一次注释掉。（不过不需要重新编译，可以直接跑例子   
+ 修改代码，在dol/examples/exampleXX下进行  
+ 编译`ant -f build_zip.xml all`，在 dol目录下进行：  
![](http://yotuku.cn/link?url=EkIAD3AeG&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   
+ 编译例子，在dol/build/bin/main下进行：  
![](http://yotuku.cn/link?url=Vk7rd3AlM&tk_plan=free&tk_storage=tietuku&tk_vuid=19634417-c10e-44e8-bbcb-cbf6b232579c&tk_time=2016111121)   


