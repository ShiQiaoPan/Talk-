[使用教程](http://wowubuntu.com/markdown/index.html)<br>
[IOS开发进阶](http://www.cocoachina.com/special/xcode/)<br>
[Swift学习](http://numbbbbb.gitbooks.io/-the-swift-programming-language-/content/index.html)<br>
[苹果软件园](http://www.maczapp.com)<br>
[苹果软件园翻墙](http://www.maczapp.com/zt-翻墙/)<br>
[Coding Guidelines for Cocoa](https://developer.apple.com/library/mac/documentation/Cocoa/Conceptual/CodingGuidelines/CodingGuidelines.html)<br>
[IOS编码规范](https://github.com/Smeegol/Objective-C-Coding-Style-Guidelines)<br>
[IOS视频学习](http://wenku.baidu.com/course/study/9f8568eae009581b6bd9ebc7#9f8568eae009581b6bd9ebc7)<br>
[高清图片](www.1x.com)
1、产生随机数
====
首先包含库文件 #include  <<stdlib.h>stdlib.h> <br/>
 #define  random(x)(rand ()%x)//宏定义
 ```c

void suiji(int x ,int y){//产生y范围内x个随机数   
      
       int num = x;
       int a[20];//可以定义个数组然后冒泡排序输出
    for(int i = 0;i < num;i++)
    {printf("%d\n",random(y));
}
```
<font color=red>高亮</font>//font color=red>(显示的内容)  /font>

 包含库文件#define <<time.h>time.h><br>
 
srand((unsigned int)time(NULL));//可以随时间变化产生随机数<br>
char a = 'a' + rand()%4 rand%4可以得到0-3之内的数---取余
2 、短路现象
====

2.1 短路现象
----

void test2() {

    int i = 5,j = 9;
    ****************************
    i == 5||j++;//前面真，不执行后面的语句j = 9
    ****************************
    printf("j = %d\n",j);
    j/=2-1;//从右至左先减
    printf("%d",j);
}
2.2
----
变量赋初值<br>
1）    int sum = 0, sum1 = 0;<br>
2)   int sum, sum1;sum = sum1 = 0;<br>
3)   错误的   int sum = sum1 = 0;

3、for循环嵌套
====
外层循环控制行数内层控制列数

(2层循环输出平面图形3层输出立体)
*****
学会使用制表符————————>九九乘法表
*****

4、数组
====
数组长度为变量的时候不能这样初始化<br>
```c
int number = 3;
int array[number] = {0};
```

这个需要用指针来动态分配内存，比如

int size = 8;
int *nums;
nums = (int *)malloc(sizeof(int)*size);

4.1 求数组长度
----
 int array[] = {1, 1, 2, 3};<br>
 int length = sizeof(array)/sizeof(int);<br>int length = sizeof(array)/sizeof(array[1])//不知道数组长度求之 
4.2 字符串
-----
scanf输入：scanf以空格结束没法录入空格<br>
gets()输入超界了会出问题 ——————> fgets() <br>
puts()输出<br>
strlen ----->字符串长度
strcpy ----->复制字符串
strcat ----->拼接字符串
strcmp ----->比较字符串

4.3
----
int arr[] = {3, 3, 3, 3, 3, 3, 5, 5, 5, 5, 5, 4, 4, 4, 4, 4, 0, 0, 0, 0, 0, 0, 4, 4, 4, 4};
    
    int length = sizeof(arr) / sizeof(arr[0]); // 数组长度
    
    int max = arr[length - 1]; // 存储最大值
    int index = 1;   // 记录当前倍率
    int sum = arr[length - 1]; // 记录当前连续数的总和
    
    for (int i = length - 1; i > 0; i --) {
        
        if (arr[i] == arr[i - 1]) {
            
            index *= 10; // 扩大倍率
            sum += arr[i - 1] * index; // 更新所表示的十进制数
            // 防止第0位判断不到
//            if (max < sum) {
//                
//                max = sum;
//            }
            
            continue;
        }
        if (arr[i] != arr[i - 1]) {
            
            // 更新最大值
            if (max < sum) {
                
                max = sum;
            }
            // 重置倍率与十进制总和
            index = 1;
            sum = arr[i - 1];
        }
    }
    
    printf("max = %d", max);


}
5.函数
====
函数声明在调用之前

宏定义 参数名大写单词之间_连接<br>

define MAX(a, b) a  > b ? a : b 不用定义类型<br>
***
define MUL(a, b) (a) * (b)  MUL (2 + 2, 4) = 4 * 4<br>
define MUL(a, b) a * b   MUL(2 + 2, 4) = 2 + 2 * 4<br>
***
static 静态变量只执行一次
****
形参和实参
交换2个数-----经典<br>
****使用指针

递归调用n!


int f(int n) {
    
    int sum = 1;
    if (n > 0){
    sum *= n * f(n - 1);
    }
 }
 
 
 int f(int n) {
    
    int sum;
    if (n < 0) {
        printf("error");
    }
    else if (n == 1 || n == 0){
        sum = 1;
    } else {
        sum = f(n - 1) * n;
    }
    return sum;
}

6、指针
====
#include <stdio.h>

// 指针的定义与初始化
void test1() {
    
    int a = 10;
    
    // 无论什么类型的指针，都占8个字节
    int *p;
    char *pChar;
    double *pD;
}

void test2() {
    
    int a = 1;
    char b = 2;
    
    int *p = &b;
    
    printf("%d", *p);
}

void test3() {
    
    // 野指针异常
    int *p;
    *p = 3;
    
    // 空指针异常
    int *q = NULL;
    *q = 3;
}

void test4() {
    
    int a = 10;
    int *p = &a;
    
    // int *p; // 定义一个指针：*p是地址
    
    // *p = 4; // 使用的时候：*p是p指向的地址的值
    // p = &b; // p在使用的时候：p表示地址
    
    a = 11;
    *p = 12;
    printf("a = %d", *p);
}

void test5() {
    
    int a = 3, b = 5, sum = 0;
    int *pA = &a, *pB = &b, *pSum = &sum;
    sum = a + b; // 直接求和
    *pSum = *pA + *pB; // 通过指针，间接求和
    printf("sum = %d", *pSum);
}

// 让pA与pB两个指针去接收a和b的地址
void swap(int *pA, int *pB) {
    
    int temp = *pA;
    *pA = *pB;
    *pB = temp;
}

// 交换的是形参的值
void errorSwap1(int a, int b) {
    
    int *pA = &a;
    int *pB = &b;
    
    int temp = *pA;
    *pA = *pB;
    *pB = temp;
}

// 交换的是pA与pB的指向，并没有交换值
void errorSwap2(int *pA, int *pB) {
    
    int *temp = pA;
    pA = pB;
    pB = temp;
}

// 不使用返回值，求两个数的最大值
void getMax(int a, int b, int *max) {
    
    
}


// 指针与数组
void test6() {
    
    int array1[5] = {1, 6, 3, 4, 5};
    int *p = array1;
    
    for (int i = 0; i < 5; i++) {
        
        printf("%d ", *(p + i));
    }
    
    // p        // 指向数组首地址的指针变量
    // p + 1    // 指向第2个元素的地址
    // p[1]     // 指向第2个元素的地址
    // *p + 1   // 第1个元素的值+1
    // *(p + 1) // 访问第二个元素的值
    // p++;     // p指向第2个元素的地址（有一个移动p的操作）
    // *(p++)   // 直接输出时：输出p指向地址的值，然后p向下移动
    // array1   // 数组首地址，常量，不可写
}

void printArray(int *array, int length) {
    
    for (int i = 0; i < length; i++) {
        
        printf("%d ", array[i]);
        printf("%d ", *(array + i));
        printf("%d ", *(array++));
    }
}

// 指针与二维数组
void test7() {
    
    int array[2][3] = {1, 2, 3, 4, 5, 6};
    int (*p)[3] = array;
//    int *q[3];
    
//    printf("%p\n%p\n%p", p, *p, &(**p));
//    printf("array[0][1] = %d", *(*p + 1));
    printf("array[1][2] = %d", *(*(p + 1) + 2));
    
    // (*p)[3] 二维数组的指针（数组指针）
    // *p[3]   指针数组
}

//void test8() {
//    
//    int const a = 10;
//    const int b = 20;
//    
//    int const * p1 = &a;
//    const int * p2 = &a;
//    int * const p3 = &a;
//    int const * const p4 = &a;
//}

void test9(){
    
    char string1[10] = "abc";
    char *string2 = "abc";
    
    //修改内容
    string1[2] = 'd';
    *string2 = "abd";
}

7、结构体
====
struct 名字 {
变量列表
};<br>
typedef struct 名字 新名//以后就可以新名代替struct 名字/给类型取名<br>
大括号整体赋值只能初始化的时候用<br>
malloc ----free配套使用
7、1结构体占字节大小
----
struct stu1 {
    
    char *name;
    int age;
    char gender;
    double score;//占8 + 8 +8 = 24个字节char gender 在最后则32个字节
};

struct stu2 {
    
    char *name;
    char a;
    int b;
    char c;//占24个字节4个寻址最快
};

8、链表
====
//
//  main.c
//  cLesson8
//
//  Created by rimi on 15/6/15.
//  Copyright (c) 2015年 weipan. All rights reserved.
//

 #include <stdio.h><br>
 #include <stdlib.h><br>
 #include <string.h><br>
struct student {
    //数据域
    
    char *id;
    int age;
    //指针域
    struct student *next;//指向下一个结点的指针
};
typedef struct student student;
//函数声明

void append(student *head);//末尾增加函数<br>
void printlink(student *head);//打印函数<br>
void inserAtIndex(student *head, int index);//任意位置插入函数<br>
student * pointAtIndex(student *head, int index);//指针移动函数<br>
void deleteAtIndex(student *head, int index);//删除函数<br>
int indexWithStudentId(student *head, char *id);//查找<br>
//函数实现<br>
void append(student *head) {
    
    student *newstu = (student *)malloc(sizeof(student));
    newstu->next = NULL;
    newstu->id = (char *)malloc(20);
    printf("请输入学号 年龄\n");
    scanf("%s %d", newstu->id, &newstu->age);
    getchar();//清空缓存
    //移动指针
    student *p = head;
    //p指针移向最后一位
    while (p->next != NULL) {
        p = p->next;
    }
    //将新的结点接到尾部
    p->next = newstu;
    return;
}
void printlink(student *head) {
    
    student *p = head;
    while (p->next != NULL) {
        printf("%s %d", p->next->id, p->next->age);
        p = p->next;
    }
    
}
void inserAtIndex(student *head, int index) {
    
    if (index < 1) {
        return;
    }
    student *newstu = (student *)malloc(sizeof(student));
    newstu->next = NULL;
    newstu->id = (char *)malloc(20);
    printf("请输入学号 年龄\n");
    scanf("%s %d", newstu->id, &newstu->age);
    getchar();//清空缓存
    student *p = pointAtIndex(head, index);
    //这2步操作不呢交换顺序
    newstu->next = p->next;//把p的下一结点接到新结点后面
    p->next = newstu;//把新的结点接到p的后面
}
student * pointAtIndex(student *head, int index/* *p */) {//也可以在加入一个p指针
    
    student *p = head;
    for (int i = 0; p->next != NULL && i < index; i++){
        p = p->next;
    }
    return p;
}
void deleteAtIndex(student *head, int index) {
    
    if (index < 1) {
        return;
    }
    student *p = pointAtIndex(head, index - 1);
    student *pDelete = p->next;//要删除的结点
    p->next = pDelete->next;//将第一个结点指向第三个结点
    free(pDelete->id);//先释放id指针的指向区
    free(pDelete);
    
}
//查找已知学号的
int indexWithStudentId(student *head, char *id) {
    
    student *p = head;
    int index = 1;
//    student *newstu = (student *)malloc(sizeof(student));
//    newstu->next = NULL;
//    newstu->id = (char *)malloc(20);
//    newstu->id = (char *)malloc(20);
//    printf("请输入查找的学号\n");
//    scanf("%s", newstu->id);
//    getchar();//清空缓存
    while (p->next != NULL) {
        if (strcmp(p->next->id, id)== 0) {
            return index;
        }
         p = p->next;
        index++;
    }
    return -1;
}
int main(int argc, const char * argv[]) {
    
    student *head = (student*)malloc(sizeof(student));
    //头指针不能改变可以叫const
    head->next = NULL;//防止野指针标记链表结束
    append(head);
    inserAtIndex(head, 1);
    indexWithStudentId(head, '111');
    printlink(head);
    
    return 0;
}
