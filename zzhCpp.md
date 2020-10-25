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

