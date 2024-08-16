## 1.目录结构

Linux区分大小写，建议使用小写字符来创建文件或目录

Linux文件扩展名对Linux系统没有特殊含义，Linux系统并不以文件扩展名划分文件类型(rc.exe只是一个文件，其扩展名.exe并不代表此文件就一定是可执行的)

Linux没有盘符的概念，顶级目录只有一个根目录 / ,所有文件都在它下面

路径选择之间用 / 表示。开头的 / 表示根目录，后面 / 表示层级

ls / 获取根目录下文件

![image-20240226170738554](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240226170738554.png)

![image-20240227210739737](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227210739737.png)

## 2.命令入门

command   -options     parameter

command ：命令本身

-options ： [可选，非必须] 命令的一些选项，可通过选项控制命令行为细节

parameter ：[可选，非必须]命令的参数，多数用于命令的指向目标



### ls命令

ls命令作用是列出目录下的内容，语法细节如下：

ls    [-a -l -h]    [Linux路径]

 [-a -l -h]是可选项

 [Linux路径] 

![image-20240503152356793](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240503152356793.png)

1.ls命令作用是？

在命令行中，以平铺的形式，展示当前工作目录(默认HOME目录)下的内容(文件或文件夹)

2.HOME目录是？

每一个用户在Linux系统的专属目录，默认在：/home/用户名

3.当前工作目录？

Linux命令在执行命令的时候，需要一个工作目录，打开命令行程序(终端)默认设置工作目录在用户的HOME目录

![image-20240503152818493](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240503152818493.png)

ls命令参数和选项

ls    [-a -l -h]    [Linux路径]

[-a -l -h] 

**-a选项，表示：all的意思，即列出全部文件(包含隐藏文件/文件夹)**

图中以 .开头的，表示Linux系统的隐藏文件/文件夹(只要是以 .开头就能自动隐藏)

只有通过-a选项，才能看到隐藏文件/文件夹

![image-20240503152934849](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240503152934849.png)

**-l 选项，以列表形式展示内容，并展示更多信息**

-l 选项其实和图形化中，文件夹以列表形式排列是一个意思

![image-20240503153012839](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240503153012839.png)

-l 和 -a可以组合使用

写法： ls -l -a	ls -la	ls -al

![image-20240226164354890](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240226164354890.png)

ls -al   以列表形式展示根目录隐藏文件

**-h 表示以易于阅读形式，列出文件大小，如K，M，G ；-h 选项必须要搭配 -l 一起使用**

![image-20240226171745337](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240226171745337.png)

```
ls命令参数的作用

可以指定要查看的文件夹(目录)内容，如果不给定参数，就查看当前工作目录内容

ls命令的选项：

​	-a 选项，可以展示出隐藏内容(以 . 开头的文件或文件夹默认被隐藏，需要 -a 才能显示)

​	-l 选项，以列表形式展示内容，并展示更多细节

​	-h 选项，需要和 -l 选项搭配使用，以更加人性化的方式显示文件大小单位
```

命令选项组合使用

命令选项是可以组合的，比如： ls -alh  等同于 ls -a -l -h

### cd切换工作目录命令

当Linux终端(命令行)打开时，会默认以用户的HOME目录作为当前工作目录

我们可以通过cd命令，更改当前所在的工作目录

语法：cd [Linux路径]

​	cd命令无需选项，只有参数，表示要切换到那个目录下

​	cd命令直接执行，不写参数，表示回到用户HOME目录

![image-20240226173602721](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240226173602721.png)

### pwd查看当前工作目录命令

通过ls验证当前工作目录不恰当

一般通过pwd命令，来查看当前工作目录

语法：pwd

​	pwd命令，无选项，无参数，直接输入pwd即可

![image-20240226173809064](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240226173809064.png)

```
cd命令作用

​	cd命令切换当前工作目录    cd [liunx路径]

​		没有选项，只有参数，表示目标路径

​		使用参数，切换到指定路径

​		不使用参数，切换工作目录到当前用户的HOME

pwd命令

​	pwd命令，没有选项，没有参数，直接使用

​	作用是：输出当前所在的工作目录
```



### 相对路径绝对路径和特殊路径符

​	**绝对路径**：以根目录为起点，路径描述以 / 开头

​	cd /home/rong2024/Desktop

![image-20240227151213921](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227151213921.png)

​	**相对路径**：以当前目录为起点，路径描述无需以 / 开头

​	cd Desktop

![image-20240227151335087](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227151335087.png)

​	**特殊路径符**：

​		.	表示当前目录，比如cd  ./ Desktop表示切换到当前目录下的Desktop目录内，和cd Desktop效果相同

![image-20240227153226005](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227153226005.png)

​		..	表示上一级目录，比如cd  .. 即可切换到上一级目录， cd  ../..  切换到上二级目录

![image-20240227153642430](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227153642430.png)

​		~	表示HOME目录，比如cd  ~ 即可切换到HOME目录cd ~/Desktop   切换到HOME内Desktop目录

![image-20240227153720843](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227153720843.png)

```
相对路径和绝对路径

​	绝对路径：以根目录做起点，描述路径方式，路径以 / 开头

​	相对路径：以当前目录作为起点，描述路径方式，路径不需以 / 开头

特殊路径符号

​	. 表示当前目录，比如cd  或 cd ./Desktop

​	.. 表示上一级目录，比如cd ..  或 cd ../..

​	~表示用户HOME目录，比如cd~ 或 cd ~/Desktop
```



### 创建目录命令(mkdir)

**mkdir命令**通过mkdir命令可以创建新的目录(文件夹)，创建文件夹

语法：mkdir [-p] linux路径

​	参数必填，即要创建的文件夹的路径

​	-p 可选项，表示自动创建不存在的父目录，适用于创建连续多层级的目录



当前目录下创建以相对路径test01

![image-20240227161926221](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227161926221.png)

 绝对路径下创建test02

![image-20240311203608084](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240311203608084.png)

返回上级目录创建test03

![image-20240311204208443](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240311204208443.png)

**-p 一次性创建多个不存在的层级目录**

创建多个层级时，没有  mkdir -p 就会无法创建

![image-20240311205022788](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240311205022788.png)

```
mkdir命令的语法和功能

​	mkdir用以创建新的目录(文件夹)

​	语法：mkdir [-p] Linux路径

​	参数必填,表示要创建的目录路径(相对，绝对，特殊路径符)

-p选项作用

​	可选，表示自动创建不存在的父目录，适用于创建连续多层级的目录
```



### 文件操作命令(touch   cat   more)

#### 	1.     **touch创建文件**

​	语法：touch linux路径

​		touch命令无选项，参数必填，表示要创建文件路径(相对，绝对，特殊)，创建文件

![image-20240227165015865](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227165015865.png)

列表查看时，d开头是文件夹，-开头是文件

#### 	2.    cat命令查看文件内容

​		语法：cat liunx路径

​		cat同样没有选项，只有必填参数，参数表示：被查看的路径(相对，绝对，特殊)

![image-20240227165758994](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227165758994.png)

#### 	3.    more命令查看文件内容可翻页

​	more命令同样可以查看文件内容，同cat不同的是：

​		cat是直接将文件内容全部显示出来

​		more支持翻页，如果文件内容过多，可以一页页展示

​	语法： more linux路径

​	同样没有选项，只有必填参数，参数表示：被查看的文件路径(相对，绝对，特殊)

查看liunx系统内置文件 路径为：/etc/services 可以使用more命令查看

**在查看过程中，空格是翻页 ，q 是退出**

![image-20240227171035624](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227171035624.png)

```
touch命令
​	用于创建一个新的文件

​	语法： touch   linux路径

​	参数必填，表示要创建的文件路径(相对，绝对，特殊)

cat命令
​	用于查看文件内容

​	语法：cat    linux路径

​	参数必填，表示要创建的文件路径(相对，绝对，特殊)

more命令
​	用于查看文件内容，可翻页查看

​	语法：more linux路径

​	参数必填，表示要创建的文件路径(相对，绝对，特殊)，空格翻页，q退出
```



### 文件操作命令(cp  mv  rm)

#### **1.使用cp复制文件，文件夹**(备份文件)

​	cp命令用于复制文件和文件夹

语法： cp [-r] 参数1 参数2

​	-r 选项，可选，用于复制文件夹使用表示递归

​	参数1，linux路径，表示被复制的文件或文件夹

​	参数2，linux路径表示要去的地方

复制文件

![image-20240227191956073](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227191956073.png)

复制文件夹

![image-20240227192512607](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227192512607.png)

#### **2.使用mv移动文件，文件夹**

​	mv命令用于移动文件或文件夹

语法：mv  参数1(被移到)  参数2(移动去的地方)

​	参数1，linux路径，表示被移动的文件或文件夹

​	参数2，linux路径，表示要移动去的地方，如果目标不在，则进行改名，确保目标存在(mv 可以用于创建新的文件或文件夹)



移动文件至文件夹中

![image-20240227193652172](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227193652172.png)

文件改名

![image-20240503154429755](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240503154429755.png)

文件夹移动至文件夹中

![image-20240227194254751](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227194254751.png)

#### **3.使用rm删除文件，文件夹**

​	rm命令用于删除文件，文件夹

语法：rm [ -r -f ]    参数1  参数2  ...... 参数N(支持无线数量参数)

-r 用于删除文件夹(同cp命令一样)

-f 表示force，强制删除(不会弹出提示确认信息)

​	普通用户删除内容不会弹出提示，只有root管理员用户删除内容会有提示

​	一般普通用户用不到 -f 选项

参数1，参数2， ......参数N表示要删除的文件或文件夹路径，按照空格隔开

删除文件

![image-20240227195659697](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227195659697.png)

删除文件夹

![image-20240227195733438](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227195733438.png)

#### rm删除文件或文件-通配符

```Linux
rm删除文件或文件-通配符
rm命令支持通配符 * ，用来做模糊匹配
  符号 * 表示通配符，即匹配任意内容(包含空)，示例：
   test* ，表示区配任何以test开头的内容
   *test ，表示匹配任何以test结尾的内容
   *test* 表示匹配任何包含test的内容
```

删除test开头的文件或文件夹

![image-20240227202742418](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227202742418.png)

删除txt结尾的文件或文件夹

![image-20240227203140581](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227203140581.png)

删除带test的文件或文件夹

![image-20240227203322241](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227203322241.png)

**-f 选项 强制删除**

可以通过 su - root ，并输入linux用户密码(和普通用户一样)临时切换到root用户

通过输入 exit 命令退回普通用户

​			普通删除要确认(y/n)   yes/no

![image-20240227204702824](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227204702824.png)

​			-f 强制删除不用确认

![image-20240227204922921](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227204922921.png)

![image-20240227205101372](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227205101372.png)

```
1. cp命令
   用于复制文件或文件夹
   语法：cp [-r] 参数1 参数2
   -r选项，可选，用于复制文件夹使用，表示递归
   参数1，Linux路径，表示被复制的文件或文件夹
   参数2，Linux路径，表示要复制去的地方
2. mv命令
   用于移动文件
   语法：mv 参数1 参数2
   参数1，Liunx路径，表示被移动的文件或文件夹
   参数2，Liunx路径，表示要移动去的地方(如果目标不存在，则进行改名。创建一个新文件或文件夹)
3. rm命令
   用于删除文件或文件夹
   语法：rm [-r -f] 参数1 参数2 ......参数N
   -r 选项，可选，文件夹删除
   -f 选项，可选，用于强制删除(不提示，一般用于root用户)
   参数，表示被删除的文件或文件夹路径，支持多个，空格隔开
   参数也支持通配符* ，用以做模糊匹配
```

### 查找命令(which，find)

#### **1.  which命令查找命令的程序文件**

which命令Linux命令本体就是一个个的二进制可执行程序，和Windows系统中的 .exe文件一个意思

通过which命令可以查看一些列命令的程序文件放在哪里

语法：which 要查找的命令

![image-20240227215046575](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227215046575.png)

#### **2.  find命令查找指定文件(按文件名查找)**

find在 su - root 用户中完成

在Linux系统中，通过find命令去搜索指定的文件

语法：find     起始路径    -name   "被查找的文件名"

![image-20240227220509454](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227220509454.png)

find命令-通配符

根据语法：find   起始路径   -name ”被查找文件名“

被查找文件名，支持使用通配符 * 来做模糊查询

​	符号 * 表示通配符，即匹配任意内容(包含空)，示例：

​	test* ，表示匹配任何以test开头的内容

![image-20240227221315229](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227221315229.png)

​	*test  ，表示匹配任何以test结尾的内容

![image-20240227221443737](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227221443737.png)

​	*test * ，表示匹配任何包含test的内容

![image-20240227222121699](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227222121699.png)

#### **3.  find命令查找指定文件(按文件大小查找)**

语法：find   起始路径    -size    + - n [KMG]

 + +，-   表示大于和小于

 + n，表示大小数字

 + kMG表示大小单位，k(小写字母)表示kb，M表示MB，G表示GB

   示例：

   * 查找小于10kb的文件： find   /   -size   -10k

     ![image-20240227223827749](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227223827749.png)*

   * 查找大于100MB的文件：find   /   -size  +100M

     ![image-20240227224023430](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227224023430.png)*

     通过 ls -lh 查看文件大小

     ![image-20240227224304524](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227224304524.png)*

   * 查找大于1GB的文件：find   /   -size   +1G

     ![image-20240227224445999](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240227224445999.png)*
   
     

```
1.which命令

查找命令的程序文件位置

语法：which 要查找的命令

无需选项，只需要参数表示查找哪个命令

2，find命令

用于查找指定的文件

按文件名查找(支持通配符)：find / -name "被查找的文件名" 

按文件大小查找(n表示大小数字，kMG表示kB，MB，GB)：find / -size +-n[kMG]
```



#### **4. grep命令过滤文件或文件内容**

通过grep命令，从文件中通过关键字过滤文件行

语法：grep  [-n]   关键字   文件路径

​	选项 -n，可选，表示在结果中显示匹配行的行号

​	参数，关键字，必填，表示过滤的关键字，带有空格或其他特殊符号，建议使用 "     "  包裹

​	参数，文件路径，必填，表示要过滤内容的文件路径，可作为内容输入端口

![image-20240228142036171](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228142036171.png)

​	-n 显示匹配行数

![image-20240228142340550](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228142340550.png)

#### **5. wc命令统计内容数量**

通过wc命令统计文件行数，单词数量

语法： wc [-c  -m  -l  -w]   文件路径

​	wc 文件路径：     行数     单词数量     字节数     文件名

![image-20240228152822446](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228152822446.png)

​	-c 选项，统计bytes数量

![image-20240228152951072](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228152951072.png)

​	-m 选项，统计字符数量

![image-20240228153015024](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228153015024.png)

​	-l 选项，统计行数

![image-20240228153027743](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228153027743.png)

​	-w 选项，统计单词数量

![image-20240228153045667](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228153045667.png)

参数，文件路径，被统计的文件，可作为内容输入端口

#### **6.    |  管道符的概念和应用**

管道符的含义：将管道符左边命令的结果作为右边命令的输入

![40d0d9a351ef3b85bca0309b28d4837a](D:\qq_new\qqxiaoxi_new\Tencent Files\2725265334\nt_qq\nt_data\Pic\2024-02\Ori\40d0d9a351ef3b85bca0309b28d4837a.png)

 使用管道符查看test.txt文件的行数

![image-20240228160101344](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228160101344.png)

使用管道符过滤home中的test文件

![image-20240228160544909](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228160544909.png)

![image-20240228160718245](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228160718245.png)

使用管道符查看/usr/bin中文件数

![image-20240228161013692](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228161013692.png)

管道符的嵌套

![image-20240228161515419](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228161515419.png)

```
1.grep命令
从文件中通过关键字过滤文件行
语法：grep [-n] 关键字 文件路径
选项-n，可选，表示在结果中显示匹配行的行号
参数：关键字，必填，表示过滤的关键字，建议使用" "包裹关键字
2.wc命令
统计：文件行数-l ，单词数量-w ，字节数-c ，字符数 -m，
不带选项默认统计：行数 单词数量 字节数 文件名
3.管道符 |
左边的结果作为右边的输入
```

1.统计文件中带有itcast关键字有几行

2.统计文件中带有itheima关键字的结果中有多少个单词

![image-20240228162616497](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228162616497.png)

#### **7. echo命令输出指定内容,**反引号 ’,重定向符

使用echo命令在命令行内输出指定内容

语法：echo  输出的内容

无需选项，只有一个参数，表示要输出的内容，复杂内容建议用 "      " 包裹

![image-20240228204917328](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228204917328.png)

**反引号 ’**

**被反引号包围的内容，会被作为命令执行，而非普通字符**

![image-20240228210557883](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228210557883.png)

**重定向符**

重定向符：> 和 >>

​	>，将左侧命令的结果，覆盖写入到符号右侧指定的文件中

​	>>, 将左侧命令的结果，追加写入到符号右侧指定的文件中



覆盖写入(会把原本的内容清空，在写入新的内容)

​	>

![image-20240228211419564](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228211419564.png)

追加写入(在原本的内容后面追加)

​	>>

![image-20240228212628958](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228212628958.png)

重定向符其实就是  (左边产生的结果)  写入  (右边的文件)

只要是能产生结果的命令都能写入右边

![image-20240228213731975](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228213731975.png)

#### **8. tail命令查看文件尾部内容**

使用 tail 命令，可以查看文件尾部内容，跟踪文件的最新更改

语法：tail [ -f   -num ]  Linux路径

​	参数，Linux路径，表示被跟踪的文件路径

​	选项， -f，表示持续跟踪

​	选项，-num，表示，查看尾部多少行，不填默认10行

![image-20240228215042740](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228215042740.png)

查看文件末尾5行

![image-20240228215539701](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228215539701.png)

持续跟踪

执行 tail -f  test.txt   命令后，不会立刻结束，需要Ctrl+C手动结束

![image-20240228220036949](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228220036949.png)

```
1. echo命令
	可以使用echo命令在命令行内输入指定内容
语法：echo 输出的内容
	无需选项，只有一个参数，表示要输出的内容，复杂内容可以用" "包围
2. ·反引号符
	被·包围的内容，会被作为命令执行，而非普通字符
3.  重定向符
	>	将左侧命令结果，覆盖写入到符号右侧指定文件中
	>>	将左侧命令结果，追加写入到符号右侧指定文件中
4. tail命令
	查看文件尾部内容，并可以持续跟踪
    语法: tail [-f -num] Linux路径
    选项， -f，表示持续跟踪(运行命令 tail -f linux路径 后文件不会结束，需要Ctrl+C)
    选项，-num，表示，查看尾部多少行，不填默认10行
```

请使用echo·并配合反引号，输出内容：我当前的工作目录是：·具体的工作目录路径· 。并结合重定向符，将输出结果覆盖写入work.txt文件

![image-20240228222104063](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228222104063.png)

请使用echo输出任意内容并追加到work.txt文件中，通过tail命令持续跟踪文件内容更改

![image-20240228222612326](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240228222612326.png)

## 使用VI，VIM编辑器完成文件编辑工作

```
安装vim：yum -y install vim
```

![image-20240301201545762](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240301201545762.png)

​	**语法：vim 文件路径**

#### 1.命令模式

​	**按 i 进入输入模式；按 ：进入底线命令模式**

![image-20240301202722209](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240301202722209.png)

![image-20240301203657551](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240301203657551.png)

#### 2.输入模式

​	**按 esc 进入命令模式**，输入内容进行编辑，

#### 3.底线命令模式

![image-20240301205641516](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240301205641516.png)

# 3.linux用户和权限

在Linux系统中，拥有最大权限的账户名为：root(超级管理员)

su - root 进入管理员用户

exit 或者 ctrl + d  退出管理员用户

管理员用户切换普通用户 su - 普通用户名

![image-20240302145706179](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240302145706179.png)

**sudo命令**

使用sudo命令，为普通的命令授权，临时以root身份执行

语法：sudo 其他命令

​	在其它命令之前，带上sudo，即可为这一条命令临时赋予 root 授权

​	但并不是所有用户，都有权力使用sudo，需要为普通用户配置 sudo 认证

**为普通用户配置sudo认证**

1.切换到root用户

2.输入visudo ，执行visudo命令，会自动通过vi编辑器打开：/etc/sudoers

3.输入下面图片

![image-20240302152845582](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240302152845582.png)

4.wq保存

```
1.Linux系统的超级管理用户是：root用户
2.su命令
	可以切换用户，语法：su - 用户名
		- 表示切换后加载环境变量，
		用户可以省略，省略默认切换到root
3.sudo命令
	可以让一条普通用户命令带有root权限，语法：sudo 其它命令
	需要以root用户执行visudo命令，增加配置可让普通用户有sudo命令执行权限
```

#### 1. 用户，用户组的概念

Linux系统中可以：

​	配置多个用户

​	配置多个用户组

​	用户可以加入多个用户组

Linux中关于权限的管控级别有2个，分别是：

​	针对用户的权限控制

​	针对用户组的权限控制

比如，针对某文件，可以控制用户的权限，也可以控制用户组的权限

##### **用户组管理命令**

以下命令需root用户执行

```
	创建用户组	groupadd    用户组名

​	删除用户组	groupdel    用户组名
```

![image-20240303223335560](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240303223335560.png)

**创建用户**

```
useradd [-g -d] 用户名

​	选项： -g 指定用户的组，不指定 -g。会创建同名组并自动加入，指定 -g 需要组已经存在，如已存在同名组，必须使用 -g

​	选项：-d 指定用户home路径，不指定，home目录默认在：/home/用户名
```

![image-20240304232727720](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240304232727720.png)

![image-20240407205228245](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240407205228245.png)

![image-20240304232837241](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240304232837241.png)

**删除用户**

```
userdel [-r] 用户名

​	选项：-r，删除用户的home目录，不使用 -r，删除用户时，home目录保留
```

删除时要在root用户下才能成功

![image-20240407205555764](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240407205555764.png)

![image-20240304233413905](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240304233413905.png)

![image-20240304233424925](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240304233424925.png)

**查看用户组**

```
id[用户名]
​	参数：用户名，被查看的用户，如果不提供则查看自身

useradd test03 -g itcast 			创建test03用户并指定添加进itcast用户组
```

![image-20240407205957145](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240407205957145.png)

**修改用户所属组**

```
usermod -aG 用户组 用户名，将指定用户加入指定用户组

 useradd test04					创建了test04用户，并默认添加进入test04用户组
 usermod -aG itcast test04		把test04用户移动至itcast用户组中
```

![image-20240407210414452](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240407210414452.png)

##### getent命令：查看当前系统中有哪些用户

```
使用getent命令，可以查看当前系统中有哪些用户

语法： getent passwd

    共有7份信息，分别是：

    用户名：密码(x)：用户ID：组ID：描述信息(无用)：home目录：执行终端(默认bash)
```

![image-20240304234603700](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240304234603700.png)

```
使用getent命令，同样可以查看当前系统中有那些用户组

语法：getent group

包含3份信息，组名称：组认证(显示为x)：组ID
```



#### 2.认知权限信息(理论)

通过 ls -l 查看文件信息 

![image-20240307172505443](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240307172505443.png)

* 序号1，表示文件，文件夹的权限控制信息
* 序号2，表示文件，文件夹所属用户
* 序号3，表示文件，文件夹所属用户组

**权限信息**

序号1的权限细节

权限细节总共分为10个槽位

​	- 表示文件	d 表示文件夹	l 表示软连接

![image-20240307172729307](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240307172729307.png)

举例：drwxr-xr-x 表示：

* 这是一个文件夹，首字母d表示
* 所属用户权限是：有r有w有x，rwx
* 所属用户组权限是：有r无w有x，r-x( - 表示无此权限)
* 其他用户权限是：有r无w有x，r-x 

**rwx**

* r 可读权限
* w 可写权限
* x 可执行权限

针对文件，文件夹不同，rwx的含义有细微差别

* r，针对文件可以查看文件内容(文件夹，可以查看文件夹内容，如ls命令)
* w，针对文件可以修改此文件(文件夹，可以创建，删除，改名)
* x，针对文件可以将文件作为程序执行(文件夹，表示可以更改工作目录到此文件夹，即cd进入)

#### chmod命令

使用Chmod命令，修改文件，文件夹的权限信息(只有文件，文件夹的所属用户或root用户可以修改)

```
语法： chmod  [-R]  文件或文件夹

​	选项：-R ，对文件夹内的全部内容应用同样的操作
u :user用户权限
g :group用户组权限
o :other其他用户权限
```

```
将文件权限修改为: rwxr-x--x
chmod u=rwx,g=rx,o=x hello.txt
```

![image-20240408184500500](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408184500500.png)

```
chmod 带-R 修改的不只是文件夹权限，还有里面所有的文件或文件夹权限
chmod -R u=rwx,g=rx,o=x test
```

![image-20240408191043678](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408191043678.png)

权限可以通过三位二进制表示

![image-20240408191620845](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408191620845.png)

![image-20240408192205791](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408192205791.png)

```
1.chmod命令

​	功能，修改文件，文件夹的权限细节

​	限制，只能是文件，文件夹的所属用户或root 有权利修改

​	语法：chmod -R 权限 文件或文件夹

​	选项：-R，对文件夹内的全部内容应用同样规则

2.权限的数字序号

​	r代表4，w代表2，x代表1

​	rwx的互相组合可以得到从0到7的8种权限组合
```

#### chown命令

使用chown命令，可以修改文件，文件夹的所属用户和用户组(此命令只适用于root用户执行)

语法: chowm -R  [用户]  :  [用户组]  文件或文件夹

​	选项，-R 同chmod，对文件夹内全部内容应用相同规则

​	选项，用户，修改所属用户

​	选项，用户组，修改所属用户组

​	:   用于分隔用户和用户组  

**值得注意的是，即使在root模式下也无法执行chown命令，最大原因是不在/home/主文件夹下/**

![image-20240408200113159](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408200113159.png)

把test.txt的所属用户组切换为root

![image-20240408200516931](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408200516931.png)

把test.txt的所属用户和用户组修改为root

​									两种都可以

![image-20240408200853259](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408200853259.png)

修改文件夹test及以下的所有文件，文件夹的用户和用户组为rong2024

![image-20240408201357681](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408201357681.png)

```
chown命令

​	功能，修改文件，文件夹的所属用户，组

​	限制，只可root执行

​	语法：chown  [-R]  [用户]  [:] [用户组]  文件或文件夹

​	选项，-R，同chmod，对文件夹全部内容应用相同规则

​	选项，用户，修改所属用户

​	选项，用户组，修改所属用户组

​	:  用于分隔用户和用户组
```

# 4.第四章

#### 1.掌握各类实用小技巧

```Python
ctrl + C			# 强制停止	
ctrl + D			# 退出账户，登出 不能用于vi/vim
history				# 查看历史输入的全部命令
!命令前缀		     # 自动执行上一次匹配前缀的命令(常用于短期使用过的命令)
ctrl + R			# 输入内容去匹配历史命令(常用于古老时期使用的命令)	
		如果搜索到的内容是你需要的,那么：
    					回车直接执行
        				键盘左右键，可以得到此命令(不执行)
# 光标移动
ctrl + A			# 跳到开头
ctrl + E			# 跳到结尾
ctrl + 键盘左键		  # 向左跳一个单词
ctrl + 键盘右键		  # 向右跳一个单词
ctrl + L			# 清屏 clear也可以实现清屏
```

​	ctrl + D 还可以退出特定程序或界面

![image-20240408203622369](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408203622369.png)

​	history命令，可以搭配其他命令；如搭配管道符和 grep过滤信息

![image-20240408204135851](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408204135851.png)

​	!命令前缀   自动执行上一次匹配前缀的命令(只对短期使用过的命令有效)

![image-20240408204858708](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408204858708.png)



#### 2. yum命令安装软件

![image-20240408210836152](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408210836152.png)



#### 3. systemctl命令控制软件

![image-20240408212606266](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408212606266.png)

```Python
start 	开启
stop  	关闭
status	查看
enable	开机自启动
disable	关闭开机自启动
```

**控制内部：查看防火墙状态**

![image-20240408213329422](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240408213329422.png)

**控制外部：查看第三方软件ntpd状态**

![image-20240409200209438](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409200209438.png)

**启动并查看第三方软件httpd**

![image-20240409200750871](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409200750871.png)

#### 4.软连接

#####  ln命令创建软连接

在系统中创建软连接，可以将文件，文件夹连接到其他位置(就是快捷方式)

**语法： ln  -s  参数1  参数2**

​	-s选项，创建软连接

​	参数1：被连接的文件或文件夹

​	参数2：要连接去的目的地



连接文件：把etc文件夹下面的yum.conf 软连接到home目录下

![image-20240409202546995](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409202546995.png)

连接文件夹： 把etc下面的yum文件夹软连接到home目录下

![image-20240409202832466](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409202832466.png)

```python
1.什么是软连接？
	可以将文件，文件夹连接到其它位置
    连接只是一个指向，并不是物理移动，类似于windows系统的快捷方式
2.软连接的使用语法
	ls -s 参数1 参数2
    	-s选项，创建软连接
        参数1：被连接的文件或文件夹
        参数2：要连接去的地方
```



#### 5.日期，时区

##### 	1.data命令查看日期时间

​		通过date命令在命令行中查看系统时间

​		语法：date  [-d]  [+格式化字符串]

​			-d 按照给定的字符串显示日期，一般用于日期计算

​			![image-20240409204335084](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409204335084.png)

​	使用date命令本体，无选项，直接查看时间	

![image-20240409204832379](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409204832379.png)

​	按照2022-1-1的格式显示时间

![image-20240409204923871](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409204923871.png)

​	按照2022-01-01 10:00:00的格式显示日期 (由于中间带空格，所以用双引号包含格式化字符串)

![image-20240409205102269](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409205102269.png)

​	**date命令进行日期加减**

​		-d选项，可以按照给定的字符串显示日期，用于日期计算

```
		year年  month月  day天  hour小时  minute分钟  second秒
```

![image-20240409210208397](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409210208397.png)

​		-d选项，配合格式化字符串一起使用

![image-20240409210626149](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409210626149.png)

##### 	2.修改Linux系统的时区

![image-20240409211118689](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240409211118689.png)

##### 	3.ntp进行时间同步和校准	

```
通过ntp程序自动校准系统时间(当ntp启动后会定期帮助联网校准系统时间)

		安装ntp：yum -y install ntp

		启动并设置开机自启：
				systemctl start ntpd
				systemctl enable ntpd

直接手动校准(root权限): ntpdate -u ntp.aliyun.com		
```



#### 6.  IP地址，主机名

##### 6.1 IP地址和主机名

![image-20240415190516278](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415190516278.png)

**特殊IP地址**

​	127.0.0.1，这个IP地址用于指代本机

​	0.0.0.0 ，特殊IP地址

​			可以用于指代本机

​			可以在端口绑定中用来确定绑定关系

​			在一些IP地址限制中，表示所有IP的意思，如放行规则设置为0.0.0.0，表示允许任意IP访问

**在Linux中修改主机名**

​	使用命令：hostname查看主机名

![image-20240415191953572](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415191953572.png)

​	可以使用命令：hostnamectl set-hostname  主机名  ，修改主机名(需要root)

![image-20240415192358203](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415192358203.png)

​	修改后需重新登录FInalShell即可看到主机名

![image-20240415192432300](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415192432300.png)

**域名解析,域名解析配置**

域名解析(主机名映射)，可以通过主机名找到对应 计算机的IP地址，这就是主机名映射(域名解析)

![image-20240415194112418](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415194112418.png)

配置域名解析

![image-20240415195040271](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415195040271.png)

![image-20240415195232222](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415195232222.png)

##### 6.2虚拟机配置固定IP地址

掌握如何在VMware Fusion中配置Linux系统的固定IP地址

第一步：

![image-20240415202902084](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415202902084.png)



第二步：

![image-20240415202100674](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415202100674.png)

![image-20240415202414300](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415202414300.png)

#### 7.网络传输

##### 7.1 下载和网络请求

​	**1.掌握使用ping命令检查服务器是否可联通**

​	**ping命令**

​	语法： ping  [-c num]  ip或主机名

​		选项：-c，检测次数，不使用-c选项，将无线次数持续检查

​		参数：ip或主机名，被检查的服务器的ip地址或主机名地址

![image-20240415203734202](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415203734202.png)

​	**2.掌握使用wget命令下载文件**

​	**wget命令**：wget是非交互式的文件下载器，可以在命令行内下载网络文件

​	语法： wget  [-b]  URL

​		选项：-b，可选，后台下载，会将日志写入到当前工作目录的wget-log文件

​		参数：URL，下载连接

​	通过tail命令可以监控后台下载进度：tail -f wget-log (无论下载是否完成，都会生成要下载的文件)

​	**3.掌握使用curl命令发起网络请求**

​	**curl命令**：curl可以发送http网络请求，可用于：下载文件，获取信息等

​	语法：curl  [-O]  URL

​		选项：-O，用于下载文件，当URL是下载连接时，可以使用此选项保存文件

​		参数：URL，要发起请求的网络地址



**curl URL** 发送http网络请求

![image-20240415210302921](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415210302921.png)

**curl -O 下载地址** 可以做到和wget命令一样的下载操作

![image-20240415210840853](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240415210840853.png)

```
1.使用ping命令可以测试到某个服务器是否可联通
语法：ping [-c num] ip或主机名
选项：-c，测试的次数

2.使用wget命令可以进行网络文件下载
语法：wget [-b] URL
选项：-b,后台下载

3.使用curl命令可以发起网路请求
语法：curl [-O] URL
选项：-O,用于下载使用
```



##### 7.2 端口

端口，时设备与外界通讯交流的出入口。端口可分为：物理端口和虚拟端口

物理端口：RJ-45，USB，HDML

虚拟端口：是指计算机内部的端口，不可见的。是用来操作系统和外部进行交互的

###### 7.2.1查看端口占用

​	使用nmap命令，安装nmap: yum  -y  install  nmap

![image-20240504114006438](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504114006438.png)

语法：nmap 被查看的ip地址

![image-20240504114030650](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504114030650.png)

###### 7.2.2查看端口占用

通过netstat命令，查看指定端口占用情况

安装:   yum  -y  Install net-tools

![image-20240504121333360](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504121333360.png)

​	语法：netstat  -anp  |  grep  端口号

![image-20240504121601693](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504121601693.png)

```
Linux系统可以支持65535个端口，其中分为三类：

公认端口：1~1023，通常用于系统内置或知名程序的预留使用。SSH服务的22端口，HTTPS服务的443端口

注册端口：1024~49151，通常可以随意使用，用于松散的绑定一些程序\服务

动态端口：49152~65535，通常不会固定绑定程序，而是当程序对外进行网络连接时，临时使用

nmap ip地址，查看指定ip的对外暴露端口
netstat -anp | grep 端口号，查看本机指定端口号的占用情况
```

#### 8.进程管理

进程概念：

​	操作系统为了管理程序，会在每一个程序运行的时候，被操作系统注册为系统中的一个进程，并会为每个进程分配一个独有的进程ID(进程号)

查看进程：

​	语法： ps  -ef	ps [-e  -f]

​	选项：-e，显示出全部的进程

​	选项：-f，以完全格式化形式展示信息(展示全部信息)

![image-20240504123301682](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504123301682.png)

![image-20240504123325518](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504123325518.png)

关闭进程

​	在Linux中，可以通过kill命令关闭进程

​	语法：kill  [-9]  进程ID

​	选项：-9，表示强制关闭进程。不使用此选项会向进程发送信号要求其关闭，但是否关闭看进程自身的处理机制

```
管理进程的命令

ps -ef				 查看进程信息

ps -ef | grep 关键字	过滤指定关键字进程信息

kill [-9] 进程号		  关闭指定进程号的进程
```

#### 9.主机状态

**top命令查看cpu，内存使用情况**

**默认每5秒刷新一次，语法：输入q 或 ctrl+c 退出**

###### 9.1top命令内容详细![image-20240504132457506](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504132457506.png)

```
PID		进程id
USER	进程所属用户
PR		进程优先级，越小越高
NI		负值表示高优先级，正值表示低优先级
VIRT	进程使用虚拟内存，单位KB
RES		进程使用物理内存，单位KB
SHR		进程使用共享内存，单位KB
S:		进程状态(S休眠,R运行,Z僵尸状态,N负数优先级,I空闲状态)
%CPU	进程占用CPU率
%MEM	进程占用内存率
TIME+	进程使用CPU时间总计，单位10毫秒
COMMAND 进程命令或名称或程序文件路径
```

![image-20240504133523227](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504133523227.png)

###### 9.2top命令选项![image-20240504133706296](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504133706296.png)

![image-20240504135019546](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504135019546.png)

###### 9.3磁盘信息监控 df 和 iostat

​	**使用df命令，查看磁盘使用情况**

​	**语法：df  [-h]**

​	**选项：-h，人性化显示**![image-20240504141618750](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504141618750.png)



​	**使用iostat查看CPU，磁盘的相关信息**

​	**语法：iostat  [-x]  [num1]  [num2]**

​	**选项：-x，显示更多信息**

​	**num1：数字，刷新间隔，num2：数字，刷新次数**

```
rKB/S:	每秒发送到设备的读取请求数
WKB/S:	每秒发送到设备的写入请求数
%util:	磁盘利用率

tps:该设备每秒的传输速率(一次传输意为：一次I/O请求；多个逻辑请求可能会被合并为：一次I/O请求)
```

![image-20240504140123280](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504140123280.png)

###### 9.4网络状态监控 sar

**使用sar命令查看网络的相关统计**

**语法:  sar  -n  DEV [num1] [num2]**

**选项：刷新间隔(默认查看一次结束),   num2：查看次数(默认无限次数)**![image-20240504140751424](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504140751424.png)

![image-20240504141216453](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504141216453.png)

```
1.使用top命令：top
	类似win的任务管理器
	查看CPU,内存，进程信息
2.使用df命令： df -h
	查看磁盘使用率
3.使用iostat命令：iostat -x [num1] [num2]
	查看磁盘速率等信息
4.sar -n DEV命令：sar -n DEV [num1] [num2]
	查看网络情况
```

#### 10.环境变量

###### 10.1 理解环境变量的作用

环境变量是操作系统在运行的时候，记录的一些关键性信息，用于辅助系统运行

在Linux系统中执行：**env命令即可查看当前系统中的环境变量**

环境变量是一种KeyValue型结构，就是键值对![image-20240504145432461](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504145432461.png)

###### 10.2 符号$的作用

在Linux系统中执行：**$环境变量(键)，取"环境变量"的值**

echo $PATH

![image-20240504145813063](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504145813063.png)

又或者：echo ${PATH}ABC

当要获取的环境变量值和其他内容混合在一起的时候，用{}来标注环境变量

![image-20240504150023783](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504150023783.png)

###### 10.3 在Linux中配置环境变量

LInux环境变量可以用户自行设置，其中分为：

**临时设置，语法：export 变量名=变量值**

**永久生效：**

​	针对当前用户生效，配置在当前用户的：~/bashrc文件中

​	针对所有用户生效，配置在系统的：	/etc/profile文件中

​	通过语法：source配置文件，进行立刻生效，或重新登陆FinalShell生效



#### 11.上传和下载

除了通过FinalSHell下方窗体进行文件传输外，还可以通过rz，sz命令进行文件传输

rz，sz命令需要安装，通过：yum -y install lrzsz

rz命令：上传。语法：rz

sz命令：下载。语法：sz 要下载的文件

文件会自动下载到桌面的 fsdownload文件夹中

![image-20240504162228476](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504162228476.png)

下载

![image-20240504162405700](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504162405700.png)

```
rz sz命令
	通过yum -y install lrzsz 安装此命令
	rz			  进行文件上传
	sz 文件名		进行文件下载	
```



#### 12.压缩和解压

![image-20240504163109939](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504163109939.png)

如何在LInux系统软件中操作 tar，gzip，zip这三种压缩格式

##### 12.1 使用tar命令压缩或解压tar或gzip文件

​	tar命令

​	Linux和Mac系统常用2种压缩方式，后缀名分别是：

​		**.tar**  称之为tarball，归档文件，即简单将文件组装到一个.tar的文件内，并没有太多体积的减少，仅仅是简单的封装

​		**.gz**     也常见为  .tar  .gz   gzip格式压缩文件，即使用gzip压缩算法将文件压缩到一个文件内，可以极大的减少压缩后的体积

针对两种格式，使用tar命令均可以进行压缩和解压缩的操作

**语法：tar  [-c  -v  -x  -f  -z  -C]  参数1，参数2  ...  参数N**

```
-c	创建压缩文件，用于压缩文件
-v	显示压缩，解压过程，用于查看进度
-x	解压模式
-f	要创建的文件，或要解压的文件，-f选项必须在所有选项中位置处于最后一个
-z	gzip模式，不使用-z就是普通的tarball模式
-C	选项解压的目的地，用于解压模式
```

###### 压缩

```
tar命令压缩固定组合
​	tarball模式 tar -cvf:
​		tar -cvf test.tar  s1.txt 2.txt 3.txt
		将s1.txt 2.txt 3.txt压缩到test.tar内，使用tarball模式
		
​	gzip模式 tar -zcvf:
​		tar -zcvf test.tar.gz  s1.txt 2.txt 3.txt
		将s1.txt 2.txt 3.txt压缩到test.tar.gz内，使用gzip模式

注意：
	-z选项如果使用的话，一般处于选项位第一个
	-f选项，必须在选项位最后一个
```

tarball模式：简单的封装

![image-20240504170543222](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504170543222.png)

gzip模式：减少压缩后的体积

![image-20240504170811801](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504170811801.png)

###### 解压

```
tar解压模式固定组合
​	tarball模式 tar  -xvf:
​ 		tar  -xvf  test.tar
        解压test.tar,将文件解压至当前目录
        
​		tar -xvf test.tar -C /home/itheima
		解压test.tar,将文件解压至指定目录(/home/itheima)
		
​		gzip模式 tar -zxvf:		
​		tar -zxvf test.tar.gz -C /home/itheima
		以gzip模式解压test.tar.gz，将文件解压至指定目录(/home/itheima)
		
注意：
​	-f选项，必须在选项组合体的最后一位
​	-z选项，建议在开头位置
​	-C选项单独使用，和解压所需的其他参数分开
```

tarball模式：默认解压，解压到当前目录

![image-20240504172747977](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504172747977.png)

tarball模式：解压到指定目录

 ![image-20240504173031224](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504173031224.png)	        ![image-20240504173126891](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504173126891.png)

gzip模式：

![image-20240504173810291](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504173810291.png)

##### 12.2 使用zip，unzip命令压缩或解压zip文件

​	语法：zip  [-r]  参数1  参数2  ...  参数N

​	-r，被压缩的包含文件夹的时候，需要使用 -r 选项，和rm，cp等命令的 -r 效果一样

```
压缩
​		zip test.zip a.txt b.txt c.txt
		将 a.txt b.txt c.txt 压缩到 test.zip文件内

​		zip -r test.zip test1 test2 a.txt
		将a.txt和test1 test2两个文件夹 压缩到test.zip文件内
```

![image-20240504175403505](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504175403505.png)

unzip命令解压文件

​	语法：unzip  [-d]  参数

​		-d，指定要解压去的位置，同tar的 -C 选项

​		参数，被解压的zip压缩包文件

```
解压
​		unzip test.zip
		将test.zip解压到当前目录
		
​		unzip test.zip -d /home/rongchi
		将test.zip解压到指定文件夹内(/home/rongchi)
```

![image-20240504180253135](C:\Users\27252\AppData\Roaming\Typora\typora-user-images\image-20240504180253135.png)

```
1.Linux系统常用压缩格式有：
​	tar格式，归档文件，简单将文件整合到一个文件内，无压缩效果
​	gzip格式，gzip压缩文件，不仅能整合到一个文件，同时具有压缩效果

2.tar命令
tar[-z -x -v -c -f -C]参数...
​	-c创建压缩文件，-v查看压缩\解压过程，-x解压模式
​	-f指定压缩\解压文件，-z，gzip模式，-C指定解压的路径
​	-z在选项组建议开头，-f在选协组必须在尾部，-C单独使用

3.zip命令
zip [-r] 参数...
​	-r,压缩文件夹使用

4.unzip命令
unzip [-d] 参数
​	-d,指定解压到的目录
```
