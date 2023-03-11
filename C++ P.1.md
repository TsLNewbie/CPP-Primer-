---
title: C++
category: /小书匠/日记/2023-03
renderNumberedHeading: true
grammar_cjkRuby: true
---

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

