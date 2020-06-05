title: 音视频学习 (二) C++ 语言入门
author: DevYK
tags:
  - 音视频学习路线
categories:
  - 专题
  - 音视频
date: 2020-06-04 17:40:00
---
![](https://devyk.oss-cn-qingdao.aliyuncs.com/blog/20200106223914.png)

## 前言

上一篇文章我们学习了 C 语言基础，那么按照咱们的学习计划该学习 C++ 语言基础了，如果没有 C/C++ 基础了可以按照我的文章序列跟着敲一篇，不会没什么可怕的，可怕的是不会还不练习，光看是学不会的。前面几篇学习语言基础我知道很枯燥，但是没有 C/C++ 语言基础到时候学习 NDK 的内容你就更看不懂了，完全就像是在看科幻片一样。所以，我们一起加油，一起学习，共同进步 。

<!-- more -->


## 简介

C++ 是一种中级语言，它是由 Bjarne Stroustrup 于 1979 年在贝尔实验室开始设计开发的。C++ 进一步扩充和完善了 C 语言，是一种面向对象的程序设计语言。C++ 可运行于多种平台上，如 Windows、MAC 操作系统以及 UNIX 的各种版本。

## 环境配置

如果您使用的是 Mac ，最快捷的获取 GCC 的方法是从苹果的网站上下载 Xcode 开发环境，并按照安装说明进行安装。一旦安装上 Xcode，您就能使用 GNU 编译器。

开发工具我这里还是使用的 CLion , 下一篇文章讲解 JNI 技术就开始用  AndroidStudio 。

## C++ 语言入门

还是以 ”HelloWorld“ 打开 C++ 的门。

### 1. 基本语法

```c++
#include <iostream> 
// 空间命名
using namespace std;
int main(){//跟 C 一样入口都是 main 函数
  test1();
  return 0;
}
void test1() {
    //1. 使用命名空间
//    cout << "C++ 语言入门第一行代码 Hello World!" << endl;
  	//就是一个对 C++ 打印的封装
    println("", "C++ 语言入门第一行代码 Hello World!");
    //未使用命名空间
//    std::cout << "C++ 语言入门第一行代码 Hello World!" << std::endl;
}
```

输出:

```
C++ 语言入门第一行代码 Hello World!
```

下面我们就来解释一下上面这段最简单的程序的组成部分

- C++ 语言定义了一些头文件，这些头文件包含了程序中必需的或有用的信息。上面这段程序中，包含了头文件 **<iostream>**。
- 下一行是一个 // 的注释。
- 下一行 **using namespace std;** 告诉编译器使用 std 命名空间。命名空间是 C++ 中一个相对新的概念。
- 下一行 **int main()** 是主函数，程序从这里开始执行。
- 下一行调用 test1() 函数
- 下一行 **cout << "C++ 语言入门第一行代码 Hello World!" << endl;** 会在屏幕上显示消息 "C++ 语言入门第一行代码 Hello World!"。
- 下一行 **return 0;** 终止 main( )函数，并向调用进程返回值 0。

中间忽略了一些注释讲解，我相信这还是能看懂的。; 

**1. 使用 g++ 编译**

```
$ g++ *.cpp *.h
$ ./a.out
```

g++ 后面跟用到了的 cpp h 文件

**2. 使用 Clion 工具编译**

直接点击 run,如下所示:

![](https://devyk.oss-cn-qingdao.aliyuncs.com/blog/20191219181436.gif)

跟 C，Java 一样。

### 2. C++ 关键字

下面表格描述了 C++ 中的关键字。这些关键字跟 C/Java 一样都不能作为常量名，变量名或其它标识符名称。

| 关键字           | 说明                                                         | 关键字               | 说明                                                         |
| ---------------- | ------------------------------------------------------------ | -------------------- | ------------------------------------------------------------ |
| **asm**          | 允许在 C++ 程序中嵌入汇编代码                                | **auto**             | （自动，automatic）是存储类型标识符，表明变量"自动"具有本地范围，块范围的变量声明（如for循环体内的变量声明）默认为auto存储类型。 |
| **bool**         | bool（布尔）类型，C++ 中的基本数据结构，其值可选为 true（真）或者 false（假）。C++ 中的 bool 类型可以和 int 混用，具体来说就是 0 代表 false，非 0 代表 true。bool 类型常用于条件判断和函数返回值。 | **break**            | break（中断、跳出），用在switch语句或者循环语句中。程序遇到 break 后，即跳过该程序段，继续后面的语句执行。 |
| **case**         | 用于 switch 语句中，用于判断不同的条件类型。                 | **namespace**        | namespace（命名空间）用于在逻辑上组织类，是一种比类大的结构。 |
| **catch**        | catch 和 try 语句一起用于异常处理。                          | **new**              | new（新建）用于新建一个对象。new 运算符总是返回一个指针。由 new 创建 |
| **char**         | char（字符，character）类型，C++ 中的基本数据结构，其值一般为 0~255 的 int。这 256 个字符对应着 256 个 ASCII 码。char 类型的数据需要用单引号 **'** 括起来。 | **operator**         | operator（操作符）用于操作符重载。这是 C++ 中的一种特殊的函数。 |
| **class**        | class（类）是 C++ 面向对象设计的基础。使用 class 关键字声明一个类。 | **private**          | private（私有的），C++ 中的访问控制符。被标明为 private 的字段只能在本类以及友元中访问。 |
| **const**        | const（常量的，constant）所修饰的对象或变量不能被改变，修饰函数时，该函数不能改变在该函数外面声明的变量也不能调用任何非const函数。在函数的声明与定义时都要加上const，放在函数参数列表的最后一个括号后。在 C++ 中，用 const 声明一个变量，意味着该变量就是一个带类型的常量，可以代替 #define，且比 #define 多一个类型信息，且它执行内链接，可放在头文件中声明；但在 C 中，其声明则必须放在源文件（即 .C 文件）中，在 C 中 const 声明一个变量，除了不能改变其值外，它仍是一具变量。 | **protected**        | protected（受保护的），C++ 中的访问控制符。被标明为 protected 的字段只能在本类以及其继承类和友元中访问。 |
| **const_cast**   | 该运算符用来修改类型的 const 或 volatile 属性。除了 const 或 volatile 修饰之外， type_id 和 expression 的类型是一样的。常量指针被转化成非常量指针，并且仍然指向原来的对象；常量引用被转换成非常量引用，并且仍然指向原来的对象；常量对象被转换成非常量对象。 | **public**           | public（公有的），C++ 中的访问控制符。被标明为 public 的字段可以在任何类 |
| **continue**     | continue（继续）关键字用于循环结构。它使程序跳过代码段后部的部分，与 break 不同的是，continue 不是进入代码段后的部分执行，而是重新开始新的循环。因而它是"继续循环"之意，不是 break（跳出）。 | **register**         | register（寄存器）声明的变量称着寄存器变量，在可能的情况下会直接存放在机器的寄存器中；但对 32 位编译器不起作用，当 global optimizations（全局优化）开的时候，它会做出选择是否放在自己的寄存器中；不过其它与 register 关键字有关的其它符号都对32位编译器有效。 |
| **default**      | default（默认、缺省）用于 switch 语句。当 switch 所有的 case 都不满足时，将进入 default 执行。default 只能放在 switch 语句所有的 case 之后，并且是可选的。 | **reinterpret_cast** | type-id 必须是一个指针、引用、算术类型、函数指针或者成员指针。它可以把一个指针转换成一个整数，也可以把一个整数转换成一个指针（先把一个指针转换成一个整数，在把该整数转换成原类型的指针，还可以得到原先的指针值）。 |
| **delete**       | delete（删除）释放程序动态申请的内存空间。delete 后面通常是一个指针或者数组 []，并且只能 delete 通过 new 关键字申请的指针，否则会发生段错误。 | **return**           | return（返回）用于在函数中返回值。程序在执行到 return 语句后立即返回，return 后面的语句无法执行到。 |
| **do**           | do-while是一类循环结构。与while循环不同，do-while循环保证至少要进入循环体一次。 | **short**            | short（短整型，short integer），C++ 中的基本数据结构，用于表示整数，精度小于 int。 |
| **double**       | double（双精度）类型，C++ 中的基本数据结构，以双精度形式存储一个浮点数。 | **signed**           | signed（有符号），表明该类型是有符号数，和 unsigned 相反。数字类型（整型和浮点型）都可以用 signed 修饰。但默认就是 signed，所以一般不会显式使用。 |
| **dynamic_cast** | dynamic_cast（动态转换），允许在运行时刻进行类型转换，从而使程序能够在一个类层次结构安全地转换类型。dynamic_cast 提供了两种转换方式，把基类指针转换成派生类指针，或者把指向基类的左值转换成派生类的引用。 | **sizeof**           | 由于 C++ 每种类型的大小都是由编译器自行决定的，为了增加可移植性，可以用 sizeof 运算符获得该数据类型占用的字节数。 |
| **else**         | else 紧跟在 if 后面，用于对 if 不成立的情况的选择。          | **static**           | static（静态的）静态变量作用范围在一个文件内，程序开始时分配空间，结束时释放空间，默认初始化为 0，使用时可改变其值。静态变量或静态函数，只有本文件内的代码才可访问它，它的名字（变量名或函数名）在其它文件中不可见。因此也称为"文件作用域"。在 C++ 类的成员变量被声明为 static（称为静态成员变量），意味着它被该类的所有实例所共享，也就是说当某个类的实例修改了该静态成员变量，其修改值为该类的其它所有实例所见；而类的静态成员函数也只能访问静态成员（变量或函数）。类的静态成员变量必须在声明它的文件范围内进行初始化才能使用，private 类型的也不例外。 |
| **enum**         | enum（枚举）类型，给出一系列固定的值，只能在这里面进行选择一个。 | **static_cast**      | 该运算符把 expression 转换为 type-id 类型，但没有运行时类型检查来保证转换的安全性。 |
| **explicit**     | explicit（显式的）的作用是"禁止单参数构造函数"被用于自动型别转换，其中比较典型的例子就是容器类型。在这种类型的构造函数中你可以将初始长度作为参数传递给构造函数。 | **struct**           | struct（结构）类型，类似于 class 关键字，与 C 语言兼容（class 关键字是不与 C 语言兼容的），可以实现面向对象程序设计。 |
| **export**       | 为了访问其他编译单元（如另一代码文件）中的变量或对象，对普通类型（包括基本数据类、结构和类），可以利用关键字 extern，来使用这些变量或对象时；但是对模板类型，则必须在定义这些模板类对象和模板函数时，使用标准 C++ 新增加的关键字 export（导出）。 | **switch**           | switch（转换）类似于 if-else-if 语句，是一种多分枝语句。它提供了一种简洁的书写，并且能够生成效率更好的代码。但是，switch 后面的判断只能是int（char也可以，但char本质上也是一种int类型）。switch 语句最后的 default 分支是可选的。 |
| **extern**       | extern（外部的）声明变量或函数为外部链接，即该变量或函数名在其它文件中可见。被其修饰的变量（外部变量）是静态分配空间的，即程序开始时分配，结束时释放。用其声明的变量或函数应该在别的文件或同一文件的其它地方定义（实现）。在文件内声明一个变量或函数默认为可被外部使用。在 C++ 中，还可用来指定使用另一语言进行链接，这时需要与特定的转换符一起使用。目前仅支持 **C** 转换标记，来支持 C 编译器链接。 | **template**         | template（模板），C++ 中泛型机制的实现。                     |
| **false**        | false（假的），C++ 的基本数据结构 bool 类型的值之一。等同于 int 的 0 值。 | **this**             | this 返回调用者本身的指针。                                  |
| **float**        | float（浮点数），C++ 中的基本数据结构，精度小于 double。     | **throw**            | throw（抛出）用于实现 C++ 的异常处理机制，可以通过 throw 关键字"抛出"一个异常。 |
| **for**          | for 是 C++ 中的循环结构之一。                                | **true**             | true（真的），C++ 的基本数据结构 bool 类型的值之一。等同于 int 的非 0 值。 |
| **friend**       | friend（友元）声明友元关系。友元可以访问与其有 friend 关系的类中的 private/protected 成员，通过友元直接访问类中的 private/protected 成员的主要目的是提高效率。友元包括友元函数和友元类。 | **try**              | try（尝试）用于实现 C++ 的异常处理机制。可以在 try 中调用可能抛出异常的函数，然后在 try 后面的 catch 中捕获并进行处理。 |
| **goto**         | goto（转到），用于无条件跳转到某一标号处开始执行。           | **typedef**          | 类型说明定义了一个数据类型的新名字而不是定义一种新的数据类型。定义名表示这个类型的新名字。 |
| **if**           | if（如果），C++ 中的条件语句之一，可以根据后面的 bool 类型的值选择进入一个分支执行。 | **typeid**           | 指出指针或引用指向的对象的实际派生类型。                     |
| **inline**       | inline（内联）函数的定义将在编译时在调用处展开。inline 函数一般由短小的语句组成，可以提高程序效率。 | **typename**         | typename（类型名字）关键字告诉编译器把一个特殊的名字解释成一个类型。 |
| **int**          | int（整型，integer），C++ 中的基本数据结构，用于表示整数，精度小于 long。 | **union**            | union（联合），类似于 enum。不同的是 enum 实质上是 int 类型的，而 union 可以用于所有类型，并且其占用空间是随着实际类型大小变化的。 |
| **long**         | long（长整型，long integer），C++ 中的基本数据结构，用于表示长整数。 | **unsigned**         | unsigned（无符号），表明该类型是无符号数，和 signed 相反。   |
| **mutable**      | mutable（易变的）是 C++ 中一个不常用的关键字。只能用于类的非静态和非常量数据成员。由于一个对象的状态由该对象的非静态数据成员决定，所以随着数据成员的改变，对像的状态也会随之发生变化。如果一个类的成员函数被声明为 const 类型，表示该函数不会改变对象的状态，也就是该函数不会修改类的非静态数据成员。但是有些时候需要在该类函数中对类的数据成员进行赋值，这个时候就需要用到 mutable 关键字。 | **using**            | 表明使用 namespace。                                         |
| **virtual**      | virtual（虚的），C++ 中用来实现多态机制。                    | **void**             | void（空的），可以作为函数返回值，表明不返回任何数据；可以作为参数，表明没有参数传入（C++中不是必须的）；可以作为指针使用。 |
| **volatile**     | volatile（不稳定的）限定一个对象可被外部进程（操作系统、硬件或并发线程等）改变 | **wchar_t**          | wchar_t 是宽字符类型，每个 wchar_t 类型占 2 个字节，16 位宽。汉字的表示就要用到 wchar_t。 |

### 4. 数据类型

**基本的内置类型**

C++ 为程序员提供了种类丰富的内置数据类型和用户自定义的数据类型。下表列出了七种基本的 C++ 数据类型：

| 类型     | 关键字                                            |
| :------- | :------------------------------------------------ |
| 布尔型   | bool                                              |
| 字符型   | char                                              |
| 整型     | int                                               |
| 浮点型   | float                                             |
| 双浮点型 | double                                            |
| 无类型   | void                                              |
| 宽字符型 | wchar_t (wchar_t 实际上的空间是和 short int 一样) |

下表显示了各种变量类型在内存中存储值时需要占用的内存，以及该类型的变量所能存储的最大值和最小值。

**注意：**不同系统会有所差异。

| 类型               | 位            | 范围                                                         |
| :----------------- | :------------ | :----------------------------------------------------------- |
| char               | 1 个字节      | -128 到 127 或者 0 到 255                                    |
| unsigned char      | 1 个字节      | 0 到 255                                                     |
| signed char        | 1 个字节      | -128 到 127                                                  |
| int                | 4 个字节      | -2147483648 到 2147483647                                    |
| unsigned int       | 4 个字节      | 0 到 4294967295                                              |
| signed int         | 4 个字节      | -2147483648 到 2147483647                                    |
| short int          | 2 个字节      | -32768 到 32767                                              |
| unsigned short int | 2 个字节      | 0 到 65,535                                                  |
| signed short int   | 2 个字节      | -32768 到 32767                                              |
| long int           | 8 个字节      | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807      |
| signed long int    | 8 个字节      | -9,223,372,036,854,775,808 到 9,223,372,036,854,775,807      |
| unsigned long int  | 8 个字节      | 0 到 18,446,744,073,709,551,615                              |
| float              | 4 个字节      | 精度型占4个字节（32位）内存空间，+/- 3.4e +/- 38 (~7 个数字) |
| double             | 8 个字节      | 双精度型占8 个字节（64位）内存空间，+/- 1.7e +/- 308 (~15 个数字) |
| long double        | 16 个字节     | 长双精度型 16 个字节（128位）内存空间，可提供18-19位有效数字。 |
| wchar_t            | 2 或 4 个字节 | 1 个宽字符                                                   |

从上表可得知，变量的大小会根据编译器和所使用的电脑而有所不同。

下面实例会输出您电脑上各种数据类型的大小。

```c++
void test2() {
    println("C++\t\t", "**************基本数据类型 Size ***********\n");

    println("bool\t\t", "所占字节数:", sizeof(bool), "\t\t最大值:",
            (numeric_limits<bool>::max)(), "\t\t最小值:", (numeric_limits<bool>::min)());
    println("char\t\t", "所占字节数:", sizeof(char), "\t\t最大值:",
            (numeric_limits<char>::max)(), "\t\t最小值:", (numeric_limits<char>::min)());
    println("unsigned char\t\t", "所占字节数:", sizeof(unsigned char), "\t\t最大值:",
            (numeric_limits<unsigned char>::max)(), "\t\t最小值:", (numeric_limits<unsigned char>::min)());
    println("signed char\t\t", "所占字节数:", sizeof(signed char), "\t\t最大值:",
            (numeric_limits<signed char>::max)(), "\t\t最小值:", (numeric_limits<signed char>::min)());
    println("int\t\t", "所占字节数:", sizeof(int), "\t\t最大值:",
            (numeric_limits<int>::max)(), "\t\t最小值:", (numeric_limits<int>::min)());
    println("unsigned int\t\t", "所占字节数:", sizeof(unsigned int), "\t\t最大值:",
            (numeric_limits<unsigned int>::max)(), "\t\t最小值:", (numeric_limits<unsigned int>::min)());
    println("signed int\t\t", "所占字节数:", sizeof(signed int), "\t\t最大值:",
            (numeric_limits<signed int>::max)(), "\t\t最小值:", (numeric_limits<signed int>::min)());
    println("short int\t\t", "所占字节数:", sizeof(short int), "\t\t最大值:",
            (numeric_limits<short int>::max)(), "\t\t最小值:", (numeric_limits<short int>::min)());
    println("unsigned short int\t\t", "所占字节数:", sizeof(unsigned short int), "\t\t最大值:",
            (numeric_limits<unsigned short int>::max)(), "\t\t最小值:", (numeric_limits<unsigned short int>::min)());
    println("signed short int\t\t", "所占字节数:", sizeof(signed short int), "\t\t最大值:",
            (numeric_limits<signed short int>::max)(), "\t\t最小值:", (numeric_limits<signed short int>::min)());
    println("long int\t\t", "所占字节数:", sizeof(long int), "\t\t最大值:",
            (numeric_limits<long int>::max)(), "\t\t最小值:", (numeric_limits<long int>::min)());
    println("signed long int\t\t", "所占字节数:", sizeof(signed long int), "\t\t最大值:",
            (numeric_limits<signed long int>::max)(), "\t\t最小值:", (numeric_limits<signed long int>::min)());
    println("unsigned long int\t\t", "所占字节数:", sizeof(unsigned long int), "\t\t最大值:",
            (numeric_limits<unsigned long int>::max)(), "\t\t最小值:", (numeric_limits<unsigned long int>::min)());
    println("float\t\t", "所占字节数:", sizeof(float), "\t\t最大值:",
            (numeric_limits<float>::max)(), "\t\t最小值:", (numeric_limits<float>::min)());
    println("double\t\t", "所占字节数:", sizeof(double), "\t\t最大值:",
            (numeric_limits<double>::max)(), "\t\t最小值:", (numeric_limits<double>::min)());
    println("long double\t\t", "所占字节数:", sizeof(long double), "\t\t最大值:",
            (numeric_limits<long double>::max)(), "\t\t最小值:", (numeric_limits<long double>::min)());
    println("wchar_t\t\t", "所占字节数:", sizeof(wchar_t), "\t\t最大值:",
            (numeric_limits<wchar_t>::max)(), "\t\t最小值:", (numeric_limits<wchar_t>::min)());

}
```

输出:

> ```
> /**
>  *   bool                 所占字节数:1       最大值:1                 最小值:0
>  *   char                 所占字节数:1       最大值:127               最小值:-128
>  *   unsigned char        所占字节数:1       最大值:255               最小值:0
>  *   signed char          所占字节数:1       最大值:127               最小值:-128
>  *   int                  所占字节数:4       最大值:2147483647        最小值:-2147483648
>  *   unsigned int         所占字节数:4       最大值:-1            		最小值:0
>  *   signed int           所占字节数:4       最大值:2147483647    		最小值:-2147483648
>  *   short int            所占字节数:2       最大值:32767             最小值:-32768
>  *   unsigned short int   所占字节数:2       最大值:65535             最小值:0
>  *   signed short int     所占字节数:2       最大值:32767             最小值:-32768
>  *   long int             所占字节数:8       最大值:-1            		最小值:0
>  *   signed long int      所占字节数:8       最大值:-1            		最小值:0
>  *   unsigned long int    所占字节数:8       最大值:-1            		最小值:0
>  *   float                所占字节数:4       最大值:-2147483648       最小值:0
>  *   double               所占字节数:8       最大值:-2147483648       最小值:0
>  *   long double          所占字节数:16      最大值:-2147483648       最小值:0
>  *   wchar_t              所占字节数:4       最大值:2147483647    		最小值:-2147483648
> */
> ```

**typedef 声明**

您可以使用 **typedef** 为一个已有的类型取一个新的名字。下面是使用 typedef 定义一个新类型的语法：

```c++
//格式: typedef type newname; 
//例子
typedef int feet;
```

现在，下面的声明是完全合法的，它创建了一个整型变量 distance：

```c++
feet distance;
```

**枚举类型**

枚举类型(enumeration)是C++中的一种派生数据类型，它是由用户定义的若干枚举常量的集合。

如果一个变量只有几种可能的值，可以定义为枚举(enumeration)类型。所谓"枚举"是指将变量的值一一列举出来，变量的值只能在列举出来的值的范围内。

创建枚举，需要使用关键字 **enum** 跟 Java 语法差不多。枚举类型的一般形式为： 

```c++
enum 枚举名{ 
     标识符[=整型常数], 
     标识符[=整型常数], 
... 
    标识符[=整型常数]
} 枚举变量;
```

如果枚举没有初始化, 即省掉"=整型常数"时, 则从第一个标识符开始。

例如，下面的代码定义了一个颜色枚举，变量 c 的类型为 color。最后，c 被赋值为 "blue"。

```c++
enum color { red, green, blue } c;
c = blue;
```

默认情况下，第一个名称的值为 0，第二个名称的值为 1，第三个名称的值为 2，以此类推。但是，您也可以给名称赋予一个特殊的值，只需要添加一个初始值即可。例如，在下面的枚举中，**green** 的值为 5。

```c++
enum color { red, green=5, blue };
```

在这里，**blue** 的值为 6，因为默认情况下，每个名称都会比它前面一个名称大 1，但 red 的值依然为 0。

### 5. 变量类型

变量其实只不过是程序可操作的存储区的名称。C++ 中每个变量都有指定的类型，类型决定了变量存储的大小和布局，该范围内的值都可以存储在内存中，运算符可应用于变量上。

变量的名称可以由字母、数字和下划线字符组成。它必须以字母或下划线开头。大写字母和小写字母是不同的，因为 C++ 是大小写敏感的。

C++ 也允许定义各种其他类型的变量，比如**枚举、指针、数组、引用、数据结构、类**等等，这将会在后续的章节中进行讲解。

下面我们将讲解如何定义、声明和使用各种类型的变量。

**定义:**

变量定义就是告诉编译器在何处创建变量的存储，以及如何创建变量的存储。变量定义指定一个数据类型，并包含了该类型的一个或多个变量的列表，如下所示：

```c++
//格式：type variable_list;
//在这里，type 必须是一个有效的 C++ 数据类型，可以是 char、wchar_t、int、float、double、bool 或任何用户自定义的对象，variable_list 可以由一个或多个标识符名称组成，多个标识符之间用逗号分隔。

//例子:
int    i, j, k;
char   c, ch;
float  f, salary;
double d;

```

**变量声明:**

变量声明向编译器保证变量以给定的类型和名称存在，这样编译器在不需要知道变量完整细节的情况下也能继续进一步的编译。变量声明只在编译时有它的意义，在程序连接时编译器需要实际的变量声明。

当您使用多个文件且只在其中一个文件中定义变量时（定义变量的文件在程序连接时是可用的），变量声明就显得非常有用。您可以使用 **extern** 关键字在任何地方声明一个变量。虽然您可以在 C++ 程序中多次声明一个变量，但变量只能在某个文件、函数或代码块中被定义一次。

**例子:**

```c++
//声明变量
extern int a, b;
extern int c;
extern float f;

void test3() {
//变量定义
    int a, b;
    int c;
    float f;

//init
    a = 10;
    b = 20;
    c = a + b;
    println("声明变量\t", "a + b=", c);

    f = 10 / 3;
    println("声明变量\t", "10/3=", f);
}
```

输出:

> 声明变量	a + b=30
> 声明变量	10/3=3

### 6. 变量作用域

作用域是程序的一个区域，一般来说有三个地方可以定义变量：

- 在函数或一个代码块内部声明的变量，称为局部变量。
- 在函数参数的定义中声明的变量，称为形式参数。
- 在所有函数外部声明的变量，称为全局变量。

我们将在后续的小节中学习什么是函数和参数。本小节我们先来讲解什么是局部变量和全局变量。

**局部变量:**

在函数或一个代码块内部声明的变量，称为局部变量。它们只能被函数内部或者代码块内部的语句使用。下面的实例使用了局部变量：

```c++
void test4() {
    //局部变量声明
    int i = 10, j = 20;
    int c;
    c = i * j;
    println("局部变量:", "i * j=", c);

}
```

输出:

> 局部变量:i * j=200

**全局变量:**

在所有函数外部定义的变量（通常是在程序的头部），称为全局变量。全局变量的值在程序的整个生命周期内都是有效的。

全局变量可以被任何函数访问。也就是说，全局变量一旦声明，在整个程序中都是可用的。下面的实例使用了全局变量和局部变量：

```c++
int g, l = 20;//声明全局变量

void test4() {
    //局部变量声明
    int i = 10, j = 10;
    int c;
    c = i * j;
    println("局部变量:", "i * j=", c);

    //赋值给全局变量
    g = (int)i / j;
    println("全局变量:", "i / j=", g);

    println("全局变量:", "l =", l);
    l = 100;//重新赋值给全局变量 l
    println("全局变量:", "l =", l);

}
```

输出:

> 局部变量:i * j=100
> 全局变量:i / j=1
> 全局变量:l =20
> 全局变量:l =100

**初始化局部变量和全局变量:**

当局部变量被定义时，系统不会对其初始化，您必须自行对其初始化。定义全局变量时，系统会自动初始化为下列值：

| 数据类型 | 初始化默认值 |
| :------- | :----------- |
| int      | 0            |
| char     | '\0'         |
| float    | 0            |
| double   | 0            |
| pointer  | NULL         |

正确地初始化变量是一个良好的编程习惯，否则有时候程序可能会产生意想不到的结果。

### 7. 常量

常量是固定值，在程序执行期间不会改变。这些固定的值，又叫做**字面量**。

**整数常量:**

整数常量可以是十进制、八进制或十六进制的常量。前缀指定基数：0x 或 0X 表示十六进制，0 表示八进制，不带前缀则默认表示十进制。

整数常量也可以带一个后缀，后缀是 U 和 L 的组合，U 表示无符号整数（unsigned），L 表示长整数（long）。后缀可以是大写，也可以是小写，U 和 L 的顺序任意。

下面列举几个整数常量的实例：

```c++
212         // 合法的
215u        // 合法的
0xFeeL      // 合法的
078         // 非法的：8 不是八进制的数字
032UU       // 非法的：不能重复后缀
  
85         // 十进制
0213       // 八进制 
0x4b       // 十六进制 
30         // 整数 
30u        // 无符号整数 
30l        // 长整数 
30ul       // 无符号长整数
```

**浮点常量:**

浮点常量由整数部分、小数点、小数部分和指数部分组成。您可以使用小数形式或者指数形式来表示浮点常量。

当使用小数形式表示时，必须包含整数部分、小数部分，或同时包含两者。当使用指数形式表示时， 必须包含小数点、指数，或同时包含两者。带符号的指数是用 e 或 E 引入的。

下面列举几个浮点常量的实例：

```c++
3.14159       // 合法的 
314159E-5L    // 合法的 
510E          // 非法的：不完整的指数
210f          // 非法的：没有小数或指数
.e55          // 非法的：缺少整数或分数
```

**布尔常量:**

布尔常量共有两个，它们都是标准的 C++ 关键字：

- **true** 值代表真。
- **false** 值代表假。

我们不应把 true 的值看成 1，把 false 的值看成 0。

**字符常量:**

字符常量是括在单引号中。如果常量以 L（仅当大写时）开头，则表示它是一个宽字符常量（例如 L'x'），此时它必须存储在 **wchar_t** 类型的变量中。否则，它就是一个窄字符常量（例如 'x'），此时它可以存储在 **char** 类型的简单变量中。

字符常量可以是一个普通的字符（例如 'x'）、一个转义序列（例如 '\t'），或一个通用的字符（例如 '\u02C0'）。

在 C++ 中，有一些特定的字符，当它们前面有反斜杠时，它们就具有特殊的含义，被用来表示如换行符（\n）或制表符（\t）等。下表列出了一些这样的转义序列码：

| 转义序列   | 含义                       |
| :--------- | :------------------------- |
| \\         | \ 字符                     |
| \'         | ' 字符                     |
| \"         | " 字符                     |
| \?         | ? 字符                     |
| \a         | 警报铃声                   |
| \b         | 退格键                     |
| \f         | 换页符                     |
| \n         | 换行符                     |
| \r         | 回车                       |
| \t         | 水平制表符                 |
| \v         | 垂直制表符                 |
| \ooo       | 一到三位的八进制数         |
| \xhh . . . | 一个或多个数字的十六进制数 |

```c++
void test5() {
    //字符常量
    println("字符常量", "\tC\n+\n+\n");
}

```

输出:

> 字符常量	C
> +
> +

**字符串常量:**

字符串字面值或常量是括在双引号 "" 中的。一个字符串包含类似于字符常量的字符：普通的字符、转义序列和通用的字符。

您可以使用空格做分隔符，把一个很长的字符串常量进行分行。

下面的实例显示了一些字符串常量。下面这三种形式所显示的字符串是相同的。

```c++
"hello, World"

"hello, \

World"

"hello, " "W" "orld"

```

**定义常量:**

在 C++ 中，有两种简单的定义常量的方式：

- 使用 **#define** 预处理器。
- 使用 **const** 关键字。

```c++
//定义常量 const,#define
#define NAME "DevYK"
#define Blog "https://www.devyk.top"

const string _NAME = "DevYK", _Blog = "https://www.devyk.top";

void test5() {
    //打印定义的常量
    println("#define 定义常量:", NAME "\t" Blog);
    //const 定义的常量
    const int length = 10, width = 20, height = 30;
    cout << "const 定义的常量\t" << _NAME << "\t" + _Blog << endl;
    println("const 定义常量\t", "求 width * height * length = ", length * width * height);
}

```

输出:

> define 定义常量:DevYK	https://www.devyk.top
> const 定义的常量	DevYK	https://www.devyk.top
> const 定义常量	求 width * height * length = 6000

### 8. 修饰符类型

C++ 允许在 **char、int 和 double** 数据类型前放置修饰符。修饰符用于改变基本类型的含义，所以它更能满足各种情境的需求。

下面列出了数据类型修饰符：

- signed
- unsigned
- long
- short

修饰符 **signed、unsigned、long 和 short** 可应用于整型，**signed** 和 **unsigned** 可应用于字符型，**long** 可应用于双精度型。

修饰符 **signed** 和 **unsigned** 也可以作为 **long** 或 **short** 修饰符的前缀。例如：**unsigned long int**。

C++ 允许使用速记符号来声明**无符号短整数**或**无符号长整数**。您可以不写 int，只写单词 **unsigned、short** 或 **unsigned、long**，int 是隐含的。例如，下面的两个语句都声明了无符号整型变量。

```c++
unsigned x;
unsigned int y;

```

为了理解 C++ 解释有符号整数和无符号整数修饰符之间的差别，我们来运行一下下面这个短程序：

```c++
void test6() {
    //演示有符号和无符号整数之间的差别
    short int i;
    int k;
    short unsigned int j;
    j = 50000;
    i = j;
    k = j;
    cout << i << " " << j << " " << k << endl;

}

```

输出:

> -15536 50000 50000

上述结果中，无符号短整数 50,000 的位模式被解释为有符号短整数 -15,536。

### 9. 存储类

存储类定义 C++ 程序中变量/函数的范围（可见性）和生命周期。这些说明符放置在它们所修饰的类型之前。下面列出 C++ 程序中可用的存储类：

- auto
- register
- static
- extern
- mutable
- thread_local (C++11)

从 C++ 17 开始，auto 关键字不再是 C++ 存储类说明符，且 register 关键字被弃用。

**auto 存储类:**

自 C++ 11 以来，**auto** 关键字用于两种情况：声明变量时根据初始化表达式自动推断该变量的类型、声明函数时函数返回值的占位符。

C++98标准中auto关键字用于自动变量的声明，但由于使用极少且多余，在C++11中已删除这一用法。

根据初始化表达式自动推断被声明的变量的类型，如：

```c++
auto f=3.14;      //double
auto s("hello");  //const char*
auto z = new auto(9); // int*
auto x1 = 5, x2 = 5.0, x3='r';//错误，必须是初始化为同一类型

```

**register 存储类:**

**register** 存储类用于定义存储在寄存器中而不是 RAM 中的局部变量。这意味着变量的最大尺寸等于寄存器的大小（通常是一个词），且不能对它应用一元的 '&' 运算符（因为它没有内存位置）。

```c++
{
   register int  miles;
}

```

寄存器只用于需要快速访问的变量，比如计数器。还应注意的是，定义 'register' 并不意味着变量将被存储在寄存器中，它意味着变量可能存储在寄存器中，这取决于硬件和实现的限制。

**static 存储类:**

**static** 存储类指示编译器在程序的生命周期内保持局部变量的存在，而不需要在每次它进入和离开作用域时进行创建和销毁。因此，使用 static 修饰局部变量可以在函数调用之间保持局部变量的值。

static 修饰符也可以应用于全局变量。当 static 修饰全局变量时，会使变量的作用域限制在声明它的文件内。

在 C++ 中，当 static 用在类数据成员上时，会导致仅有一个该成员的副本被类的所有对象共享。

```c++
//函数声明
void test7_fun(void);

//声明全局变量
static int valueCount = 5;


void test7() {
    //1.
    while(valueCount--){
        test7_fun();
    }
}

void test7_fun() {
    //使用 static 修饰局部变量可以在函数调用之间保持局部变量的值。
    static int value = 5;
    value++;
    cout << "变量 value 为：" << value << endl;
    cout << "变量 valueCount 为：" << valueCount << endl;
}

```

输出:

> 变量 value 为：6
> 变量 valueCount 为：4
> 变量 value 为：7
> 变量 valueCount 为：3
> 变量 value 为：8
> 变量 valueCount 为：2
> 变量 value 为：9
> 变量 valueCount 为：1
> 变量 value 为：10
> 变量 valueCount 为：0

**extern 存储类:**

**extern** 存储类用于提供一个全局变量的引用，全局变量对所有的程序文件都是可见的。当您使用 'extern' 时，对于无法初始化的变量，会把变量名指向一个之前定义过的存储位置。

当您有多个文件且定义了一个可以在其他文件中使用的全局变量或函数时，可以在其他文件中使用 *extern* 来得到已定义的变量或函数的引用。可以这么理解，*extern* 是用来在另一个文件中声明一个全局变量或函数。

extern 修饰符通常用于当有两个或多个文件共享相同的全局变量或函数的时候，如下所示：

第一个文件: main.cpp

```c++
//extern 存储值
extern void value_extern();

void test7() {
    value_extern();
}

```

第二个文件：main_1.cpp

```c++
#include <iostream>

using namespace std;
void value_extern(void){
    cout << "value_extern 执行了" <<endl;
}

```

输出:

> value_extern 执行了

### 10. 运算符

运算符是一种告诉编译器执行特定的数学或逻辑操作的符号。C++ 内置了丰富的运算符，并提供了以下类型的运算符：

- 算术运算符
- 关系运算符
- 逻辑运算符
- 位运算符
- 赋值运算符
- 杂项运算符

本小节将逐一介绍算术运算符、关系运算符、逻辑运算符、位运算符、赋值运算符和其他运算符。

**算术运算符:**

下表显示了 C++ 支持的算术运算符。

假设变量 A 的值为 10，变量 B 的值为 20，则：

| 运算符 | 描述                                                         | 实例             |
| :----- | :----------------------------------------------------------- | :--------------- |
| +      | 把两个操作数相加                                             | A + B 将得到 30  |
| -      | 从第一个操作数中减去第二个操作数                             | A - B 将得到 -10 |
| *      | 把两个操作数相乘                                             | A * B 将得到 200 |
| /      | 分子除以分母                                                 | B / A 将得到 2   |
| %      | 取模运算符，整除后的余数                                     | B % A 将得到 0   |
| ++     | [自增运算符](https://www.runoob.com/cplusplus/cpp-increment-decrement-operators.html)，整数值增加 1 | A++ 将得到 11    |
| --     | [自减运算符](https://www.runoob.com/cplusplus/cpp-increment-decrement-operators.html)，整数值减少 1 | A-- 将得到 9     |

```c++
void test8() {
    //算术运算符
    int a = 21;
    int b = 10;
    int c;

    c = a + b;
    cout << "Line 1 - c 的值是 " << c << endl;
    c = a - b;
    cout << "Line 2 - c 的值是 " << c << endl;
    c = a * b;
    cout << "Line 3 - c 的值是 " << c << endl;
    c = a / b;
    cout << "Line 4 - c 的值是 " << c << endl;
    c = a % b;
    cout << "Line 5 - c 的值是 " << c << endl;

    int d = 10;   //  测试自增、自减
    c = d++; //先赋值，再自增
    cout << "Line 6 - c 的值是 " << c << " " << d << endl;

    d = 12;    // 重新赋值
    c = d--; //先赋值，再自减
    cout << "Line 7 - c 的值是 " << c << " " << d << endl;

}

```

输出:

> Line 1 - c 的值是 31
> Line 2 - c 的值是 11
> Line 3 - c 的值是 210
> Line 4 - c 的值是 2
> Line 5 - c 的值是 1
> Line 6 - c 的值是 10 11
> Line 7 - c 的值是 12 11

**关系运算符:**

下表显示了 C++ 支持的关系运算符。

假设变量 A 的值为 10，变量 B 的值为 20，则：

| 运算符 | 描述                                                         | 实例              |
| :----- | :----------------------------------------------------------- | :---------------- |
| ==     | 检查两个操作数的值是否相等，如果相等则条件为真。             | (A == B) 不为真。 |
| !=     | 检查两个操作数的值是否相等，如果不相等则条件为真。           | (A != B) 为真。   |
| >      | 检查左操作数的值是否大于右操作数的值，如果是则条件为真。     | (A > B) 不为真。  |
| <      | 检查左操作数的值是否小于右操作数的值，如果是则条件为真。     | (A < B) 为真。    |
| >=     | 检查左操作数的值是否大于或等于右操作数的值，如果是则条件为真。 | (A >= B) 不为真。 |
| <=     | 检查左操作数的值是否小于或等于右操作数的值，如果是则条件为真。 | (A <= B) 为       |

```c++
void test8() {   
    //关系运算符
    if (a == b) {
        cout << "Line 1 - a 等于 b" << endl;
    } else {
        cout << "Line 1 - a 不等于 b" << endl;
    }
    if (a < b) {
        cout << "Line 2 - a 小于 b" << endl;
    } else {
        cout << "Line 2 - a 不小于 b" << endl;
    }
    if (a > b) {
        cout << "Line 3 - a 大于 b" << endl;
    } else {
        cout << "Line 3 - a 不大于 b" << endl;
    }
    /* 改变 a 和 b 的值 */
    a = 5;
    b = 20;
    if (a <= b) {
        cout << "Line 4 - a 小于或等于 b" << endl;
    }
    if (b >= a) {
        cout << "Line 5 - b 大于或等于 a" << endl;
    }
}

```

输出:

> Line 1 - a 不等于 b
> Line 2 - a 不小于 b
> Line 3 - a 大于 b
> Line 4 - a 小于或等于 b
> Line 5 - b 大于或等于 a

**逻辑运算符:**

下表显示了 C++ 支持的关系逻辑运算符。

假设变量 A 的值为 1，变量 B 的值为 0，则：

| 运算符 | 描述                                                         | 实例              |
| :----- | :----------------------------------------------------------- | :---------------- |
| &&     | 称为逻辑与运算符。如果两个操作数都非零，则条件为真。         | (A && B) 为假。   |
| \|\|   | 称为逻辑或运算符。如果两个操作数中有任意一个非零，则条件为真。 | (A \|\| B) 为真。 |
| !      | 称为逻辑非运算符。用来逆转操作数的逻辑状态。如果条件为真则逻辑非运算符将使其为假。 | !(A && B) 为真。  |

```c++
void test8() {
  
    //逻辑运算符

    if (a && b) {
        cout << "Line 1 - 条件为真" << endl;
    }
    if (a || b) {
        cout << "Line 2 - 条件为真" << endl;
    }
    /* 改变 a 和 b 的值 */
    a = 0;
    b = 10;
    if (a && b) {
        cout << "Line 3 - 条件为真" << endl;
    } else {
        cout << "Line 4 - 条件不为真" << endl;
    }
    if (!(a && b)) {
        cout << "Line 5 - 条件为真" << endl;
    }  
}

```

输出:

> Line 1 - 条件为真
> Line 2 - 条件为真
> Line 4 - 条件不为真
> Line 5 - 条件为真

**位运算符:**

位运算符作用于位，并逐位执行操作。&、 | 和 ^ 的真值表如下所示：

| p    | q    | p & q | p \| q | p ^ q |
| :--- | :--- | :---- | :----- | :---- |
| 0    | 0    | 0     | 0      | 0     |
| 0    | 1    | 0     | 1      | 1     |
| 1    | 1    | 1     | 1      | 0     |
| 1    | 0    | 0     | 1      | 1     |

假设如果 A = 60，且 B = 13，现在以二进制格式表示，它们如下所示：

A = 0011 1100

B = 0000 1101

\-----------------

A&B = 0000 1100

A|B = 0011 1101

A^B = 0011 0001

~A  = 1100 0011

下表显示了 C++ 支持的位运算符。假设变量 A 的值为 60，变量 B 的值为 13，则：

| 运算符 | 描述                                                         | 实例                                                         |
| :----- | :----------------------------------------------------------- | :----------------------------------------------------------- |
| &      | 如果同时存在于两个操作数中，二进制 AND 运算符复制一位到结果中。 | (A & B) 将得到 12，即为 0000 1100                            |
| \|     | 如果存在于任一操作数中，二进制 OR 运算符复制一位到结果中。   | (A \| B) 将得到 61，即为 0011 1101                           |
| ^      | 如果存在于其中一个操作数中但不同时存在于两个操作数中，二进制异或运算符复制一位到结果中。 | (A ^ B) 将得到 49，即为 0011 0001                            |
| ~      | 二进制补码运算符是一元运算符，具有"翻转"位效果，即0变成1，1变成0。 | (~A ) 将得到 -61，即为 1100 0011，一个有符号二进制数的补码形式。 |
| <<     | 二进制左移运算符。左操作数的值向左移动右操作数指定的位数。   | A << 2 将得到 240，即为 1111 0000                            |
| >>     | 二进制右移运算符。左操作数的值向右移动右操作数指定的位数。   | A >> 2 将得到 15，即为 0000 1111                             |

```c++
void test8() {

    println("\n\n\n", "位运算符");
    //位运算符
    unsigned int aW = 60;      // 60 = 0011 1100
    unsigned int bW = 13;      // 13 = 0000 1101
    int cW = 0;

    cW = aW & bW;             // 12 = 0000 1100
    cout << "Line 1 - cW 的值是 " << cW << endl;

    cW = aW | bW;             // 61 = 0011 1101
    cout << "Line 2 - cW 的值是 " << cW << endl;

    cW = aW ^ bW;             // 49 = 0011 0001
    cout << "Line 3 - cW 的值是 " << cW << endl;

    cW = ~aW;                // -61 = 1100 0011
    cout << "Line 4 - cW 的值是 " << cW << endl;

    cW = aW << 2;            // 240 = 1111 0000
    cout << "Line 5 - cW 的值是 " << cW << endl;

    cW = aW >> 2;            // 15 = 0000 1111
    cout << "Line 6 - cW 的值是 " << cW << endl;
}

```

输出:

> Line 1 - cW 的值是 12
> Line 2 - cW 的值是 61
> Line 3 - cW 的值是 49
> Line 4 - cW 的值是 -61
> Line 5 - cW 的值是 240
> Line 6 - cW 的值是 15

**赋值运算符:**

| 运算符 | 描述                                                         | 实例                            |
| :----- | :----------------------------------------------------------- | :------------------------------ |
| =      | 简单的赋值运算符，把右边操作数的值赋给左边操作数             | C = A + B 将把 A + B 的值赋给 C |
| +=     | 加且赋值运算符，把右边操作数加上左边操作数的结果赋值给左边操作数 | C += A 相当于 C = C + A         |
| -=     | 减且赋值运算符，把左边操作数减去右边操作数的结果赋值给左边操作数 | C -= A 相当于 C = C - A         |
| *=     | 乘且赋值运算符，把右边操作数乘以左边操作数的结果赋值给左边操作数 | C *= A 相当于 C = C * A         |
| /=     | 除且赋值运算符，把左边操作数除以右边操作数的结果赋值给左边操作数 | C /= A 相当于 C = C / A         |
| %=     | 求模且赋值运算符，求两个操作数的模赋值给左边操作数           | C %= A 相当于 C = C % A         |
| <<=    | 左移且赋值运算符                                             | C <<= 2 等同于 C = C << 2       |
| >>=    | 右移且赋值运算符                                             | C >>= 2 等同于 C = C >> 2       |
| &=     | 按位与且赋值运算符                                           | C &= 2 等同于 C = C & 2         |
| ^=     | 按位异或且赋值运算符                                         | C ^= 2 等同于 C = C ^ 2         |
| \|=    | 按位或且赋值运算符                                           | C \|= 2 等同于 C = C \| 2       |

```c++
void test8() {
    println("\n\n\n", "赋值运算符");
    a = 50;
    //赋值运算符
    c = a;
    cout << "Line 1 - =  运算符实例，c 的值 = : " << c << endl;

    c += a;
    cout << "Line 2 - += 运算符实例，c 的值 = : " << c << endl;

    c -= a;
    cout << "Line 3 - -= 运算符实例，c 的值 = : " << c << endl;

    c *= a;
    cout << "Line 4 - *= 运算符实例，c 的值 = : " << c << endl;

    c /= a;
    cout << "Line 5 - /= 运算符实例，c 的值 = : " << c << endl;

    c = 200;
    c %= a;
    cout << "Line 6 - %= 运算符实例，c 的值 = : " << c << endl;

    c <<= 2;
    cout << "Line 7 - <<= 运算符实例，c 的值 = : " << c << endl;

    c >>= 2;
    cout << "Line 8 - >>= 运算符实例，c 的值 = : " << c << endl;

    c &= 2;
    cout << "Line 9 - &= 运算符实例，c 的值 = : " << c << endl;

    c ^= 2;
    cout << "Line 10 - ^= 运算符实例，c 的值 = : " << c << endl;

    c |= 2;
    cout << "Line 11 - |= 运算符实例，c 的值 = : " << c << endl;
}

```

> 输出:
>
> Line 1 - =  运算符实例，c 的值 = : 50
> Line 2 - += 运算符实例，c 的值 = : 100
> Line 3 - -= 运算符实例，c 的值 = : 50
> Line 4 - *= 运算符实例，c 的值 = : 2500
> Line 5 - /= 运算符实例，c 的值 = : 50
> Line 6 - %= 运算符实例，c 的值 = : 0
> Line 7 - <<= 运算符实例，c 的值 = : 0
> Line 8 - >>= 运算符实例，c 的值 = : 0
> Line 9 - &= 运算符实例，c 的值 = : 0
> Line 10 - ^= 运算符实例，c 的值 = : 2
> Line 11 - |= 运算符实例，c 的值 = : 2

**其它:**

| 运算符               | 描述                                                         |
| :------------------- | :----------------------------------------------------------- |
| sizeof               | [sizeof 运算符](https://www.runoob.com/cplusplus/cpp-sizeof-operator.html)返回变量的大小。例如，sizeof(a) 将返回 4，其中 a 是整数。 |
| Condition ? X : Y    | [条件运算符](https://www.runoob.com/cplusplus/cpp-conditional-operator.html)。如果 Condition 为真 ? 则值为 X : 否则值为 Y。 |
| ,                    | [逗号运算符](https://www.runoob.com/cplusplus/cpp-comma-operator.html)会顺序执行一系列运算。整个逗号表达式的值是以逗号分隔的列表中的最后一个表达式的值。 |
| .（点）和 ->（箭头） | [成员运算符](https://www.runoob.com/cplusplus/cpp-member-operators.html)用于引用类、结构和共用体的成员。 |
| Cast                 | [强制转换运算符](https://www.runoob.com/cplusplus/cpp-casting-operators.html)把一种数据类型转换为另一种数据类型。例如，int(2.2000) 将返回 2。 |
| &                    | [指针运算符 &](https://www.runoob.com/cplusplus/cpp-pointer-operators.html) 返回变量的地址。例如 &a; 将给出变量的实际地址。 |
| *                    | [指针运算符 *](https://www.runoob.com/cplusplus/cpp-pointer-operators.html) 指向一个变量。例如，*var; 将指向变量 var。 |

### 11. 循环

C++ 编程语言提供了以下几种循环类型。点击链接查看每个类型的细节。

| 循环类型                                                     | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [while 循环](https://www.runoob.com/cplusplus/cpp-while-loop.html) | 当给定条件为真时，重复语句或语句组。它会在执行循环主体之前测试条件。 |
| [for 循环](https://www.runoob.com/cplusplus/cpp-for-loop.html) | 多次执行一个语句序列，简化管理循环变量的代码。               |
| [do...while 循环](https://www.runoob.com/cplusplus/cpp-do-while-loop.html) | 除了它是在循环主体结尾测试条件外，其他与 while 语句类似。    |
| [嵌套循环](https://www.runoob.com/cplusplus/cpp-nested-loops.html) | 您可以在 while、for 或 do..while 循环内使用一个或多个循环。  |

**循环控制语句:**

循环控制语句更改执行的正常序列。当执行离开一个范围时，所有在该范围中创建的自动对象都会被销毁。

C++ 提供了下列的控制语句。点击链接查看每个语句的细节。

| 控制语句                                                     | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [break 语句](https://www.runoob.com/cplusplus/cpp-break-statement.html) | 终止 **loop** 或 **switch** 语句，程序流将继续执行紧接着 loop 或 switch 的下一条语句。 |
| [continue 语句](https://www.runoob.com/cplusplus/cpp-continue-statement.html) | 引起循环跳过主体的剩余部分，立即重新开始测试条件。           |
| [goto 语句](https://www.runoob.com/cplusplus/cpp-goto-statement.html) | 将控制转移到被标记的语句。但是不建议在程序中使用 goto 语句。 |

**死循环:**

如果条件永远不为假，则循环将变成无限循环。**for** 循环在传统意义上可用于实现无限循环。由于构成循环的三个表达式中任何一个都不是必需的，您可以将某些条件表达式留空来构成一个无限循环。

```c++
#include <iostream>
using namespace std;
 
int main ()
{
 	//也可以使用  while (true){}
   for( ; ; )
   {
      printf("This loop will run forever.\n");
   }
 
   return 0;
}

```

当条件表达式不存在时，它被假设为真。您也可以设置一个初始值和增量表达式，但是一般情况下，C++ 程序员偏向于使用 for(;;) 结构来表示一个无限循环。

**注意：**您可以按 Ctrl + C 键终止一个无限循环。

**例子:**

```c++
void test9() {

    //for 循环
    for (int i = 0; i < 10; ++i) {
        if (i % 2 == 1) {
            cout << i << "==" << i % 2 << endl;
            //跳出当前循环，继续下一次操作
            continue;
        }
        if (i == 8) {
            cout << "跳出循环" << endl;
            break;
        }
        cout << "遍历中..." << "==" << i << endl;
    }

    for (int j = 0; j < 3; ++j) {
        if (j == 1) {
            cout << "j 跳出循环" << endl;
            return;
        }
        cout << "j 就遍历中..." << "==" << j << endl;
    }


};

```

> **输出:**
>
> 遍历中...==0
> 1==1
> 遍历中...==2
> 3==1
> 遍历中...==4
> 5==1
> 遍历中...==6
> 7==1
> 跳出循环
> j 就遍历中...==0
> j 跳出循环

### 12. 判断

**判断语句:**

C++ 编程语言提供了以下类型的判断语句。点击链接查看每个语句的细节。

| 语句                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [if 语句](https://www.runoob.com/cplusplus/cpp-if.html)      | 一个 **if 语句** 由一个布尔表达式后跟一个或多个语句组成。    |
| [if...else 语句](https://www.runoob.com/cplusplus/cpp-if-else.html) | 一个 **if 语句** 后可跟一个可选的 **else 语句**，else 语句在布尔表达式为假时执行。 |
| [嵌套 if 语句](https://www.runoob.com/cplusplus/cpp-nested-if.html) | 您可以在一个 **if** 或 **else if** 语句内使用另一个 **if** 或 **else if** 语句。 |
| [switch 语句](https://www.runoob.com/cplusplus/cpp-switch.html) | 一个 **switch** 语句允许测试一个变量等于多个值时的情况。     |
| [嵌套 switch 语句](https://www.runoob.com/cplusplus/cpp-nested-switch.html) | 您可以在一个 **switch** 语句内使用另一个 **switch** 语句。   |

**三元运算符:**

我们已经在前面的章节中讲解了 [**条件运算符 ? :**](https://www.runoob.com/cplusplus/cpp-conditional-operator.html)，可以用来替代 **if...else** 语句。它的一般形式如下：

```c++
void test10() {
    int i = 10;
		//格式：Exp1 ? Exp2 : Exp3;
  	//其中，Exp1、Exp2 和 Exp3 是表达式。请注意，冒号的使用和位置。
		//? 表达式的值是由 Exp1 决定的。如果 Exp1 为真，则计算 Exp2 的值，结果即为整个 ? 表达式的			//值。如果 Exp1 为假，则计算 Exp3 的值，结果即为整个 ? 表达式的值。
    i = i == 10 ? i = 9 : i;
    cout << i << endl;
}

```

> **输出:**
>
> 9

### 13. 函数

函数是一组一起执行一个任务的语句。每个 C++ 程序都至少有一个函数，即主函数 **main()** ，所有简单的程序都可以定义其他额外的函数。

**定义函数:**

```c++
return_type function_name( parameter list )
{
   body of the function
}

```

在 C++ 中，函数由一个函数头和一个函数主体组成。下面列出一个函数的所有组成部分：

- **返回类型：**一个函数可以返回一个值。**return_type** 是函数返回的值的数据类型。有些函数执行所需的操作而不返回值，在这种情况下，return_type 是关键字 **void**。
- **函数名称：**这是函数的实际名称。函数名和参数列表一起构成了函数签名。
- **参数：**参数就像是占位符。当函数被调用时，您向参数传递一个值，这个值被称为实际参数。参数列表包括函数参数的类型、顺序、数量。参数是可选的，也就是说，函数可能不包含参数。
- **函数主体：**函数主体包含一组定义函数执行任务的语句。

例子:

```c++
// 函数返回两个数中较大的那个数
int max(int num1, int num2) 
{
   // 局部变量声明
   int result;
 
   if (num1 > num2)
      result = num1;
   else
      result = num2;
 
   return result; 
}

```

**函数声明:**

```c++
//格式: return_type function_name( parameter list );
//例子:
int max(int num1, int num2);
int max(int, int);

```

当您在一个源文件中定义函数且在另一个文件中调用函数时，函数声明是必需的。在这种情况下，您应该在调用函数的文件顶部声明函数。

**调用函数:**

创建 C++ 函数时，会定义函数做什么，然后通过调用函数来完成已定义的任务。

当程序调用函数时，程序控制权会转移给被调用的函数。被调用的函数执行已定义的任务，当函数的返回语句被执行时，或到达函数的结束括号时，会把程序控制权交还给主程序。

调用函数时，传递所需参数，如果函数返回一个值，则可以存储返回值。例如：

```c++
#include <iostream>
using namespace std;
 
// 函数声明
int max(int num1, int num2);
 
int main ()
{
   // 局部变量声明
   int a = 100;
   int b = 200;
   int ret;
 
   // 调用函数来获取最大值
   ret = max(a, b);
 
   cout << "Max value is : " << ret << endl;
 
   return 0;
}
 
// 函数返回两个数中较大的那个数
int max(int num1, int num2) 
{
   // 局部变量声明
   int result;
 
   if (num1 > num2)
      result = num1;
   else
      result = num2;
 
   return result; 
}

```

> **输出:**
>
> Max value is : 200

**函数参数:**

如果函数要使用参数，则必须声明接受参数值的变量。这些变量称为函数的**形式参数**。

形式参数就像函数内的其他局部变量，在进入函数时被创建，退出函数时被销毁。

当调用函数时，有三种向函数传递参数的方式：

| 调用类型                                                     | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [传值调用](https://www.runoob.com/cplusplus/cpp-function-call-by-value.html) | 该方法把参数的实际值复制给函数的形式参数。在这种情况下，修改函数内的形式参数对实际参数没有影响。 |
| [指针调用](https://www.runoob.com/cplusplus/cpp-function-call-by-pointer.html) | 该方法把参数的地址复制给形式参数。在函数内，该地址用于访问调用中要用到的实际参数。这意味着，修改形式参数会影响实际参数。 |
| [引用调用](https://www.runoob.com/cplusplus/cpp-function-call-by-reference.html) | 该方法把参数的引用复制给形式参数。在函数内，该引用用于访问调用中要用到的实际参数。这意味着，修改形式参数会影响实际参数。 |

默认情况下，C++ 使用**传值调用**来传递参数。一般来说，这意味着函数内的代码不能改变用于调用函数的参数。之前提到的实例，调用 max() 函数时，使用了相同的方法。

**参数的默认值:**

当您定义一个函数，您可以为参数列表中后边的每一个参数指定默认值。当调用函数时，如果实际参数的值留空，则使用这个默认值。

这是通过在函数定义中使用赋值运算符来为参数赋值的。调用函数时，如果未传递参数的值，则会使用默认值，如果指定了值，则会忽略默认值，使用传递的值。请看下面的实例：

```c++
#include <iostream>
using namespace std;
 
int sum(int a, int b=20)
{
  int result;
 
  result = a + b;
  
  return (result);
}
 
int main ()
{
   // 局部变量声明
   int a = 100;
   int b = 200;
   int result;
 
   // 调用函数来添加值
   result = sum(a, b);
   cout << "Total value is :" << result << endl;
 
   // 再次调用函数
   result = sum(a);
   cout << "Total value is :" << result << endl;
 
   return 0;
}

```

> **输出:**
>
> Total value is :300
> Total value is :120

### 14. 数学运算

在 C++ 中，除了可以创建各种函数，还包含了各种有用的函数供您使用。这些函数写在标准 C 和 C++ 库中，叫做**内置**函数。您可以在程序中引用这些函数。

C++ 内置了丰富的数学函数，可对各种数字进行运算。下表列出了 C++ 中一些有用的内置的数学函数。

为了利用这些函数，您需要引用数学头文件 **<cmath>**。

| 序号 | 函数 & 描述                                                  |
| :--- | :----------------------------------------------------------- |
| 1    | **double cos(double);** 该函数返回弧度角（double 型）的余弦。 |
| 2    | **double sin(double);** 该函数返回弧度角（double 型）的正弦。 |
| 3    | **double tan(double);** 该函数返回弧度角（double 型）的正切。 |
| 4    | **double log(double);** 该函数返回参数的自然对数。           |
| 5    | **double pow(double, double);** 假设第一个参数为 x，第二个参数为 y，则该函数返回 x 的 y 次方。 |
| 6    | **double hypot(double, double);** 该函数返回两个参数的平方总和的平方根，也就是说，参数为一个直角三角形的两个直角边，函数会返回斜边的长度。 |
| 7    | **double sqrt(double);** 该函数返回参数的平方根。            |
| 8    | **int abs(int);** 该函数返回整数的绝对值。                   |
| 9    | **double fabs(double);** 该函数返回任意一个浮点数的绝对值。  |
| 10   | **double floor(double);** 该函数返回一个小于或等于传入参数的最大整数。 |

下面是一个关于数学运算的简单实例：

```c++
void test11() {
    //数字定义
    short s = 10;
    int i = -1000;
    long l = 100000;
    float f = 250.41;
    double d = 200.45;

    //数学运算
    cout << "sin(d) :" << sin(d) << endl;
    cout << "abs(i)  :" << abs(i) << endl;
    cout << "floor(d) :" << floor(d) << endl;
    cout << "sqrt(f) :" << sqrt(f) << endl;
    cout << "pow( d, 2) :" << pow(d, 2) << endl;

    //生成随机数之前必须先调用 srand() 函数。
    int a;
    srand((unsigned) time(NULL));
    //生成 5 个随机数
    for (int j = 0; j < 5; ++j) {
        a = rand();
        cout << "随机数：" << a << endl;
    }
}

```

> **输出:**
>
> sin(d) :-0.574448
> abs(i)  :1000
> floor(d) :200
> sqrt(f) :15.8243
> pow( d, 2) :40180.2
> 随机数：1753472662
> 随机数：696942453
> 随机数：1135996833
> 随机数：1569150401
> 随机数：1611604447

### 15. 数组

C++ 支持**数组**数据结构，它可以存储一个固定大小的相同类型元素的顺序集合。

**声明数组:**

在 C++ 中要声明一个数组，需要指定元素的类型和元素的数量，如下所示：

```c++
//格式:
type arrayName [ arraySize ];//这叫做一维数组。arraySize 必须是一个大于零的整数常量，type 可以是任意有效的 C++ 数据类型。
//例子:
double balance[10];

```

**初始化数组:**

在 C++ 中，您可以逐个初始化数组，也可以使用一个初始化语句，如下所示：

```c++
double d[5] = {1.0, 2.0, 3.0, 4.0, 5.0};
//修改数组
d[4] = 50.0;

```

上面的意思是先定义一个大小为 5 的数组，然后在修改索引为 4 的数值，以下是上面的图形表示:

![](https://devyk.oss-cn-qingdao.aliyuncs.com/blog/20200105213603.png)

**访问数组元素:**

数组元素可以通过数组名称加索引进行访问。元素的索引是放在方括号内，跟在数组名称的后边。例如：

```c++
double temp = d[4];

```

上面的语句将把数组中第 4 个元素的值赋给 temp 变量。下面的实例使用了上述的三个概念，即，声明数组、数组赋值、访问数组：

```c++
void test12() {
    int n[100]; //包含 100 个整数
    for (int i = 0; i < 100; ++i) {
        n[i] = i;
    }
    //setw 可以理解为 输出的间隔为 10 个字符
    cout << "Element" << setw(10) << "value" << setw(10) << n[20] << endl;

    // 输出数组中每个元素的值
    for (int j = 0; j < 100; j++) {
        cout << "Element" << setw(10) << "value" << setw(10) << n[j] << endl;
    }
}

```

> **输出:**
>
> Element     value        20
> Element     value         0
> Element     value         1
> Element     value         2
> Element     value         3
> Element     value         4
> Element     value         5
> Element     value         6
> Element     value         7
> Element     value         8
> Element     value         9
> Element     value        10
> Element     value        11
> Element     value        12
>
> ...

**其它:**

在 C++ 中，数组是非常重要的，我们需要了解更多有关数组的细节。下面列出了 C++ 程序员必须清楚的一些与数组相关的重要概念：

| 概念                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [多维数组](https://www.runoob.com/cplusplus/cpp-multi-dimensional-arrays.html) | C++ 支持多维数组。多维数组最简单的形式是二维数组。           |
| [指向数组的指针](https://www.runoob.com/cplusplus/cpp-pointer-to-an-array.html) | 您可以通过指定不带索引的数组名称来生成一个指向数组中第一个元素的指针。 |
| [传递数组给函数](https://www.runoob.com/cplusplus/cpp-passing-arrays-to-functions.html) | 您可以通过指定不带索引的数组名称来给函数传递一个指向数组的指针。 |
| [从函数返回数组](https://www.runoob.com/cplusplus/cpp-return-arrays-from-function.html) | C++ 允许从函数返回数组。                                     |

### 16. 字符串

C++ 提供了以下两种类型的字符串表示形式：

- C 风格字符串
- C++ 引入的 string 类类型

**C 风格字符串:**

在上一篇文章中我们学习了 C 中定义字符串，这里我们在复习下，看下面示例:

```c
char greeting[6] = {'H', 'e', 'l', 'l', 'o', '\0'};
//等同于如下定义
char greeting[] = "Hello";

```

以下是 C/C++ 中定义的字符串的内存表示：

其实，您不需要把 *null* 字符放在字符串常量的末尾。C++ 编译器会在初始化数组时，自动把 '\0' 放在字符串的末尾。让我们尝试输出上面的字符串：![](https://devyk.oss-cn-qingdao.aliyuncs.com/blog/20200105214650.png)

其实，您不需要把 *null* 字符放在字符串常量的末尾。C++ 编译器会在初始化数组时，自动把 '\0' 放在字符串的末尾。

例子:

```c++
void test13() {
    char message[10] = {'1', '2', '3', '4', '5', '6', '7', '8', '9', '\0'};
    cout << message << endl;
}

```

> **输出:**
>
> 123456789

C++ 中有大量的函数用来操作以 null 结尾的字符串：supports a wide range of functions that manipulate null-terminated strings:

| 序号 | 函数 & 目的                                                  |
| :--- | :----------------------------------------------------------- |
| 1    | **strcpy(s1, s2);** 复制字符串 s2 到字符串 s1。              |
| 2    | **strcat(s1, s2);** 连接字符串 s2 到字符串 s1 的末尾。       |
| 3    | **strlen(s1);** 返回字符串 s1 的长度。                       |
| 4    | **strcmp(s1, s2);** 如果 s1 和 s2 是相同的，则返回 0；如果 s1<s2 则返回值小于 0；如果 s1>s2 则返回值大于 0。 |
| 5    | **strchr(s1, ch);** 返回一个指针，指向字符串 s1 中字符 ch 的第一次出现的位置。 |
| 6    | **strstr(s1, s2);** 返回一个指针，指向字符串 s1 中字符串 s2 的第一次出现的位置。 |

下面的实例使用了上述的一些函数：

```c++
void test13() {
    char ctr1[20] = "网名:";
    char ctr2[50] = "个人Blog地址:";

    int ctr1Len, ctr2Len;

    strcat(ctr1, "DevYK");
    strcat(ctr2, "https://www.devyk.top");
    cout << "ctr1\t" << ctr1 << "\n" << "ctr2\t" << ctr2 << endl;
    ctr1Len = strlen(ctr1);
    ctr2Len = strlen(ctr2);
    cout << "ctr1Len" << setw(10) << ctr1Len << "\nctr2Len" << setw(10) << ctr2Len << endl;

}

```

> **输出:**
>
> ctr1	网名:DevYK
> ctr2	个人Blog地址:https://www.devyk.top
> ctr1Len        12
> ctr2Len        38

**C++ 中的 String:**

C++ 标准库提供了 **string** 类类型，支持上述所有的操作，另外还增加了其他更多的功能。我们将学习 C++ 标准库中的这个类，现在让我们先来看看下面这个实例：

现在您可能还无法透彻地理解这个实例，因为到目前为止我们还没有讨论类和对象。所以现在您可以只是粗略地看下这个实例，等理解了面向对象的概念之后再回头来理解这个实例。

```c++
#include <iostream>
#include <string>
int main(){
  test13();
  return 0;
}
void test13() {
    printf("\n\n\nstring 类型字符串");

    string meg[10] = {"1", "2", "3", "4", "5", "6", "7", "8", "9"};
    cout << meg << endl;
    //定义 string 变量
    string str1add, str2add;
    int str1Len, str2Len;

    //init
    string str1 = "网名:";
    string str2 = "个人Blog地址:";

    //追加到 str 末尾
    str1add = str1.append("DevYK");
    str2add = str2.append("https://www.devyk.top");

    cout << "str1\t" << str1 << "\n" << "str2\t" << str2 << endl;
    str1Len = str1add.length();
    str2Len = str2add.size();
    cout << "str1Len" << setw(10) << str1Len << "\nstr2Len" << setw(10) << str2Len << endl;


}

```

> **输出:**
>
> string 类型字符串0x7ffee9b98550
> str1	网名:DevYK
> str2	个人Blog地址:https://www.devyk.top
> str1Len        12
> str2Len        38

### 17. 指针

学习 C++ 的指针既简单又有趣。通过指针，可以简化一些 C++ 编程任务的执行，还有一些任务，如动态内存分配，没有指针是无法执行的。所以，想要成为一名优秀的 C++ 程序员，学习指针是很有必要的。

正如您所知道的，每一个变量都有一个内存位置，每一个内存位置都定义了可使用连字号（&）运算符访问的地址，它表示了在内存中的一个地址。请看下面的实例，它将输出定义的变量地址：

```c++
void test14() {
    int var1;
    char var2[10];
    cout << "var1 变量的地址\t" << &var1 << "\nvar2 变量的地址\t" << &var2 << endl;
}

```

> **输出:**
>
> var1 变量的地址	0x7ffeeef58698
> var2 变量的地址	0x7ffeeef5869e

通过上面的实例，我们了解了什么是内存地址以及如何访问它。接下来让我们看看什么是指针。

**指针是什么？**

**指针**是一个变量，其值为另一个变量的地址，即，内存位置的直接地址。就像其他变量或常量一样，您必须在使用指针存储其他变量地址之前，对其进行声明。指针变量声明的一般形式为：

```c++
type *var-name;


```

在这里，**type** 是指针的基类型，它必须是一个有效的 C++ 数据类型，**var-name** 是指针变量的名称。用来声明指针的星号 * 与乘法中使用的星号是相同的。但是，在这个语句中，星号是用来指定一个变量是指针。以下是有效的指针声明：

```c++
int    *ip;    /* 一个整型的指针 */
double *dp;    /* 一个 double 型的指针 */
float  *fp;    /* 一个浮点型的指针 */
char   *ch;    /* 一个字符型的指针 */

```

所有指针的值的实际数据类型，不管是整型、浮点型、字符型，还是其他的数据类型，都是一样的，都是一个代表内存地址的长的十六进制数。不同数据类型的指针之间唯一的不同是，指针所指向的变量或常量的数据类型不同。

**指针的使用:**

使用指针时会频繁进行以下几个操作：定义一个指针变量、把变量地址赋值给指针、访问指针变量中可用地址的值。这些是通过使用一元运算符 ***** 来返回位于操作数所指定地址的变量的值。下面的实例涉及到了这些操作：

```c++
void test14() {
    int var = 20; //实际变量的声明
    int *ip;
    //将 var 地址赋值给 ip 指针变量中
    ip = &var;

    cout << "指针变量中存储的地址\t" << ip << endl;
    cout << "指针变量中的地址\t" << ip << endl;
    cout << "指针变量中地址对应的值\t" << *ip << endl;
}

```

> **输出:**
>
> 指针变量中存储的地址	0x7ffeeef58694
> 指针变量中的地址	0x7ffeeef58694
> 指针变量中地址对应的值	20

### 18. 引用

引用变量是一个别名，也就是说，它是某个已存在变量的另一个名字。一旦把引用初始化为某个变量，就可以使用该引用名称或变量名称来指向变量。

**引用 VS 指针:**

引用很容易与指针混淆，它们之间有三个主要的不同：

- 不存在空引用。引用必须连接到一块合法的内存。
- 一旦引用被初始化为一个对象，就不能被指向到另一个对象。指针可以在任何时候指向到另一个对象。
- 引用必须在创建时被初始化。指针可以在任何时间被初始化。

**创建引用:**

```c++
int i = 17;

```

我们可以为 i 声明引用变量，如下所示:

```c++
int&  r = i;
double& s = d;

```

在这些声明中，& 读作**引用**。因此，第一个声明可以读作 "r 是一个初始化为 i 的整型引用"，第二个声明可以读作 "s 是一个初始化为 d 的 double 型引用"。下面的实例使用了 int 和 double 引用：

```c++
void test15() {
    //声明变量
    int a = 10, b = 20;
    //声明引用变量
    int &i = a;
    int &j = b;

    cout << "a == " << a << "\t &i ==" << i << endl;

    cout << "b == " << b << "\t &j ==" << j << endl;

    a = 5, b = 6;
    cout << "a == " << a << "\t &i ==" << i << endl;

    cout << "b == " << b << "\t &j ==" << j << endl;

}

```

> **输出:**
>
> a == 10	 &i ==10
> b == 20	 &j ==20
> a == 5	   &i ==5
> b == 6	   &j ==6

引用通常用于函数参数列表和函数返回值。下面列出了 C++ 程序员必须清楚的两个与 C++ 引用相关的重要概念：

| 概念                                                         | 描述                                                     |
| :----------------------------------------------------------- | :------------------------------------------------------- |
| [把引用作为参数](https://www.runoob.com/cplusplus/passing-parameters-by-references.html) | C++ 支持把引用作为参数传给函数，这比传一般的参数更安全。 |
| [把引用作为返回值](https://www.runoob.com/cplusplus/returning-values-by-reference.html) | 可以从 C++ 函数中返回引用，就像返回其他数据类型一样。    |

### 19. 日期 & 时间

C++ 标准库没有提供所谓的日期类型。C++ 继承了 C 语言用于日期和时间操作的结构和函数。为了使用日期和时间相关的函数和结构，需要在 C++ 程序中引用 <ctime> 头文件。

有四个与时间相关的类型：**clock_t、time_t、size_t** 和 **tm**。类型 clock_t、size_t 和 time_t 能够把系统时间和日期表示为某种整数。

结构类型 **tm** 把日期和时间以 C 结构的形式保存，tm 结构的定义如下：

```c++
struct tm {
  int tm_sec;   // 秒，正常范围从 0 到 59，但允许至 61
  int tm_min;   // 分，范围从 0 到 59
  int tm_hour;  // 小时，范围从 0 到 23
  int tm_mday;  // 一月中的第几天，范围从 1 到 31
  int tm_mon;   // 月，范围从 0 到 11
  int tm_year;  // 自 1900 年起的年数
  int tm_wday;  // 一周中的第几天，范围从 0 到 6，从星期日算起
  int tm_yday;  // 一年中的第几天，范围从 0 到 365，从 1 月 1 日算起
  int tm_isdst; // 夏令时
}

```

下面是 C/C++ 中关于日期和时间的重要函数。所有这些函数都是 C/C++ 标准库的组成部分，您可以在 C++ 标准库中查看一下各个函数的细节。

| 序号 | 函数 & 描述                                                  |
| :--- | :----------------------------------------------------------- |
| 1    | [**time_t time(time_t \*time);**](https://www.runoob.com/cplusplus/c-function-time.html) 该函数返回系统的当前日历时间，自 1970 年 1 月 1 日以来经过的秒数。如果系统没有时间，则返回 .1。 |
| 2    | [**char \*ctime(const time_t \*time);**](https://www.runoob.com/cplusplus/c-function-ctime.html) 该返回一个表示当地时间的字符串指针，字符串形式 *day month year hours:minutes:seconds year\n\0*。 |
| 3    | [**struct tm \*localtime(const time_t \*time);**](https://www.runoob.com/cplusplus/c-function-localtime.html) 该函数返回一个指向表示本地时间的 **tm** 结构的指针。 |
| 4    | [**clock_t clock(void);**](https://www.runoob.com/cplusplus/c-function-clock.html) 该函数返回程序执行起（一般为程序的开头），处理器时钟所使用的时间。如果时间不可用，则返回 .1。 |
| 5    | [**char \* asctime ( const struct tm \* time );**](https://www.runoob.com/cplusplus/c-function-asctime.html) 该函数返回一个指向字符串的指针，字符串包含了 time 所指向结构中存储的信息，返回形式为：day month date hours:minutes:seconds year\n\0。 |
| 6    | [**struct tm \*gmtime(const time_t \*time);**](https://www.runoob.com/cplusplus/c-function-gmtime.html) 该函数返回一个指向 time 的指针，time 为 tm 结构，用协调世界时（UTC）也被称为格林尼治标准时间（GMT）表示。 |
| 7    | [**time_t mktime(struct tm \*time);**](https://www.runoob.com/cplusplus/c-function-mktime.html) 该函数返回日历时间，相当于 time 所指向结构中存储的时间。 |
| 8    | [**double difftime ( time_t time2, time_t time1 );**](https://www.runoob.com/cplusplus/c-function-difftime.html) 该函数返回 time1 和 time2 之间相差的秒数。 |
| 9    | [**size_t strftime();**](https://www.runoob.com/cplusplus/c-function-strftime.html) 该函数可用于格式化日期和时间为指定的格式。 |

**当前日期:**

```c++
void test16() {
    //获取系统的时间
    time_t now = time(0);
    //把 now 转为字符串
    char *curTime = ctime(&now);

    //把 now 转为 tm 结构
    tm *gmtm = gmtime(&now);
    cout << "当前时间\t" << curTime << endl;

    curTime = asctime(gmtm);

    cout << "UTC 日期和时间\t" << curTime << endl;

}

```

> **输出:**
>
> 当前时间					Sun Jan  5 22:11:15 2020
>
> UTC 日期和时间		Sun Jan  5 14:11:15 2020

**使用结构 tm 格式化时间:**

**tm** 结构在 C/C++ 中处理日期和时间相关的操作时，显得尤为重要。tm 结构以 C 结构的形式保存日期和时间。大多数与时间相关的函数都使用了 tm 结构。下面的实例使用了 tm 结构和各种与日期和时间相关的函数。

在练习使用结构之前，需要对 C 结构有基本的了解，并懂得如何使用箭头 -> 运算符来访问结构成员。

```c++
void test16() {
    //基于当前系统的日期/时间
    cout << "1970 到目前经过的秒数:" << now << endl;

    tm *ltm = localtime(&now);
    //输出 tm 结构的各个组成部分
    cout << "年: " << 1990 + ltm->tm_year << endl;
    cout << "月: " << 1 + ltm->tm_mon << endl;
    cout << "日: " << ltm->tm_mday << endl;
    cout << "时: " << ltm->tm_hour << endl;
    cout << "分: " << ltm->tm_min << endl;
    cout << "秒: " << ltm->tm_sec << endl;
}


```

> **输出:**
>
> 1970 到目前经过的秒数:1578233475
> 年: 2110
> 月: 1
> 日: 5
> 时: 22
> 分: 11
> 秒: 15

### 20. 输入输出

C++ 标准库提供了一组丰富的输入/输出功能，我们将在后续的章节进行介绍。本章将讨论 C++ 编程中最基本和最常见的 I/O 操作。

C++ 的 I/O 发生在流中，流是字节序列。如果字节流是从设备（如键盘、磁盘驱动器、网络连接等）流向内存，这叫做**输入操作**。如果字节流是从内存流向设备（如显示屏、打印机、磁盘驱动器、网络连接等），这叫做**输出操作**。

**I/O 库头文件**

下列的头文件在 C++ 编程中很重要。

| 头文件         | 函数和描述                                                   |
| :------------- | :----------------------------------------------------------- |
| **<iostream>** | 该文件定义了 **cin、cout、cerr** 和 **clog** 对象，分别对应于标准输入流、标准输出流、非缓冲标准错误流和缓冲标准错误流。 |
| **<iomanip>**  | 该文件通过所谓的参数化的流操纵器（比如 **setw** 和 **setprecision**），来声明对执行标准化 I/O 有用的服务。 |
| **<fstream>**  | 该文件为用户控制的文件处理声明服务。我们将在文件和流的相关章节讨论它的细节。 |

**标准输入流 cout:**

预定义的对象 **cout** 是 **iostream** 类的一个实例。cout 对象"连接"到标准输出设备，通常是显示屏。**cout** 是与流插入运算符 << 结合使用的。

**标准输入流 cin:**

预定义的对象 **cin** 是 **iostream** 类的一个实例。cin 对象附属到标准输入设备，通常是键盘。**cin** 是与流提取运算符 >> 结合使用的。

**标准错误流 cerr:**

预定义的对象 **cerr** 是 **iostream** 类的一个实例。cerr 对象附属到标准错误设备，通常也是显示屏，但是 **cerr** 对象是非缓冲的，且每个流插入到 cerr 都会立即输出。

**cerr** 也是与流插入运算符 << 结合使用的。

**标准日志流 clog:**

预定义的对象 **clog** 是 **iostream** 类的一个实例。clog 对象附属到标准错误设备，通常也是显示屏，但是 **clog** 对象是缓冲的。这意味着每个流插入到 clog 都会先存储在缓冲在，直到缓冲填满或者缓冲区刷新时才会输出。

**clog** 也是与流插入运算符 << 结合使用的。



例子:

```c++
void test17() {
    //1. 标准输出流 cout
    char str[] = "Hello World";
    cout << "值为:" << str << endl;
    //2.  标准输入流 cin
    char name[10];
    cout << "请输入你的名称: ";
    cin >> name;
    cout << "你的名称是：" << name << endl;
//    请输入你的名称: DevYK
//    你的名称是：DevYK

    //3. 标准错误流 cerr
    char errStr[] = "Read Error";
    cerr << "error message：" << errStr << endl; //输出为报红的:error message：Read Error

    //4. 标准日志流 clog
    char logStr[] = "out Log";
    clog << "Debug Log：" << logStr << endl; // 输出为报红的 Debug Logout Log
}

```

> **输出:**

![](https://devyk.oss-cn-qingdao.aliyuncs.com/blog/20200105222252.gif)

### 21. 数据结构

C/C++ 数组允许定义可存储相同类型数据项的变量，但是**结构**是 C++ 中另一种用户自定义的可用的数据类型，它允许您存储不同类型的数据项。

**定义结构:**

为了定义结构，您必须使用 **struct** 语句。struct 语句定义了一个包含多个成员的新的数据类型，struct 语句的格式如下：

```c++
struct type_name {
member_type1 member_name1;
member_type2 member_name2;
member_type3 member_name3;
.
.
} object_names;

```

**type_name** 是结构体类型的名称，**member_type1 member_name1** 是标准的变量定义，比如 **int i;** 或者 **float f;** 或者其他有效的变量定义。在结构定义的末尾，最后一个分号之前，您可以指定一个或多个结构变量，这是可选的。下面是声明一个结构体类型 **Movies**，变量为 **movies**：

```c++
//定义结构
struct Movies {
    char title[10];
    char address[30];
}movies;

```

**访问结构成员:**

为了访问结构的成员，我们使用**成员访问运算符（.）**。成员访问运算符是结构变量名称和我们要访问的结构成员之间的一个句号。

下面的实例演示了结构的用法：

```c++
//定义结构
struct Movies {
    char title[10];
    char address[30];
};

void test18() {
    //定义结构体变量
    Movies movieA, movieB;

    //movieA 详述
    strcpy(movieA.title, "叶问4");
    strcpy(movieA.address, "china");

    //movieB 详述
    strcpy(movieB.title, "战狼2");
    strcpy(movieB.address, "china");

    //输出电影信息
    cout << movieA.title << "\t" << movieA.address << endl;
    cout << movieB.title << "\t" << movieB.address << endl;

}


```

> **输出:**
>
> 叶问4	china
> 战狼2	china

**结构体作为函数参数:**

您可以把结构作为函数参数，传参方式与其他类型的变量或指针类似。您可以使用上面实例中的方式来访问结构变量：

```c++
//定义结构
struct Movies {
    char title[10];
    char address[30];
};

void movieInfo(struct Movies movie);

void test18() {
    //定义结构体变量
    Movies movieA, movieB;

    //movieA 详述
    strcpy(movieA.title, "叶问4");
    strcpy(movieA.address, "china");

    //movieB 详述
    strcpy(movieB.title, "战狼2");
    strcpy(movieB.address, "china");

    //将结构体作为函数参数传递
    movieInfo(movieA);
    movieInfo(movieB);


}

void movieInfo(struct Movies movie) {
    //输出电影信息
    cout << movie.title << "\t" << movie.address << endl;
}


```

> **输出:**
>
> 叶问4	china
> 战狼2	china

**指针结构的指针:**

您可以定义指向结构的指针，方式与定义指向其他类型变量的指针相似，如下所示：

```c++
struct Movies *struct_pointer;

```

现在，您可以在上述定义的指针变量中存储结构变量的地址。为了查找结构变量的地址，请把 & 运算符放在结构名称的前面，如下所示：

```c++
struct_pointer = &Movies;

```

为了使用指向该结构的指针访问结构的成员，您必须使用 -> 运算符，如下所示：

```c++
struct_pointer->title;

```

让我们使用结构指针来重写上面的实例，这将有助于您理解结构指针的概念：

```c++
//定义结构
struct Movies {
    char title[10];
    char address[30];
}movies;


void movieInfo(struct Movies *movie);

void test18() {
    //定义结构体变量
    Movies movieA, movieB;

    //movieA 详述
    strcpy(movieA.title, "叶问4");
    strcpy(movieA.address, "china");

    //movieB 详述
    strcpy(movieB.title, "战狼2");
    strcpy(movieB.address, "china");


    //将结构体作为指针传递
    movieInfo(&movieA);
    movieInfo(&movieB);

}

void movieInfo(struct Movies *movie) {
    //输出电影信息
    // 为了使用指向该结构的指针访问结构的成员，您必须使用 -> 运算符
    cout << movie->title << "\t" << movie->address << endl;
}


```

> **输出:**
>
> 叶问4	china
> 战狼2	china

### 22. 类 & 对象

C++ 在 C 语言的基础上增加了面向对象编程，C++ 支持面向对象程序设计。类是 C++ 的核心特性，通常被称为用户定义的类型。

类用于指定对象的形式，它包含了数据表示法和用于处理数据的方法。类中的数据和方法称为类的成员。函数在一个类中被称为类的成员。

**类定义:**

定义一个类，本质上是定义一个数据类型的蓝图。这实际上并没有定义任何数据，但它定义了类的名称意味着什么，也就是说，它定义了类的对象包括了什么，以及可以在这个对象上执行哪些操作。

类定义是以关键字 **class** 开头，后跟类的名称。类的主体是包含在一对花括号中。类定义后必须跟着一个分号或一个声明列表。例如，我们创建一个 *.h 文件 使用关键字 **class** 定义 Person 数据类型，如下所示：

```c++
//定义了一个 Person ,跟 Java class 差不多
class Person {
public: //公共的属性
    Person(); //空参

    ~Person(); //Person 销毁执行

    Person(char *name, char *gen, int age); //有参构造

  	//成员变量
    char *name;
    char *gen;
    int age;

  	//函数
    void setName(char *name);

    char *getName();

    void setGen(char *gen);

    char *getGen();

    void setAge(int age);

    int getAge();
};

```

关键字 **public** 确定了类成员的访问属性。在类对象作用域内，公共成员在类的外部是可访问的。您也可以指定类的成员为 **private** 或 **protected**。

**定义 C++ 对象:**

类提供了对象的蓝图，所以基本上，对象是根据类来创建的。声明类的对象，就像声明基本类型的变量一样。下面的语句声明了类 Person的两个对象：

```c++
Person personTemp;//声明 personTemp 类型为 Person

```

**访问数据成员:**

类的对象的公共数据成员可以使用直接成员访问运算符 (.) 来访问。为了更好地理解这些概念，让我们尝试一下下面的实例：

```c++
//1. person.h 文件中定义 Person 对象
//定义了一个 Person ,跟 Java class 差不多
class Person {
public: //公共的属性
    Person();

    ~Person();

    Person(char *name, char *gen, int age);

    char *name;
    char *gen;
    int age;

    void setName(char *name);

    char *getName();

    void setGen(char *gen);

    char *getGen();

    void setAge(int age);

    int getAge();

};

//2. person.cpp 

Person::Person(char *name, char *gen, int age) {
    this->name = name;
    this->age = age;
    this->gen = gen;
}

Person::~Person() {
    cout << "Person 销毁" << endl;
}

Person::Person() {
    cout << "执行 Person 空参构造函数" << endl;
}

void Person::setAge(int age) {
    this->age = age;
}

void Person::setName(char *name) {
    this->name = name;
}

void Person::setGen(char *gen) {
    this->gen = gen;
}

char *Person::getName() {
    cout << "DevYK getName" << endl;
    return this->name;
}

char *Person::getGen() {
    return this->gen;
}

int Person::getAge() {
    return this->age;
}

//3. 测试
void test19() {
    //栈里面定义的当该方法执行完就会回收掉 Person 对象
    Person personTemp;
    personTemp.setGen("男");
    personTemp.setName("小明");
    personTemp.setAge(18);
    cout << personTemp.getName() << "\t" << personTemp.getGen() << "\t" << personTemp.getAge() << endl;
    //初始化 Person 对象，在堆内存中，如果不主动清理 那么就会造成 内存泄漏
    Person *person = new Person("DevYK", "男", 28);
    cout << person->getName() << "\t" << person->getGen() << "\t" << person->getAge() << endl;
    //释放 person 堆内存
    delete person;
}

```

> **输出:**
>
> 执行 Person 空参构造函数
> 小明	男	18
> DevYK	男	28
> Person 销毁
> Person 销毁

需要注意的是，私有的成员和受保护的成员不能使用直接成员访问运算符 (.) 来直接访问。我们将在后续的教程中学习如何访问私有成员和受保护的成员。

**类 & 对象详解:**

到目前为止，我们已经对 C++ 的类和对象有了基本的了解。下面的列表中还列出了其他一些 C++ 类和对象相关的概念，可以点击相应的链接进行学习。

| 概念                                                         | 描述                                                         |
| :----------------------------------------------------------- | :----------------------------------------------------------- |
| [类成员函数](https://www.runoob.com/cplusplus/cpp-class-member-functions.html) | 类的成员函数是指那些把定义和原型写在类定义内部的函数，就像类定义中的其他变量一样。 |
| [类访问修饰符](https://www.runoob.com/cplusplus/cpp-class-access-modifiers.html) | 类成员可以被定义为 public、private 或 protected。默认情况下是定义为 private。 |
| [构造函数 & 析构函数](https://www.runoob.com/cplusplus/cpp-constructor-destructor.html) | 类的构造函数是一种特殊的函数，在创建一个新的对象时调用。类的析构函数也是一种特殊的函数，在删除所创建的对象时调用。 |
| [C++ 拷贝构造函数](https://www.runoob.com/cplusplus/cpp-copy-constructor.html) | 拷贝构造函数，是一种特殊的构造函数，它在创建对象时，是使用同一类中之前创建的对象来初始化新创建的对象。 |
| [C++ 友元函数](https://www.runoob.com/cplusplus/cpp-friend-functions.html) | **友元函数**可以访问类的 private 和 protected 成员。         |
| [C++ 内联函数](https://www.runoob.com/cplusplus/cpp-inline-functions.html) | 通过内联函数，编译器试图在调用函数的地方扩展函数体中的代码。 |
| [C++ 中的 this 指针](https://www.runoob.com/cplusplus/cpp-this-pointer.html) | 每个对象都有一个特殊的指针 **this**，它指向对象本身。        |
| [C++ 中指向类的指针](https://www.runoob.com/cplusplus/cpp-pointer-to-class.html) | 指向类的指针方式如同指向结构的指针。实际上，类可以看成是一个带有函数的结构。 |
| [C++ 类的静态成员](https://www.runoob.com/cplusplus/cpp-static-members.html) | 类的数据成员和函数成员都可以被声明为静态的。                 |

### 23. 继承

面向对象程序设计中最重要的一个概念是继承。继承允许我们依据另一个类来定义一个类，这使得创建和维护一个应用程序变得更容易。这样做，也达到了重用代码功能和提高执行效率的效果。

当创建一个类时，您不需要重新编写新的数据成员和成员函数，只需指定新建的类继承了一个已有的类的成员即可。这个已有的类称为**基类**，新建的类称为**派生类**。

继承代表了 **is a** 关系。例如，哺乳动物是动物，狗是哺乳动物，因此，狗是动物，等等。

**基类 & 派生类:**

一个类可以派生自多个类，这意味着，它可以从多个基类继承数据和函数。定义一个派生类，我们使用一个类派生列表来指定基类。类派生列表以一个或多个基类命名，形式如下：

```c++
class derived-class: access-specifier base-class

```

其中，访问修饰符 access-specifier 是 **public、protected** 或 **private** 其中的一个，base-class 是之前定义过的某个类的名称。如果未使用访问修饰符 access-specifier，则默认为 private。

```c++
//1. 定义基类
class SuperMan {
public:
    ~SuperMan();

    char *superName;

    void setSuperName(char *superName);

    char *getSuperName();
};

//2. 定义子类
class DevYK : public SuperMan {
public:
    DevYK();

    ~DevYK();

    char *getSupName();
};

//3. 测试
void test20() {
		//子类
    DevYK *devYkTemp = new DevYK();
    //父类set Name
    devYkTemp->setSuperName("superMan");
    //子类获取
    cout << "单继承:" << devYkMoreTemp->getPersonName();
}

```

指针类型的访问需要以 “->” 形式来访问

> **输出:**
>
> 执行 DevYK 空参构造函数
>
> 单继承:superMan

**访问控制和继承:**

派生类可以访问基类中所有的非私有成员。因此基类成员如果不想被派生类的成员函数访问，则应在基类中声明为 private。

我们可以根据访问权限总结出不同的访问类型，如下所示：

| 访问     | public | protected | private |
| :------- | :----- | :-------- | :------ |
| 同一个类 | yes    | yes       | yes     |
| 派生类   | yes    | yes       | no      |
| 外部的类 | yes    | no        | no      |

一个派生类继承了所有的基类方法，但下列情况除外：

- 基类的构造函数、析构函数和拷贝构造函数。
- 基类的重载运算符。
- 基类的友元函数。

**多继承:**

多继承即一个子类可以有多个父类，它继承了多个父类的特性。

C++ 类可以从多个类继承成员，语法如下：

```c++
class <派生类名>:<继承方式1><基类名1>,<继承方式2><基类名2>,…
{
<派生类类体>
};

```

其中，访问修饰符继承方式是 **public、protected** 或 **private** 其中的一个，用来修饰每个基类，各个基类之间用逗号分隔，如上所示。现在让我们一起看看下面的实例：

```c++
//1. 定义基类 Person
class Person {
public: //公共的属性
    Person();

    ~Person();

    Person(char *name, char *gen, int age);

    char *name;
    char *gen;
    int age;

    void setName(char *name);

    char *getName();

    void setGen(char *gen);

    char *getGen();

    void setAge(int age);

    int getAge();



};

//2. 定义基类 SuperMan
class SuperMan {
public:
    ~SuperMan();

    char *superName;

    void setSuperName(char *superName);

    char *getSuperName();
};

//3. 派生类
/**
 * 继承关系
 * 多继承
 */
class DevYK : public Person, public SuperMan {
public:
    DevYK(char *name, int age) : Person(name, "nan", age) {};

    int length;

    DevYK();

    ~DevYK();

    char *getPersonName();

    char *getSupName();

    void setLength(int len);

    int getLength();

    char *getName();
};

//4. 测试
void test20() {
//    //子类
    DevYK *devYkTemp = new DevYK();
    //父类set Name
    devYkTemp->setName("DevYK");
    //子类获取
    cout << "单继承 Person Name:" << devYkTemp->getPersonName() << endl;

    //多继承
    DevYK *devYkMoreTemp = new DevYK();
    //给父类 Person set Name
    devYkMoreTemp->setName("DevYK");
    //给父类 Super set Name
    devYkMoreTemp->setSuperName("superMan");
    //子类获取
    cout << "多继承 Person Name:" << devYkMoreTemp->getPersonName()<< endl;
    cout << "多继承  SuperMan Name:" << devYkMoreTemp->getSupName() << endl;
    //释放内存
    delete devYkTemp, devYkMoreTemp;
}

```

> **输出:**
>
> 执行 Person 空参构造函数
> 执行 DevYK 空参构造函数
> 单继承 Person Name:DevYK
> 执行 Person 空参构造函数
> 执行 DevYK 空参构造函数
> 多继承 Person Name:DevYK
> 多继承  SuperMan Name:superMan
> DevYK 销毁
> SuperMan 销毁
> Person 销毁

### 24. 重载运算符和重载函数

C++ 允许在同一作用域中的某个**函数**和**运算符**指定多个定义，分别称为**函数重载**和**运算符重载**。

重载声明是指一个与之前已经在该作用域内声明过的函数或方法具有相同名称的声明，但是它们的参数列表和定义（实现）不相同。

当您调用一个**重载函数**或**重载运算符**时，编译器通过把您所使用的参数类型与定义中的参数类型进行比较，决定选用最合适的定义。选择最合适的重载函数或重载运算符的过程，称为**重载决策**。

**函数重载:**

```c++
//1. 在 .h 文件中定义 DevYK 对象
class DevYK {
public:
    int length;

    DevYK();

    ~DevYK();

    void setLength(int len);

    int getLength();

};

//2. .cpp 实现

DevYK::DevYK() {
    cout << "执行 DevYK 空参构造函数" << endl;
}

DevYK::~DevYK() {
    cout << "DevYK 销毁" << endl;
}

void DevYK::setLength(int len) {
    this->length = len;
}

int DevYK::getLength() {
    return this->length;
}

//3. 测试
void test21() {
    //1.运算符重载
    DevYK devYkA;
    DevYK devYkB;
    DevYK devYkC;

    //进行初始化赋值
    devYkA.setLength(500);
    devYkB.setLength(20);

    cout << "devYkA length ： " << devYkA.getLength() << endl;
    cout << "devYkB length ： " << devYkB.getLength() << endl;
};

```

> **输出:**
>
> devYkA length ： 500
> devYkB length ： 20

**运算符重载:**

您可以重定义或重载大部分 C++ 内置的运算符。这样，您就能使用自定义类型的运算符。

重载的运算符是带有特殊名称的函数，函数名是由关键字 operator 和其后要重载的运算符符号构成的。与其他函数一样，重载运算符有一个返回类型和一个参数列表。

```c++
DevYK operator+(const DevYK &b);

```

下面的实例使用成员函数演示了运算符重载的概念。在这里，对象作为参数进行传递，对象的属性使用 **this** 运算符进行访问，如下所示：

```c++
//1. 在 .h 文件中定义 DevYK 对象
class DevYK {
public:
    int length;

    DevYK();

    ~DevYK();

    void setLength(int len);

    int getLength();
  
    DevYK operator+(const DevYK &b);

};

//2. .cpp 实现

DevYK::DevYK() {
    cout << "执行 DevYK 空参构造函数" << endl;
}

DevYK::~DevYK() {
    cout << "DevYK 销毁" << endl;
}

void DevYK::setLength(int len) {
    this->length = len;
}

int DevYK::getLength() {
    return this->length;
}

// 重载 + 运算符，用于把两个 Box 对象相加
class DevYK DevYK::operator+(const class DevYK &b) {
    DevYK devYk;
    devYk.length = this->length + b.length;
    return devYk;
}

//3. 测试:
void test21() {
    //1.运算符重载
    DevYK devYkA;
    DevYK devYkB;
    DevYK devYkC;

    //进行初始化赋值
    devYkA.setLength(500);
    devYkB.setLength(20);

    cout << "devYkA length ： " << devYkA.getLength() << endl;
    cout << "devYkB length ： " << devYkB.getLength() << endl;

    devYkC = devYkA + devYkB;
    cout << "DevYK 运算符重载 = " << devYkC.getLength() << endl;
};

```

> **输出:**
>
> devYkA length ： 500
> devYkB length ： 20
>
> DevYK 运算符重载 = 520

### 25. 多态

**多态**按字面的意思就是多种形态。当类之间存在层次结构，并且类之间是通过继承关联时，就会用到多态。

C++ 多态意味着调用成员函数时，会根据调用函数的对象的类型来执行不同的函数。

下面的实例中，基类 Shape 被派生为两个类，如下所示：

```c++
//1. 定义了一个 Person 基类,跟 Java class 差不多
class Person {
public: //公共的属性
    Person();

    ~Person();

    Person(char *name, char *gen, int age);

    char *name;
    char *gen;
    int age;

    void setName(char *name);

    char *getName();

    void setGen(char *gen);

    char *getGen();

    void setAge(int age);

    int getAge();
     /**
     * 虚函数 是在基类中使用关键字 virtual 声明的函数。
     * 在派生类中重新定义基类中定义的虚函数时，会告诉编译器不要静态链接到该函数。
     * @return
     */
    //virtual 转移给子类实现
    virtual int test() {
        return 10;
    };
};

//2. 定义 DevYK 派生类
class DevYK : public Person {
public:
    DevYK(char *name, int age) : Person(name, "nan", age) {};

    int length;

    DevYK();

    ~DevYK();

    char *getPersonName();

    void setLength(int len);

    int getLength();

    DevYK operator+(const DevYK &b);

    char *getName();
  
    int test() {
        return -10;
    };
};

//3. .cpp 文件

#include "ClssSample.h"
#include <iostream>

using namespace std;


Person::Person(char *name, char *gen, int age) {
    this->name = name;
    this->age = age;
    this->gen = gen;
}

Person::~Person() {
    cout << "Person 销毁" << endl;
}

Person::Person() {
    cout << "执行 Person 空参构造函数" << endl;
}

void Person::setAge(int age) {
    this->age = age;
}

void Person::setName(char *name) {
    this->name = name;
}

void Person::setGen(char *gen) {
    this->gen = gen;
}

char *Person::getName() {
    return this->name;
}

char *Person::getGen() {
    return this->gen;
}

int Person::getAge() {
    return this->age;
}


DevYK::DevYK() {
    cout << "执行 DevYK 空参构造函数" << endl;
}

DevYK::~DevYK() {
    cout << "DevYK 销毁" << endl;
}

char *DevYK::getName() {
    cout << "DevYK getName" << endl;
    return this->name;
}

char *DevYK::getPersonName() {
    return this->name;
}


void DevYK::setLength(int len) {
    this->length = len;
}

int DevYK::getLength() {
    return this->length;
}

// 重载 + 运算符，用于把两个 Box 对象相加
class DevYK DevYK::operator+(const class DevYK &b) {
    DevYK devYk;
    devYk.length = this->length + b.length;
    return devYk;
}

//3. 测试

void test22() {
    //父类
    Person *person;
    //定义子类
    DevYK devYk("DevYK", 27);
    if (person) {
        cout << "Person\t" << person->getName() << "\t" << person->getGen() << "\t" << person->getAge() << endl;
    }
    cout << "DevYK->\t" << devYk.getName() << "\t" << devYk.getGen() << "\t" << devYk.getAge() << endl;

    //把 devyk 的内存地址赋值给 person
    person = &devYk;

    if (person) {
        cout << "Person\t" << person->getName() << "\t" << person->getGen() << "\t" << person->getAge() << endl;
    }
    cout << "DevYK 内存地址->\t" << &devYk << " Person 内存地址\t" << person << endl;

    //获取子类数据
    int test = person->test();
    cout << "test->\t" << test << endl;
}

```

> **输出:**
>
> DevYK->	DevYK getName
> DevYK		nan	27
> Person		DevYK	nan	27
> DevYK 内存地址->	0x7ffee1d26628 Person 内存地址	0x7ffee1d26628
> test->	-10
> DevYK 销毁
> Person 销毁

**虚函数:**

**虚函数** 是在基类中使用关键字 **virtual** 声明的函数。在派生类中重新定义基类中定义的虚函数时，会告诉编译器不要静态链接到该函数。

我们想要的是在程序中任意点可以根据所调用的对象类型来选择调用的函数，这种操作被称为**动态链接**，或**后期绑定**。

**纯虚函数:**

您可能想要在基类中定义虚函数，以便在派生类中重新定义该函数更好地适用于对象，但是您在基类中又不能对虚函数给出有意义的实现，这个时候就会用到纯虚函数。

### 26. 数据封装

所有的 C++ 程序都有以下两个基本要素：

- **程序语句（代码）：**这是程序中执行动作的部分，它们被称为函数。
- **程序数据：**数据是程序的信息，会受到程序函数的影响。

封装是面向对象编程中的把数据和操作数据的函数绑定在一起的一个概念，这样能避免受到外界的干扰和误用，从而确保了安全。数据封装引申出了另一个重要的 OOP 概念，即**数据隐藏**。

**数据封装**是一种把数据和操作数据的函数捆绑在一起的机制，**数据抽象**是一种仅向用户暴露接口而把具体的实现细节隐藏起来的机制。

C++ 通过创建**类**来支持封装和数据隐藏（public、protected、private）。我们已经知道，类包含私有成员（private）、保护成员（protected）和公有成员（public）成员。默认情况下，在类中定义的所有项目都是私有的。例如：

```c++
class Box
{
   public:
      double getVolume(void)
      {
         return length * breadth * height;
      }
   private:
      double length;      // 长度
      double breadth;     // 宽度
      double height;      // 高度
};

```

变量 length、breadth 和 height 都是私有的（private）。这意味着它们只能被 Box 类中的其他成员访问，而不能被程序中其他部分访问。这是实现封装的一种方式。

为了使类中的成员变成公有的（即，程序中的其他部分也能访问），必须在这些成员前使用 **public** 关键字进行声明。所有定义在 public 标识符后边的变量或函数可以被程序中所有其他的函数访问。

把一个类定义为另一个类的友元类，会暴露实现细节，从而降低了封装性。理想的做法是尽可能地对外隐藏每个类的实现细节。

```c++
//1. .h
class Box
{
   public:
      double getVolume(void)
      {
         return length * breadth * height;
      }
   private:
      double length;      // 长度
      double breadth;     // 宽度
      double height;      // 高度
};
//2. .cpp
double Box::getVolume() {
    return this->length * this->height * this->width;
}

void Box::initValue() {
    //默认
    int a = 10, b = 20, c = 30;
    length = a, width = b, height = c;
}
//3. cpp 测试
void test23() {
    Box box;
    box.initValue();
    cout << "数据私有封住:" << box.getVolume() << endl;
}

```

> **输出:**
>
> 数据私有封住:6000

### 27. 接口(抽象类)

接口描述了类的行为和功能，而不需要完成类的特定实现。

C++ 接口是使用**抽象类**来实现的，抽象类与数据抽象互不混淆，数据抽象是一个把实现细节与相关的数据分离开的概念。

如果类中至少有一个函数被声明为纯虚函数，则这个类就是抽象类。纯虚函数是通过在声明中使用 "= 0" 来指定的。

例子参考 25 小节的多态。

### 28. 文件和流

到目前为止，我们已经使用了 **iostream** 标准库，它提供了 **cin** 和 **cout** 方法分别用于从标准输入读取流和向标准输出写入流。

本教程介绍如何从文件读取流和向文件写入流。这就需要用到 C++ 中另一个标准库 **fstream**，它定义了三个新的数据类型：

| 数据类型 | 描述                                                         |
| :------- | :----------------------------------------------------------- |
| ofstream | 该数据类型表示输出文件流，用于创建文件并向文件写入信息。     |
| ifstream | 该数据类型表示输入文件流，用于从文件读取信息。               |
| fstream  | 该数据类型通常表示文件流，且同时具有 ofstream 和 ifstream 两种功能，这意味着它可以创建文件，向文件写入信息，从文件读取信息。 |

要在 C++ 中进行文件处理，必须在 C++ 源代码文件中包含头文件 <iostream> 和 <fstream>。

在从文件读取信息或者向文件写入信息之前，必须先打开文件。**ofstream** 和 **fstream** 对象都可以用来打开文件进行写操作，如果只需要打开文件进行读操作，则使用 **ifstream** 对象。

下面是 open() 函数的标准语法，open() 函数是 fstream、ifstream 和 ofstream 对象的一个成员。

```c++
void open(const char *filename, ios::openmode mode);

```

在这里，**open()** 成员函数的第一参数指定要打开的文件的名称和位置，第二个参数定义文件被打开的模式。

| 模式标志   | 描述                                                         |
| :--------- | :----------------------------------------------------------- |
| ios::app   | 追加模式。所有写入都追加到文件末尾。                         |
| ios::ate   | 文件打开后定位到文件末尾。                                   |
| ios::in    | 打开文件用于读取。                                           |
| ios::out   | 打开文件用于写入。                                           |
| ios::trunc | 如果该文件已经存在，其内容将在打开文件之前被截断，即把文件长度设为 0。 |

您可以把以上两种或两种以上的模式结合使用。例如，如果您想要以写入模式打开文件，并希望截断文件，以防文件已存在，那么您可以使用下面的语法：

```c++
ofstream outfile;
outfile.open("file.dat", ios::out | ios::trunc );

```

类似地，您如果想要打开一个文件用于读写，可以使用下面的语法：

```c++
ifstream  afile;
afile.open("file.dat", ios::out | ios::in );

```

**关闭文件:**

当 C++ 程序终止时，它会自动关闭刷新所有流，释放所有分配的内存，并关闭所有打开的文件。但程序员应该养成一个好习惯，在程序终止前关闭所有打开的文件。

下面是 close() 函数的标准语法，close() 函数是 fstream、ifstream 和 ofstream 对象的一个成员。

```c++
void close();

```

**写入文件:**

在 C++ 编程中，我们使用流插入运算符（ << ）向文件写入信息，就像使用该运算符输出信息到屏幕上一样。唯一不同的是，在这里您使用的是 **ofstream** 或 **fstream** 对象，而不是 **cout** 对象。

**读取文件:**

在 C++ 编程中，我们使用流提取运算符（ >> ）从文件读取信息，就像使用该运算符从键盘输入信息一样。唯一不同的是，在这里您使用的是 **ifstream** 或 **fstream** 对象，而不是 **cin** 对象。

**读取 & 写入实例:**

```c++
void test24() {
    char data[100];
    //ofstream: 用于创建文件并向文件写入信息。
    ofstream outfile;
    outfile.open("/Users/devyk/Data/ClionProjects/NDK_Sample/README.md");
    cout << "请输入写入文件的内容：" << endl;
    cin.getline(data, 100);
    //向文件开始写入数据
    outfile << data << endl;

    cin.ignore();
    //关闭打开的文件
    outfile.close();


    cout << "\n\n" << endl;
    char readData[100];
    //开始读文件
    ifstream readFile;
    readFile.open("/Users/devyk/Data/ClionProjects/NDK_Sample/README.md");
    readFile.getline(readData, 100);
    cout << "读取成功\n" << readData << endl;
    readFile.close();


}

```



![](https://devyk.oss-cn-qingdao.aliyuncs.com/blog/20200106211229.gif)

### 29. 异常处理

异常是程序在执行期间产生的问题。C++ 异常是指在程序运行时发生的特殊情况，比如尝试除以零的操作。

异常提供了一种转移程序控制权的方式。C++ 异常处理涉及到三个关键字：**try、catch、throw**。

- **throw:** 当问题出现时，程序会抛出一个异常。这是通过使用 **throw** 关键字来完成的。
- **catch:** 在您想要处理问题的地方，通过异常处理程序捕获异常。**catch** 关键字用于捕获异常。
- **try:** **try** 块中的代码标识将被激活的特定异常。它后面通常跟着一个或多个 catch 块。

如果有一个块抛出一个异常，捕获异常的方法会使用 **try** 和 **catch** 关键字。try 块中放置可能抛出异常的代码，try 块中的代码被称为保护代码。使用 try/catch 语句的语法如下所示：

```c++
try
{
   // 保护代码
}catch( ExceptionName e1 )
{
   // catch 块
}catch( ExceptionName e2 )
{
   // catch 块
}catch( ExceptionName eN )
{
   // catch 块
}

```

如果 **try** 块在不同的情境下会抛出不同的异常，这个时候可以尝试罗列多个 **catch** 语句，用于捕获不同类型的异常。

**抛出异常:**

您可以使用 **throw** 语句在代码块中的任何地方抛出异常。throw 语句的操作数可以是任意的表达式，表达式的结果的类型决定了抛出的异常的类型。

以下是尝试除以零时抛出异常的实例：

```c++
double division(int a, int b)
{
   if( b == 0 )
   {
      throw "Division by zero condition!";
   }
   return (a/b);
}

```

**捕获异常:**

**catch** 块跟在 **try** 块后面，用于捕获异常。您可以指定想要捕捉的异常类型，这是由 catch 关键字后的括号内的异常声明决定的。

```c++
try
{
   // 保护代码
}catch( ExceptionName e )
{
  // 处理 ExceptionName 异常的代码
}

```

下面是一个实例，抛出一个除以零的异常，并在 catch 块中捕获该异常。

```c++
#include <iostream>
using namespace std;
 
double division(int a, int b)
{
   if( b == 0 )
   {
      throw "Division by zero condition!";
   }
   return (a/b);
}
 
int main ()
{
   int x = 50;
   int y = 0;
   double z = 0;
 
   try {
     z = division(x, y);
     cout << z << endl;
   }catch (const char* msg) {
     cerr << msg << endl;
   }
 
   return 0;
}

```

由于我们抛出了一个类型为 **const char\*** 的异常，因此，当捕获该异常时，我们必须在 catch 块中使用 const char*。当上面的代码被编译和执行时，它会产生下列结果：

> **输出:**
>
> Division by zero condition!

**自定义异常:**

您可以通过继承和重载 **exception** 类来定义新的异常。下面的实例演示了如何使用 std::exception 类来实现自己的异常：

```c++
//自定义一个新的异常
class MyException : public std::exception{

public:
    const char* what() const  throw(){
        return "C++ 操作失误，请检查代码是否正确!";
    }
};

//测试:
void test25() {
    try {
        throw "空指针异常";
    } catch (const char *msg) {
        cout << "错误日志:\t" << msg << endl;
    }

    //自定义异常
    try {
        throw MyException();
    } catch (MyException exception) {
        cout << "自定义异常:" << exception.what() << endl;
    } catch (exception &error) {
        cout << "其它异常:" << error.what() << endl;
    }
}

```

> **输出:**
>
> 错误日志:	空指针异常
> 自定义异常:C++ 操作失误，请检查代码是否正确!

### 30. 动态内存

了解动态内存在 C++ 中是如何工作的是成为一名合格的 C++ 程序员必不可少的。C++ 程序中的内存分为两个部分：

- **栈：**在函数内部声明的所有变量都将占用栈内存。
- **堆：**这是程序中未使用的内存，在程序运行时可用于动态分配内存。

很多时候，您无法提前预知需要多少内存来存储某个定义变量中的特定信息，所需内存的大小需要在运行时才能确定。

在 C++ 中，您可以使用特殊的运算符为给定类型的变量在运行时分配堆内的内存，这会返回所分配的空间地址。这种运算符即 **new** 运算符。

如果您不再需要动态分配的内存空间，可以使用 **delete** 运算符，删除之前由 new 运算符分配的内存。

**new 和 delete 运算符:**

下面是使用 new 运算符来为任意的数据类型动态分配内存的通用语法：

```c++
new data-type;

```

在这里，**data-type** 可以是包括数组在内的任意内置的数据类型，也可以是包括类或结构在内的用户自定义的任何数据类型。让我们先来看下内置的数据类型。例如，我们可以定义一个指向 double 类型的指针，然后请求内存，该内存在执行时被分配。我们可以按照下面的语句使用 **new** 运算符来完成这点：

```c++
double* pvalue  = NULL; // 初始化为 null 的指针
pvalue  = new double;   // 为变量请求内存

```

如果自由存储区已被用完，可能无法成功分配内存。所以建议检查 new 运算符是否返回 NULL 指针，并采取以下适当的操作：

```c++
double* pvalue  = NULL;
if( !(pvalue  = new double ))
{
   cout << "Error: out of memory." <<endl;
   exit(1);
 
}

```

**malloc()** 函数在 C 语言中就出现了，在 C++ 中仍然存在，但建议尽量不要使用 malloc() 函数。new 与 malloc() 函数相比，其主要的优点是，new 不只是分配了内存，它还创建了对象。

在任何时候，当您觉得某个已经动态分配内存的变量不再需要使用时，您可以使用 delete 操作符释放它所占用的内存，如下所示：

```c++
delete pvalue;        // 释放 pvalue 所指向的内存

```

下面的实例中使用了上面的概念，演示了如何使用 new 和 delete 运算符：

```c++
void test26() {
    //演示如何使用 new 和 delete 运算符：
    //初始化为 null 的指针
    double *pvalue = NULL;
    //为变量申请内存
    pvalue = new double;
    //在分配的地址存储值
    *pvalue = 1314.520;
    //打印存储的数字
    cout << "pvalue 的地址值为:\t" << &pvalue << "\n在该地址存储的值为:\t" << *pvalue << endl;
    //释放内存
    delete pvalue;

    //数组的动态内存分配
    //动态分配，数组长度为 10
    int *array = new int[10];
    //释放数组内存
    delete[] array;

    //对象的动态内存分配
    Box *testBox = new Box[10];
    delete[] testBox;

}

```

> **输出:**
>
> pvalue 的地址值为:	0x7ffee8b27658
> 在该地址存储的值为:	1314.52
>
> pvalue 的地址值为:	0x7ffee7b8c658
> 在该地址存储的值为:	1314.52
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用构造函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！
> 调用析构函数！

### 31. 命名空间

**定义命名空间:**

命名空间的定义使用关键字 **namespace**，后跟命名空间的名称，如下所示：

```c++
namespace namespace_name {
   // 代码声明
}

```

为了调用带有命名空间的函数或变量，需要在前面加上命名空间的名称，如下所示：

```c++
name::code;  // code 可以是变量或函数

```

让我们来看看命名空间如何为变量或函数等实体定义范围：

```c++
//1. 定义命名空间
namespace test1_space {
    void func() {
        cout << "test1_space" << endl;
    }
}
namespace test2_space {
    void func2() {
        cout << "test2_space" << endl;
    }
}


void test27() {
    test1_space::func();
    test2_space::func2();
}

```

> **输出:**
>
> test1_space
> test2_space

**using 指令:**

您可以使用 **using namespace** 指令，这样在使用命名空间时就可以不用在前面加上命名空间的名称。这个指令会告诉编译器，后续的代码将使用指定的命名空间中的名称。

```c++
//1. 定义命名空间
namespace test1_space {
    void func() {
        cout << "test1_space" << endl;
    }
}
namespace test2_space {
    void func2() {
        cout << "test2_space" << endl;
    }
}
//2. 使用 using 指令
using namespace test1_space;
using namespace test2_space;

void test27() {
    //1.
    test1_space::func();
    test2_space::func2();
    //2.
    func();
    func2();
}

```

> **输出:**
>
> test1_space
> test2_space
>
> test1_space
> test2_space

### 32. 预处理器

预处理器是一些指令，指示编译器在实际编译之前所需完成的预处理。

所有的预处理器指令都是以井号（#）开头，只有空格字符可以出现在预处理指令之前。预处理指令不是 C++ 语句，所以它们不会以分号（;）结尾。

我们已经看到，之前所有的实例中都有 **#include** 指令。这个宏用于把头文件包含到源文件中。

C++ 还支持很多预处理指令，比如 #include、#define、#if、#else、#line 等，让我们一起看看这些重要指令。

**define 预处理:**

define 预处理指令用于创建符号常量。该符号常量通常称为**宏**，指令的一般形式是：

```c++
#define macro-name replacement-text 

```

当这一行代码出现在一个文件中时，在该文件中后续出现的所有宏都将会在程序编译之前被替换为 replacement-text。例如：

```c++
//1. 预处理器
#define  MAX 100;
void test28() {
    cout << "通过预处理器定义了一个 MAX:" << MAX;
}

```

> **输出:**
>
> 通过预处理器定义了一个 MAX:100

**参数宏:**

您可以使用 #define 来定义一个带有参数的宏，如下所示：

```c++
//2. 参数宏
#define  MAX_VALUE(a, b)(a>b?a:b);
void test28() {
    cout << "\n通过预处理器定义了一个 MAX_VALUE:" << MAX_VALUE(10, 20);
}

```

> **输出:**
>
> 通过预处理器定义了一个 MAX_VALUE:20

**条件编译:**

有几个指令可以用来有选择地对部分程序源代码进行编译。这个过程被称为条件编译。

条件预处理器的结构与 if 选择结构很像。请看下面这段预处理器的代码：

```c++
//3. 条件编译
#ifdef  NULL
#define NULL 0
#endif

```

### 33. 多线程

多线程是多任务处理的一种特殊形式，多任务处理允许让电脑同时运行两个或两个以上的程序。一般情况下，两种类型的多任务处理：**基于进程和基于线程**。

- 基于进程的多任务处理是程序的并发执行。
- 基于线程的多任务处理是同一程序的片段的并发执行。

多线程程序包含可以同时运行的两个或多个部分。这样的程序中的每个部分称为一个线程，每个线程定义了一个单独的执行路径。

本教程假设您使用的是 Linux 操作系统，我们要使用 POSIX 编写多线程 C++ 程序。POSIX Threads 或 Pthreads 提供的 API 可在多种类 Unix POSIX 系统上可用，比如 FreeBSD、NetBSD、GNU/Linux、Mac OS X 和 Solaris。

**创建线程:**

下面的程序，我们可以用它来创建一个 POSIX 线程：

```c++
#include <pthread.h>
pthread_create (thread, attr, start_routine, arg) 

```

在这里，**pthread_create** 创建一个新的线程，并让它可执行。下面是关于参数的说明：

| 参数          | 描述                                                         |
| :------------ | :----------------------------------------------------------- |
| thread        | 指向线程标识符指针。                                         |
| attr          | 一个不透明的属性对象，可以被用来设置线程属性。您可以指定线程属性对象，也可以使用默认值 NULL。 |
| start_routine | 线程运行函数起始地址，一旦线程被创建就会执行。               |
| arg           | 运行函数的参数。它必须通过把引用作为指针强制转换为 void 类型进行传递。如果没有传递参数，则使用 NULL。 |

创建线程成功时，函数返回 0，若返回值不为 0 则说明创建线程失败。

**终止线程:**

使用下面的程序，我们可以用它来终止一个 POSIX 线程：

```c++
#include <pthread.h>
pthread_exit (status) 

```

在这里，**pthread_exit** 用于显式地退出一个线程。通常情况下，pthread_exit() 函数是在线程完成工作后无需继续存在时被调用。

如果 main() 是在它所创建的线程之前结束，并通过 pthread_exit() 退出，那么其他线程将继续执行。否则，它们将在 main() 结束时自动被终止。

```c++
//定义一个线程数量宏
#define NUM_THREADS 5

//线程的运行函数
void *logD(void * args) {
   int threadID =  *((int*)args);
    cout << "线程执行了" << threadID << endl;
}

void test29() {
    //定义线程的 ID 变量，多个变量使用数组
    pthread_t tids[NUM_THREADS];

    for (int i = 0; i < NUM_THREADS; ++i) {
        //参数依次是：创建的线程 id,线程参数，调用的函数，传入的参数函数
        int ptc = pthread_create(&tids[i],NULL,logD,(void*)&(i));
        if(0!=ptc){
            cout << "pthread_create error:error code ：" << ptc << endl;
        }
    }


    //等线程执行完毕后在释放线程
    pthread_exit(NULL);

}

```

> **输出:**
>
> 线程执行了线程执行了5
> 线程执行了5
> 5
> 线程执行了5
> 线程执行了5

## 总结

这里差不多 C++ 基础都讲解完了，面向对象思想还是很好理解的，下来大家一定要好好消化，下一个开始就开始使用 AS 学习 JNI 知识了。

## 参考

- [C++ 关键字介绍](https://www.runoob.com/w3cnote/cpp-keyword-intro.html)
- [C++ 实例练习](https://www.runoob.com/cplusplus/cpp-examples.html)
- [C++ 基础入门