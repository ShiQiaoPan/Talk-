# Talk-
Hello world
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
=========
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
=========

2.1 短路现象
-----------

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
