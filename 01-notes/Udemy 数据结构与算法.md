# Udemy 数据结构与算法（c/c++）

## Chapter1 Introduce 介绍

网站：https://www.udemy.com/course/datastructurescncpp/ 

作者：Abdul Bari Udemy

评分：4.7 

学生数：100777 

官网售价：US$ 99.9

课程时长 ： 45h

## Chapter2 Basics C/C++基础

### Arrays

defined as a collection of similar data elements.

main memory（Heap，Stack，Code Section）

定义的数组，储存在栈内  

### Structure

defined as a collection of data members that are related data members under one name

定义的结构，储存在栈内

老师这边的板书忽略了内存对齐的问题。

>内存对齐三个原则:
>
>结构体变量的起始地址能够被其最宽的成员大小整除
>结构体每个成员相对于起始地址的偏移能够被其自身大小整除，如果不能则在前一个成员后面补充字节
>结构体总体大小能够被最宽的成员的大小整除，如不能则在后面补充字节

我实操下来，就是char如果连char，那么他们实际是一体的。一起进行内存对齐。

```c++
#include <iostream>
struct  child{
    int roll; //4

};
struct  child1{
    int roll; //4
    char name[25];//28

};
struct  child2{
    int roll; //4
    char name[25];//28
    char dept[10];//12

};
struct  child3{
    int roll; //4
    char name[25];//28
    char dept[10];//12
    char add[50];//52
};
struct  child4{
    int roll ;//4
    char name[25];//28
    int m; //4
    char dept[10];//12
    int t;//4
    char add[50];//52
};
int main() {

    std::cout << sizeof(child) << std::endl;
    std::cout << sizeof(child1) << std::endl;
    std::cout << sizeof(child2) << std::endl;
    std::cout << sizeof(child3) << std::endl;
    std::cout << sizeof(child4) << std::endl;
    return 0;
}
/*
C:\Users\Admin\CLionProjects\0801\cmak e-build-debug\0801.exe
4
32
40
92
104
*/
```

### Pointers 

defined as an **address variable** that is meant for storing address of data

- access heap memory 

  - c				malloc     

    ```c++
    int *p;
    p = (int*)malloc(6*sizeof(int));
    ```

  - c++            new

    ```c++
    int *p;
    p = new int[5];
    ```

    

- **access the resources which are  outside the program**

- pass parameters



### Reference

 alias given to a variable

### Pointers upon a structure

```c++
struct Rect r = {1,4};
struct Rect *p = &r;
(*p).length = 20;
p->length = 20;
```

### Function

 a piece of code which performs a specific task 

单体编程 Monolithic programming 所有都在一个main函数内

模块化编程或面向过程编程 modular programming or procedural programming

c++ 面向对象

### Parameter Passing 参数传递

实参actual parameters

形参 formal parameters

- Pass by Value

拷贝赋值，实际函数里的变量和main函数的变量无关

- Pass by Address

使用指针，形参必须为指针

会在stack 开辟一些空间用来存指针

```c++
void swap(int* x, int* y){
    int temp;
    temp = *x;
    *x = *y;
    *y= temp;
}
swap(&a,&b);
```



- Pass by Reference

起的别名，只是从不同函数角度看不一样，实际是一样的。

swap 不再完全独立，代码会被粘贴到swap位置，和main共享堆栈区 

所以引用调用应该用在小段代码，避免循环。

```c++
void swap(int&x, int&y){
    int temp;
    temp = x;
    x = y;
    y= temp;
}
swap(a, b);
```

> https://www.cnblogs.com/yanlingyin/archive/2011/12/07/2278961.html

### Array as Parameters

```c++
void fun(int a[],n){  }
```

数组其实就是指针，只不过多了一些规定

### Structure as  Parameters.

```c++
struct Rectangle{
    int length;
    int width;
}
int area(struct Rectangle r){
    //pass by value
    
    return r.length*r.width;
}
int area(struct Rectangle &r){
    //pass by reference
    r.length ++;
    return r.length*r.width;
}
void changelength(struct Rectangle *r,int len){
    (*r).length = len;
    r->length = len;
}
struct Rectangle n(10,5);
changelength(&n,20);
```

 

### Constructor

### Templates

## Chapter3 SetUp 准备环境

## Chapter 4 Data structure 初探数据结构

## Chapter5 Recursion 再探递归

## Chapter6 Array 数列

## Chapter7 Array ADT 数列-抽象数据结构

## Chapter8 String 字符串

## Chapter9 Special Matrix 特殊矩阵

## Chapter10 Sparse Matrix 稀疏矩阵

## Chapter11 Linked list 链表