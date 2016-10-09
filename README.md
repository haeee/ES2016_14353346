# DOL配置
14353346	 许瑶婷
***
## 安装一些必要的环境
>$	sudo apt-get update  
$	sudo apt-get install ant  
$ 	sudo apt-get install openjdk-8-jdk  
$	sudo apt-get install unzip
***
## 解压文件
1. 将dolethz.zip和systemc-2.3.1.tgz放到ubuntu里
+ 新建dol的文件夹  
$	mkdir dol  

+ 将dolethz.zip解压到 dol文件夹中  
$	unzip dol_ethz.zip -d dol  

+ 解压systemc  
$	tar -zxvf systemc-2.3.1.tgz  
***
## 编译systemc
1. 解压后进入systemc-2.3.1的目录下  
$	cd systemc-2.3.1  

+ 新建一个临时文件夹objdir  
$	mkdir objdir  

+ 进入该文件夹objdir  
$	cd objdir  

+ 运行configure(能根据系统的环境设置一下参数，用于编译)  
$	../configure CXX=g++ --disable-async-updates  
成功运行configure后如图：
![](http://i1.piimg.com/567571/252234e749dab93b.jpg)

+ 编译   
$	sudo make install  
编译完后文件目录如下  ($ cd ..  返回上级目录 ；$ ls 查看目录清单)：
![](http://p1.bpimg.com/567571/acaf958257d98bbf.jpg)  

+ 记录当前的工作路径(会输出当前所在路径，记下来，待会有用)   
$	pwd  
![](http://p1.bpimg.com/567571/53189c8a23298ffa.jpg) 当前的工作路径为 /home/yt/systemc-2.3.1 
***


## 编译dol  
1. 进入刚刚dol的文件夹，修改build_zip.xml文件，open with gedit  
找到下面这段话，就是说上面编译的systemc位置在哪里  
`<property name="systemc.inc" value="YYY/include"/>`  
`<property name="systemc.lib" value="YYY/lib-linux/libsystemc.a"/>`  
把YYY改成pwd的结果（注意，对于 64位 系统的机器，lib-linux要改成lib-linux64)，即改为：  
`<property name="systemc.inc"   value="/home/yt/systemc-2.3.1/include"/>`  
 `<property name="systemc.lib"   value="/home/yt/systemc-2.3.1/lib-linux64/libsystemc.a"/>`  

+ 然后是编译  
$	ant -f build_zip.xml all  
若成功会显示build successful，如图：  
![](http://i1.piimg.com/567571/c9c0ca74c5beb87b.jpg)

+ 试运行第一个例子  
$	cd build/bin/main  
$	ant -f runexample.xml -Dnumber=1  
**注意，**dol/build/bin/main下的runexample.xml 215-217行需要先注释掉，即将  
`<tstamp>  
      <format property="touch.time"
              pattern="MM/dd/yyyy hh:mm aa"
              offset="-5" unit="second"/>
    </tstamp>`  
    `<touch datetime="${touch.time}">
      <fileset dir="example${number}"/>`  
修改为：  
`<!--     <tstamp>
      <format property="touch.time"
              pattern="MM/dd/yyyy hh:mm aa"
              offset="-5" unit="second"/>
    </tstamp>`  
   ` <touch datetime="${touch.time}">
      <fileset dir="example${number}"/>
    </touch> -->`  
成功结果如图：  
![](http://i1.piimg.com/567571/72699ade9d285f62.jpg)