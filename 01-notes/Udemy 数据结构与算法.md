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

### 

### Parameter Passing 参数传递

### Class 

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