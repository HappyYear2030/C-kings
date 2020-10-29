> 老周的C++学习笔记

# C++

# **C++基本内置类型**

| 关键字      | 类型         |
| ----------- | ------------ |
| **bool**    | **布尔型**   |
| **char**    | **字符型**   |
| **int**     | **整形**     |
| **float**   | **浮点型**   |
| **double**  | **双浮点型** |
| **void**    | **无类型**   |
| **wchar_t** | **宽字符型** |

***

# C++ 变量类型

变量其实只不过是程序可操作的存储区的名称。C++ 中每个变量都有指定的类型，类型决定了变量存储的大小和布局，该范围内的值都可以存储在内存中，运算符可应用于变量上。

变量的名称可以**由字母、数字和下划线字符**组成。它**必须以字母或下划线**开头。大写字母和小写字母是不同的，因为 C++ 是大小写敏感的。

| 类型        | 描述                                                         |
| :---------- | :----------------------------------------------------------- |
| **bool**    | **存储值 true 或 false。**                                   |
| char        | 通常是一个字符（八位）。这是一个整数类型。                   |
| int         | 对机器而言，整数的最自然的大小。                             |
| float       | 单精度浮点值。单精度是这样的格式，1位符号，8位指数，23位小数。![img](https://www.runoob.com/wp-content/uploads/2014/09/v2-749cc641eb4d5dafd085e8c23f8826aa_hd.png) |
| double      | 双精度浮点值。双精度是1位符号，11位指数，52位小数。![img](https://www.runoob.com/wp-content/uploads/2014/09/v2-48240f0e1e0dd33ec89100cbe2d30707_hd.png) |
| void        | 表示类型的缺失。                                             |
| **wchar_t** | **宽字符类型。**                                             |

---

# **C++各类型字节和数据范围**

<table class="reference">
<tbody><tr><th>类型</th><th>位</th><th>范围</th></tr>
<tr><td>char</td><td>1 个字节</td><td>-128 到 127 或者 0 到 255</td></tr>
<tr><td>unsigned char</td><td>1 个字节</td><td>0 到 255</td></tr>
<tr><td>signed char</td><td>1 个字节</td><td>-128 到 127</td></tr>
<tr><td>int</td><td>4 个字节</td><td>-2147483648 到 2147483647</td></tr>
<tr><td>unsigned int</td><td>4 个字节</td><td>0 到 4294967295</td></tr>
<tr><td>signed int</td><td>4 个字节</td><td>-2147483648 到 2147483647</td></tr>
<tr><td>short int</td><td>2 个字节</td><td>-32768 到 32767</td></tr>
<tr><td>unsigned short int</td><td>2 个字节</td><td>0 到 65,535</td></tr>
<tr><td>signed short int</td><td>2 个字节</td><td>-32768 到 32767</td></tr>
<tr><td>long int</td><td>8 个字节</td><td>-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</td></tr>
<tr><td>signed long int</td><td>8 个字节</td><td>-9,223,372,036,854,775,808 到 9,223,372,036,854,775,807</td></tr>
<tr><td>unsigned long int</td><td>8 个字节</td><td>0 到 18,446,744,073,709,551,615</td></tr>
<tr><td>float</td><td>4 个字节</td><td>精度型占4个字节（32位）内存空间，+/- 3.4e +/- 38 (~7 个数字)</td></tr>
<tr><td>double</td><td>8 个字节</td><td>双精度型占8 个字节（64位）内存空间，+/- 1.7e +/- 308 (~15 个数字)</td></tr>
<tr><td>long double</td><td>16 个字节</td><td>长双精度型 16 个字节（128位）内存空间，可提供18-19位有效数字。</td></tr>
<tr><td>wchar_t</td><td>2 或 4 个字节</td><td>1 个宽字符</td></tr>
</tbody></table>
***

# C++枚举类型

>枚举类型(enumeration)是C++中的一种派生数据类型，它是由用户定义的若干枚举常量的集合。如果一个变量只有几种可能的值，可以定义为枚举(enumeration)类型。所谓"枚举"是指将变量的值一一列举出来，**变量的值只能在列举出来的值的范围内。**

## 创建枚举，需要使用关键字 **enum**。枚举类型的一般形式为：

```
enum color { red, green, blue } c;
c = blue;
```

## 如果枚举没有初始化, 即省掉"=整型常数"时, 则从第一个标识符开始。

例如，下面的代码定义了一个颜色枚举，变量 c 的类型为 color。最后，c 被赋值为 "blue"。

<pre class="prettyprint prettyprinted" style=""><span class="kwd">enum</span><span class="pln"> color </span><span class="pun">{</span><span class="pln"> red</span><span class="pun">,</span><span class="pln"> green</span><span class="pun">,</span><span class="pln"> blue </span><span class="pun">}</span><span class="pln"> c</span><span class="pun">;</span><span class="pln">
c </span><span class="pun">=</span><span class="pln"> blue</span><span class="pun">;</span></pre>

默认情况下，第一个名称的值为 0，第二个名称的值为 1，第三个名称的值为 2，以此类推。但是，您也可以给名称赋予一个特殊的值，只需要添加一个初始值即可。例如，在下面的枚举中，**green** 的值为 5。

```
enum color { red, green=5, blue };
```

在这里，**blue** 的值为 6，因为默认情况下，每个名称都会比它前面一个名称大 1，但 red 的值依然为 0。

***

> **虽然您可以在 C++ 程序中多次声明一个变量，但变量只能在某个文件、函数或代码块中被定义一次。**

---

# **初始化局部变量和全局变量**

**当局部变量被定义时，系统不会对其初始化，您必须自行对其初始化。**<u>定义全局变量时，系统会自动初始化为下列值：</u>

| 数据类型 | 初始化默认值 |
| :------- | :----------- |
| int      | 0            |
| char     | '\0'         |
| float    | 0            |
| double   | 0            |
| pointer  | NULL         |

---

# 整数常量

整数常量可以是**十进制、八进制或十六进制的常量。前缀指定基数：0x 或 0X 表示十六进制，0 表示八进制，不带前缀则默认表示十进制**。

**整数常量也可以带一个后缀，后缀是 U 和 L 的组合，U 表示无符号整数（unsigned），L 表示长整数（long）。后缀可以是大写，也可以是小写，U 和 L 的顺序任意。**

---

# C++常用头文件

## 1.#include<iostream

iostream 的意思是输入输出流。#include<iostream>是标准的C++头文件，任何符合标准的C++开发环境都有这个头文件。

## 2.#include<fsteram

fstream是[C++](https://www.baidu.com/s?wd=C%2B%2B&tn=SE_PcZhidaonwhc_ngpagmjz&rsv_dl=gh_pc_zhidao) STL中对文件操作的合集，包含了常用的所有文件操作。其中包含basic_ifstream,basic_ofstream,basic_fstream,basic_filebuf,ifstream,ofstream,fstream,filebuf,wifstream,wofstream, wfstream,wfilebuf 这些类。
其中ifstream用于输入文件流的类，ofstream用于输出文件流的类，fstream是文件流的类，filebuf是文件流缓冲区的类。在C++中，所有的文件操作，都是以流(stream)的方式进行的，fstream也就是文件流file stream。
其中basic修饰的是模板类，不带w修饰的是用于窄字符（char）的类如ifstream,ofstream,fstream,filebuf，带w修饰的类是用于宽字符(w_char)的类如wifstream,wofstream,wfstream,wfilebuf。
最常用的两种操作为：
1).插入器(<<)
　　向流输出数据。比如说打开了一个文件流fout，那么调用fout<<"Write to file"<<endl;就表示把字符串"Write to file"写入文件并换行。
2).析取器(>>)
　　从流中输入数据。比如说打开了文件流fin，那么定义整型变量x的情况下，fin>>x；就是从文件中读取一个整型数据，并存储到x中。

## 3.#include<chrono

>（参考：https://www.jianshu.com/p/1437e612a367）

在C++11中，<chrono>是标准模板库中与时间有关的头文件。该头文件中所有函数与类模板均定义在std::chrono命名空间中。

std::chrono是在C++11中引入的，是一个模板库，用来处理时间和日期的Time library。要使用chrono库，需要include<chrono>，其所有实现均在chrono命名空间下。

std::chrono::duration：记录时间长度的，表示一段时间，如1分钟、2小时、10毫秒等。表示为类模板duration的对象，用一个count representation与一个period precision表示。例如，10毫秒的10为count representation，毫秒为period precision。

第一个模板参数为表示时间计数的数据类型。成员函数count返回该计数。第二个模板参数表示计数的一个周期，一般是std::ratio类型，表示一个周期(即一个时间嘀嗒tick)是秒钟的倍数或分数，在编译时应为一个有理数常量。
std::chrono::time_point：记录时间点的，表示一个具体时间。例如某人的生日、今天的日出时间等。表示为类模板time_point的对象。用相对于一个固定时间点epoch的duration来表示。

std::chrono::clocks：时间点相对于真实物理时间的框架。至少提供了3个clock：

(1)、system_clock：当前系统范围(即对各进程都一致)的一个实时的日历时钟(wallclock)。

(2)、steady_clock：当前系统实现的一个维定时钟，该时钟的每个时间嘀嗒单位是均匀的(即长度相等)。

(3)、high_resolution_clock：当前系统实现的一个高分辨率时钟。

![img](https://img2018.cnblogs.com/blog/1432424/201904/1432424-20190401144302110-1957880066.png)

## 4.#include<algorithm

 >（参考：https://blog.csdn.net/bw9839/article/details/81054773）

\#include<algorithm>：algorithm意为"算法",是C++的标准模版库（STL）中最重要的头文件之一，提供了大量基于迭代器的非成员模版函数。

非修改性序列操作（12个）:
循环: 对序列中的每个元素执行某操作 for_each()
查找: 在序列中找出某个值的第一次出现的位置 find() , 利用底层元素的等于操作符，对范围内的元素与输入的值进行比较。当匹配时，结束搜索，返回该元素的一个 InputIterator 。
在序列中找出符合某谓词的第一个元素 find_if()
在序列中找出一子序列的最后一次出现的位置 find_end()
在序列中找出第一次出现指定值集中之值的位置 find_first_of()
在序列中找出相邻的一对值 adjacent_find()
计数: 在序列中统计某个值出现的次数 count()
在序列中统计与某谓词匹配的次数 count_if()
比较: 找出两个序列相异的第一个元素 mismatch()
两个序列中的对应元素都相同时为真 equal()
搜索: 在序列中找出一子序列的第一次出现的位置 search()
在序列中找出一值的连续n次出现的位置 search_n()

修改性序列操作（27个）:
复制: 从序列的第一个元素起进行复制 copy()
从序列的最后一个元素起进行复制 copy_backward()
交换: 交换两个元素 swap()
交换指定范围的元素 swap_ranges()
交换由迭代器所指的两个元素 iter_swap()
变换: 将某操作应用于指定范围的每个元素 transform()
替换: 用一个给定值替换一些值 replace()
替换满足谓词的一些元素 replace_if()
复制序列时用一给定值替换元素 replace_copy()
复制序列时替换满足谓词的元素 replace_copy_if()
填充: 用一给定值取代所有元素 fill()
用一给定值取代前n个元素 fill_n()
生成: 用一操作的结果取代所有元素 generate()
用一操作的结果取代前n个元素 generate_n()
删除: 删除具有给定值的元素 remove()
删除满足谓词的元素 remove_if()
复制序列时删除具有给定值的元素 remove_copy()
复制序列时删除满足谓词的元素 remove_copy_if()
唯一: 删除相邻的重复元素 unique()
复制序列时删除相邻的重复元素 unique_copy()
反转: 反转元素的次序 reverse()
复制序列时反转元素的次序 reverse_copy()
环移 :循环移动元素 rotate()
复制序列时循环移动元素 rotate_copy()
随机 :采用均匀分布来随机移动元素 random_shuffle()
划分 :将满足某谓词的元素都放到前面 partition()
将满足某谓词的元素都放到前面并维持原顺序 stable_partition()

序列排序及相关操作（27个）:
排序: 以很好的平均效率排序 sort()
排序，并维持相同元素的原有顺序 stable_sort()
将序列的前一部分排好序 partial_sort()
复制的同时将序列的前一部分排好序 partial_sort_copy()
第n个元素： 将第n各元素放到它的正确位置 nth_element()
二分检索： 找到大于等于某值的第一次出现 lower_bound()
找到大于某值的第一次出现 upper_bound()
找到：（在不破坏顺序的前提下）可插入给定值的最大范围 equal_range()
在有序序列中确定给定元素是否存在 binary_search()
归并： 归并两个有序序列 merge()
归并两个接续的有序序列 inplace_merge()
有序结构上的集合操作： 一序列为另一序列的子序列时为真 includes()
构造两个集合的有序并集 set_union()
构造两个集合的有序交集 set_intersection()
构造两个集合的有序差集 set_difference()
构造两个集合的有序对称差集（并-交） set_symmetric_difference()
堆操作： 向堆中加入元素 push_heap()
从堆中弹出元素 pop_heap()
从序列构造堆 make_heap()
给堆排序 sort_heap()
最大和最小： 两个值中较小的 min()
两个值中较大的 max()
序列中的最小元素 min_element()
序列中的最大元素 max_element()
词典比较： 两个序列按字典序的第一个在前 lexicographical_compare()
排列生成器： 按字典序的下一个排列 next_permutation()
按字典序的前一个排列 prev_permutation()

5.#include <unistd.h>

由字面意思，unistd.h是unix std的意思，是POSIX标准定义的unix类系统定义符号常量的头文件，包含了许多UNIX系统服务的函数原型，例如read函数、write函数和getpid函数。

unistd.h含有的常量与函数：

ssize_t   **read**(int, void *, size_t);
int     **unlink**(const char *);
ssize_t   **write**(int, const void *, size_t);
int     **usleep**(useconds_t);
unsigned   **sleep**(unsigned);

int     **access**(const char *, int);
unsigned   **alarm**(unsigned);
int     **chdir**(const char *);
int     **chown**(const char *, uid_t, gid_t);
int     **close**(int);
size_t   **confstr**(int, char *, size_t);
void    **_exit**(int);
pid_t    **fork**(void);

NULL      // Null pointer
SEEK_CUR  // Set file offset to current plus offset.
SEEK_END  // Set file offset to EOF plus offset.
SEEK_SET  // Set file offset to offset.

## 6.#include<thread

> （参考自：https://blog.csdn.net/sevenjoin/article/details/82187127）

C++11中加入了<thread>头文件，此头文件主要声明了std::thread线程类。C++11的标准类std::thread对线程进行了封装，定义了C++11标准中的一些表示线程的类、用于互斥访问的类与方法等。应用C++11中的std::thread便于多线程程序的移值。

std::thread类成员函数：
(1)、get_id：获取线程ID，返回一个类型为std::thread::id的对象。
(2)、joinable：检查线程是否可被join。检查thread对象是否标识一个活动(active)的可行性线程。缺省构造的thread对象、已经完成join的thread对象、已经detach的thread对象都不是joinable。
(3)、join：调用该函数会阻塞当前线程。阻塞调用者(caller)所在的线程直至被join的std::thread对象标识的线程执行结束。
(4)、detach：将当前线程对象所代表的执行实例与该线程对象分离，使得线程的执行可以单独进行。一旦线程执行完毕，它所分配的资源将会被释放。
(5)、native_handle：该函数返回与std::thread具体实现相关的线程句柄。native_handle_type是连接thread类和操作系统SDK API之间的桥梁，如在Linux g++(libstdc++)里，native_handle_type其实就是pthread里面的pthread_t类型，当thread类的功能不能满足我们的要求的时候(比如改变某个线程的优先级)，可以通过thread类实例的native_handle()返回值作为参数来调用相关的pthread函数达到目录。This member function is only present in class thread if the library implementation supports it. If present, it returns a value used to access implementation-specific information associated to the thread.
(6)、swap：交换两个线程对象所代表的底层句柄。
(7)、operator=：moves the thread object
(8)、hardware_concurrency：静态成员函数，返回当前计算机最大的硬件并发线程数目。基本上可以视为处理器的核心数目。

另外，std::thread::id表示线程ID，定义了在运行时操作系统内唯一能够标识该线程的标识符，同时其值还能指示所标识的线程的状态。Values of this type are returned by thread::get_id and this_thread::get_id to identify threads.

有时候我们需要在线程执行代码里面对当前调用者线程进行操作，针对这种情况，C++11里面专门定义了一个命名空间this_thread，此命名空间也声明在<thread>头文件中，其中包括**get_id()函数用来获取当前调用者线程的ID；yield()函数可以用来将调用者线程跳出运行状态，重新交给操作系统进行调度，即当前线程放弃执行，操作系统调度另一线程继续执行；sleep_until()函数是将线程休眠至某个指定的时刻(time point),该线程才被重新唤醒；sleep_for()函数是将线程休眠某个指定的时间片(time span)，该线程才被重新唤醒，不过由于线程调度等原因，实际休眠实际可能比sleep_duration所表示的时间片更长。**

## 7.#include<map

> (参考自：https://blog.csdn.net/superinzaghi747/article/details/52550738;

​            https://blog.csdn.net/qq_34621771/article/details/81164674）

map 是一种关联容器， 提供一对一的关联， 关联的形式为： KEY—-VALUE（键值对），另外关键字不能重复。
map 也可看做是 关键字映射的集合， 即，map中不可出现重复的关键字，每条映射的关键字都是不同的。



1). map最基本的构造函数；
  map<string , int >mapstring;     map<int ,string >mapint;
  map<sring, char>mapstring;     map< char ,string>mapchar;
  map<char ,int>mapchar;       map<int ,char >mapint；
2). map添加数据；
  map<int ,string> maplive;  
  1.maplive.insert(pair<int,string>(102,”aclive”));
  2.maplive.insert(map<int,string>::value_type(321,”hai”));
  3, maplive[112]=”April”;//map中最简单最常用的插入添加！
3).map中元素的查找：
  find()函数返回一个迭代器指向键值为key的元素，如果没找到就返回指向map尾部的迭代器。     
  map<int ,string >::iterator l_it;; 
  l_it=maplive.find(112);
  if(l_it==maplive.end())
        cout<<”we do not find 112”<<endl;
  else cout<<”wo find 112”<<endl;
4).map中元素的删除：
  如果删除112；
  map<int ,string >::iterator l_it;;
  l_it=maplive.find(112);
  if(l_it==maplive.end())
    cout<<”we do not find 112”<<endl;
  else  maplive.erase(l_it);  //delete 112;
5).map中 swap的用法：
 Map中的swap不是一个容器中的元素交换，而是两个容器交换；

6).map的sort问题：
 Map中的元素是自动按key升序排序,所以不能对map用sort函数;

7).  map的基本操作函数：
   C++ Maps是一种关联式容器，包含“关键字/值”对
   begin()      返回指向map头部的迭代器
   clear(）     删除所有元素
   count()      返回指定元素出现的次数
   empty()      如果map为空则返回true
   end()       返回指向map末尾的迭代器
   equal_range()   返回特殊条目的迭代器对
   erase()      删除一个元素
   find()      查找一个元素
   get_allocator()  返回map的配置器
   insert()     插入元素
   key_comp()    返回比较元素key的函数
   lower_bound()   返回键值>=给定元素的第一个位置
   max_size()    返回可以容纳的最大元素个数
   rbegin()     返回一个指向map尾部的逆向迭代器
   rend()      返回一个指向map头部的逆向迭代器
   size()      返回map中元素的个数
   swap()       交换两个map
   upper_bound()   返回键值>给定元素的第一个位置
   value_comp()    返回比较元素value的函数

---

# C++数组

```
double balance[5] = {1000.0, 2.0, 3.4, 7.0, 50.0};
```

```
double balance[] = {1000.0, 2.0, 3.4, 7.0, 50.0};（ C和C++在定义数组时的差别 ）

int a[];//这是错误的

int i;/int i=3;
int a[i];//这个写法也是错的
也就是说静态数组必须有初值
```

---

| 概念                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [多维数组](https://www.runoob.com/cplusplus/cpp-multi-dimensional-arrays.html) | C++ 支持多维数组。多维数组最简单的形式是二维数组。           |
| [指向数组的指针](https://www.runoob.com/cplusplus/cpp-pointer-to-an-array.html) | 您可以通过指定不带索引的数组名称来生成一个指向数组中第一个元素的指针。 |
| [传递数组给函数](https://www.runoob.com/cplusplus/cpp-passing-arrays-to-functions.html) | 您可以通过指定不带索引的数组名称来给函数传递一个指向数组的指针。 |
| **[从函数返回数组](https://www.runoob.com/cplusplus/cpp-return-arrays-from-function.html)** | **C++ 允许从函数返回数组。**（C和C++的差别）**               |

---

# C++字符串

| 序号 | 函数 & 目的                                                  |
| :--- | ------------------------------------------------------------ |
| 1    | **strcpy(s1, s2);** 复制字符串 s2 到字符串 s1。              |
| 2    | **strcat(s1, s2);** 连接字符串 s2 到字符串 s1 的末尾。       |
| 3    | **strlen(s1);** 返回字符串 s1 的长度。                       |
| 4    | **strcmp(s1, s2);** 如果 s1 和 s2 是相同的，则返回 0；如果 s1<s2 则返回值小于 0；如果 s1>s2 则返回值大于 0。 |
| 5    | **strchr(s1, ch);** 返回一个指针，指向字符串 s1 中字符 ch 的第一次出现的位置。 |
| 6    | **strstr(s1, s2);** 返回一个指针，指向字符串 s1 中字符串 s2 的第一次出现的位置。 |

---

# C++引用

## C++ 引用 vs 指针

**引用很容易与指针混淆，它们之间有三个主要的不同：**

- **不存在空引用。引用必须连接到一块合法的内存**。
- **一旦引用被初始化为一个对象，就不能被指向到另一个对象。指针可以在任何时候指向到另一个对象。**
- **引用必须在创建时被初始化。指针可以在任何时间被初始化。**

```
int i = 9;
int& r = i;
cout << i <<end1;
cout << r <<end1;
---
9
9
---
```

---

# C++类，对象

**类定义是以关键字 class 开头**

```
class name{//name为类名
	public:
		elemtype data1;
		elemtype data2;
		elemtype data3;
		...
};
class name{//name为类名
	public://公开
		elemtype data1;
	private://私有
		elemtype data2;
	protected://已受保护
		elemtype data3;
		...
};
int main(){
	name NAME1;//定义一个NAME1类型变量，NAME1为对象
	
	NAME1.data1 = ...;//初始化NAME1变量中的成员
	NAME2.data2 = ...;//初始化NAME1变量中的成员
	NAME3.data3 = ...;//初始化NAME1变量中的成员
			...
}
类的成员可以是函数
```

想要访问私有数据就必须在公开部分创建几个函数 返回私有成员需要一个函数，操作私有成员需要使用其他的公开函数；



| 概念                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [类成员函数](https://www.runoob.com/cplusplus/cpp-class-member-functions.html) | **类的成员函数是指那些把定义和原型写在类定义内部的函数，就像类定义中的其他变量一样。** |
| [类访问修饰符](https://www.runoob.com/cplusplus/cpp-class-access-modifiers.html) | **类成员可以被定义为 public（公开）、private（秘密） 或 protected（保护）。默认情况下是定义为 private。** |
| [构造函数 & 析构函数](https://www.runoob.com/cplusplus/cpp-constructor-destructor.html) | 类的构造函数是一种特殊的函数，在创建一个新的对象时调用。类的析构函数也是一种特殊的函数，在删除所创建的对象时调用。 |
| [C++ 拷贝构造函数](https://www.runoob.com/cplusplus/cpp-copy-constructor.html) | 拷贝构造函数，是一种特殊的构造函数，它在创建对象时，是使用同一类中之前创建的对象来初始化新创建的对象。 |
| [C++ 友元函数](https://www.runoob.com/cplusplus/cpp-friend-functions.html) | **友元函数**可以访问类的 private 和 protected 成员。         |
| [C++ 内联函数](https://www.runoob.com/cplusplus/cpp-inline-functions.html) | 通过内联函数，编译器试图在调用函数的地方扩展函数体中的代码。 |
| [C++ 中的 this 指针](https://www.runoob.com/cplusplus/cpp-this-pointer.html) | 每个对象都有一个特殊的指针 **this**，它指向对象本身。        |
| [C++ 中指向类的指针](https://www.runoob.com/cplusplus/cpp-pointer-to-class.html) | 指向类的指针方式如同指向结构的指针。实际上，类可以看成是一个带有函数的结构。 |
| [C++ 类的静态成员](https://www.runoob.com/cplusplus/cpp-static-members.html) | 类的数据成员和函数成员都可以被声明为静态的。                 |

---

# 函数后的括号

```
elemtype name(void){}//不接受任何类型
elemtype name(int){}//只接受int类型
...
```

# 用cout直接进行进制输出

| 控制符                        | 作 用                                                        |
| :---------------------------- | :----------------------------------------------------------- |
| dec                           | 设置数值的基数为10                                           |
| hex                           | 设置数值的基数为16                                           |
| oct                           | 设置数值的基数为8                                            |
| setfill(c)                    | 设置填充字符c，c可以是字符常量或字符变量                     |
| setprecision(n)               | 设置浮点数的精度为n位。在以一般十进制小数形式输出时，n代表有效数字。在以fixed(固定小数位数)形式和 scientific(指数)形式输出时，n为小数位数 |
| setw(n)                       | 设置字段宽度为n位                                            |
| setiosflags( ios::fixed)      | 设置浮点数以固定的小数位数显示                               |
| setiosftags( ios::scientific) | 设置浮点数以科学记数法(即指数形式)显示                       |
| setiosflags( ios::left)       | 输出数据左对齐                                               |
| setiosflags( ios::right)      | 输出数据右对齐                                               |
| setiosflags( ios::skipws)     | 忽略前导的空格                                               |
| setiosflags( ios::uppercase)  | 数据以十六进制形式输出时字母以大写表示                       |
| setiosflags( ios::lowercase)  | 数据以十六进制形式输出时宇母以小写表示                       |
| setiosflags(ios::showpos)     | 输出正数时给出“+”号                                          |

当我们想对输出的数添加某些属性时可以在前面加(<< hex / oct / dec)(只用过这几个) 但是要注意的是他们会对后面的数据造成影响，比如说我们想要16进制输出，在数据前面加一个 << hex 后面的所有数据都会以16进制输出直到碰上下一个属性，就像 << oct;

``` 
cout << hex << a << b << ...<< oct
```



![image-20201029185109406](C:\Users\周志豪\AppData\Roaming\Typora\typora-user-images\image-20201029185109406.png)

还有强制类型转换 a = 'G', cout << char(a+4);