---
title: C++
category: /小书匠/日记/2023-03
renderNumberedHeading: true
grammar_cjkRuby: true
---
[toc!]


## 初次进入C++世界



### 进入C++
C++ 是用 cout 生成字符输出。

注释符号： //

C++ 对大小写敏感，所以要区分大小写。

第一个编程：
```C++
//My first.cpp

#include<iostream>
int main()
{

using namespace std; // 这一行很重要，是提供 cout 语法的编程。
cout << "Hello World" ;
cout << endl;

return 0;

}
```
预处理编译指令： #include
函数头： int main()
编译指令： using namespace
函数体： { }
结束main()函数的 ：return

如果要让窗口一直打开，直到按任何键，可以加上
```c++
cin.get()
```

### C语言输入和输出

C语言和C++在输入输出有不一样。

但是C++可以使用C的内容。

```c++

int main()
{

//C
printf("Hello World");
scanf(a);
printf(a);

//C++

cout << "Hello World" << endl;
cin >> a;
cout << a;
}

```

!! 重点： 若要在C++里使用 C语言，则需要加上 stdio.h 文件。

### 语句和分号

语句是要执行的操作，为理解源代码，编译器需要重点一条语句的结束和开始。 

：C++没办法忽略 分号。

```c++
int main()

//在C语言里，省略return type 相当于说 function 类型为 int
//但在C++里，已经淘汰了。

main() //不建议使用

//可以一下这样写，但其实和int main（）一样的。
int main(void)

//Void 明确指出，函数不会接收任何参数。

//或者也可以这样写
void main()

```

### C++预处理器和iostream文件

```C++
//My first.cpp

#include<iostream>


```

**iostream文件**： io 指的是 input / output。
C++的INPUT/Output 涉及 iostream 文件的多个定义。
为了使用cout来输出消息，第一个程序需要这些定义。

### 头文件

像iostream 文件 叫做 包含文件（include file)，由于他们包含在其他文件中，
也叫做头文件(header file) 由于他们被包含在文件起始处。

| 头文件类型  | 约定                  | 示例       | 说明                         |
| ----------- | --------------------- | ---------- | ---------------------------- |
| C++旧式风格 | 以.h结尾              | iostream.h | C++可以使用                  |
| C旧式风格   | 以.h结尾              | math.h     | C,C++可以使用                |
| C++新式风格 | 没有扩展名            | iostream   | C++可以使用：用namespace std |
| 转换后的C   | 加上前缀c，没有扩展名 | cmath      | C++可以使用                  |

### 名称空间
如果直接使用iostream，而不是iostream.h 是没办法使用的。
在需要加一个内容：

```c++
using namespace std;
```
这叫做using 编译指令。
名称空间是C++特性。在编写大型程序的时候可以把现有的代码组合起来更加容易。
但其中有可能出现的问题是：两个已经封装好的产品，他们都包含相同名称的函数。比如 wanda()函数。
这样编译器要调用函数时就不清楚是哪个wanda()
所以重点是：建议加上前缀，这样就可以用名称空间的名称来指出想使用哪个厂商的产品。
比如：
```c++
Microflop::wanda("Go dacing?"); //use Microflop namespace version
Piscine::wanda("a fish name Desire");// use Piscine namespace version
```

按照这种方式，类、函数和变量便是C++编译器的标准组件。它们都被放置在名称空间std中。
仅当头文件没有扩展名h时，情况才是如此。
这意思是：iostream 中定义的cout变量实际上是 std::cout。
endl = std::endl

*：通常这种情况太麻烦了，所以这个就很重要。*
```c++
using namespace std;
```
这样使得std名称空间里的所有名称都可以用。是一种偷懒的办法。但是如果是大型程序，也是一个潜在的问题。、
所以更好的办法，只使所需的名称可以用，可以通过using声明来实现。

```c++
using std::cout;  // make cout available
using std::endl;  // make endl available
using std::cin;   // make cin  available

using namespace std; // make all names of std available.


```

### cout 进行C++输出

先看看如何输出消息的。

```c++

int main()
{

cout << "Hello World" << endl;

}
```

**cout ：** cout 对象
**<< ：** 插入运算符
**"Hello World"** ： 字符串

cout << "Hello World" << endl;

**PS：稍微比较重要的内容**------运算符重载
运算符重载： 在C里 "<<" 为 **按位左移运算符**。
而C++ 里是 **插入运算符**
这是运算符重载的一个例子。
通过重载，让同一个运算符有不同的含义，编译器会通过上下文来判断运算符的含义。
C本身就有运算符重载的情况：
& ： 地址运算符，也表示按位AND运算符。
\* ：表示乘法，也表示对指针解除引用。

#### 控制符 endl 
在C++里 cout 是不会自动换行的，所以需要一个换行符。

endl ： 重起一行。

```c++
cout << endl;

//endl 的作用便是换行，而在C里相当于\n
//而在C++里，\n也可以使用为换行。

cout << " Who \n next ?" ;
cout << "Who" << endl << "next ?" ;

//以下为换行的，用endl会方便一些。
cout << endl;
cout << "\n";
```

### C++源代码的格式化

有些语言是面向行的（Python），则每条语句占一行，在编译器里只要换行就代表一条语句。而在C++里，则是 **分号**。

所以C++里搞得很乱都无所谓，最重要的是 分号 要在。

```c++

#include <iostream>
int
main
()
{  using namespace
std;
cout
<<
"太乱啦"
<< endl;

return 0 ;

}

```

**但你这样写只有折磨自己和折磨团队的份，所以千万不要这样做。** = = 

### 源代码中的标记和空白
一行代码中不可分割的元素叫做标记（Token）
通常：必须用空格，制表符或回车将两个Token分开，空格，制表符和回车都叫做 空白 （white space）

以下为各种情况：
```c++

return0;  // Invalid, must be return 0;
return (0); // Valid, white space omitted
return  (0); // Valid
intmain();  // Invalid
int main(); // Valid
int main (); // Valid

```

## C++源代码风格

**C++书所提到一个非常重要的，C++源代码风格。**
通过遵守以下规矩：
1.每条语句占一行。
2.每个函数都有一个开始花括号和一个结束花括号，这两个花括号各占一行。
3.函数中的语句都相对于花括号进行缩进。
4.与函数名称相关的圆括号周围没有空白。

## C++语句。


程序：

```c++
#include <iostream>

int main()
{
 using namespace std;
 
 int carrots;       //declare an integer variable
 
 carrots = 25;      //assign a value to the variable
 cout << "I have "; << carrots << "carrots." << endl;  //carrots = display the value of the variable
 carrots = carrots - 1;  // modify the variable
 cout <<"Crunch, crunch. Now I have " << carrots << "carrots." <<endl;
 return 0;


}
```
效果：
```
I have 25carrots.
Crunch, crunch. Now I have 24carrots.
```

### 声明语句和变量

```c++
int carrots;
```
这条语句提供了两项消息。需要的内存和内存单元的名称：
被存储的数据类型：int
变量名：carrots
具体来说，这条语句指出程序需要足够的存储空间来存储一个整数，在C++中int代表一个无小数点的整数。
编译器负责分配和标记内存的细节。

第二个任务则是给存储单元指定名称：carrots.

### 赋值语句

```c++
carrots = 25;
```
符号 " = " 为赋值运算符，而C++/C有一项不寻常的特性————可以连续使用赋值运算符。
比如以下程序：

```c++
int steinway;
int baldwin;
int yamaha;
yamaha = baldwin = steinway = 88;
```
以上程序的情况是：
赋值将会从右到走进行，首先88先赋值给steinway，然后steinway的值（88)赋值给baldwin，而最后baldwin (88)会赋值给 yamaha.

在赋值里，可以进行修改，比如：
```C++

```