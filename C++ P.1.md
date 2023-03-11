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

