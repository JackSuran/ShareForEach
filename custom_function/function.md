# 自定义函数
## 自定义函数长什么样
认识一个新事物我们总是要从他们的样貌开始的嘛。那么就让我们来认识一下我们的新朋友`自定义函数`
***

### 自定义函数的定义
自定义函数的定义（创建）语法由下面的几部分构成
`返回值类型`+`函数标识符`(函数的名字)+`传入参数`以及 { `函数体` }

例如：
``` C
int AddTwoNumber(int num1,int nun2)
{
    int sum = num1 + num2;
    retuen sum;
}
```

![函数构成](/Image/function.png "函数构成")

### 自定义函数的调用

在C语言，**所有程序**都是从main函数开始的，因此main函数又被称为`入口函数`

那我们的自定义函数什么时候才能**被使用**呢？

这就需要我们去`调用`它啦

调用的语法：
`函数标识符`+`(传入参数)`

![函数调用](/Image/Dofunction.png "函数调用")

代码示例：
``` C
#include<stdio.h>

int AddTwoNumber(int num1,int nun2)
{
    int sum = num1 + num2;
    retuen sum;
}

int main()
{
    int sum;
    int a = 10;
    int b = 20;

    sum = AddTwoNumber(a,b);
    printf("sum = %d",sum);

    return 0;
}
```
### 返回值类型
返回值就是经过你自定义函数的操作之后，你的函数需要对外界做的回应。

还是看回这个例子：
``` C
#include<stdio.h>

int AddTwoNumber(int num1,int nun2)
{
    int sum = num1 + num2;
    retuen sum;
}

int main()
{
    int sum;
    int a = 10;
    int b = 20;

    sum = AddTwoNumber(a,b);
    printf("sum = %d",sum);

    return 0;
}
```
在这个例子中，我们可以知道`AddTwoNumber`函数的功能是把传入的2个整型数据加工成他们的和，并以int类型的sum的形式传递出去`retuen sum;` 

传递出去的东西总得有别的一个东西来接收吧
在这个例子中是由main函数中的`sum`来接收`AddTwoNumber`函数返回的数据

会有点绕，对不对？
简单来说，如果你自定义的函数是有返回值的，**你可以把函数的调用部分看成返回值**

**比如：`sum = AddTwoNumber(a,b);`可以看成`sum = sum;`**
其中第一个sum是main函数里面的，第二个是`AddTwoNumber`函数返回的

这样有没有好理解一些些咧👀

***

可能你看到这些奇奇怪怪的名词是会有些不知所云。但没有关系，就跟人与人之间的关系差不多，多跟Ta打打交道，多麻烦Ta做事，慢慢你们就会熟悉的了。同样，你们也会喜欢上自定义函数的ヽ(￣ω￣(￣ω￣〃)ゝ

## 自定义函数有什么用
我相信有部分会同学对`函数`这个概念感到疑惑。很大一部分原因就是因为`函数`叫做“函数”。我们来看看函数的英文"function"。如果你们来翻译的话，我想大部分同学都会选择“功能”。到这里，相信大家都会或多或少的有种明悟的感觉。

**没错，`函数`就是实现某个功能的东西。**

以我们最先了解的`printf`函数为例。顾名思义，这个函数就是把信息打印在`控制台`(那个黑框框)上的。

***

### 自定义函数初体验
简单知道它的样子后，我们来尝试性地和它打打交道吧

#### 求和并输出

``` C
#include<stdio.h>

int main()
{
    int sum;
    int a = 10;
    int b = 20;

    sum = a + b;
    printf("sum = %d+%d=%d\n",a,b,sum);

    return 0;
}
```
显然，这个主main里面实现了a与b相加，并输出想要的数据。相信这对大家都不是什么难题。让我们增加一点点难度
``` C
#include<stdio.h>

int main()
{
    int sum;
    int a = 10;
    int b = 20;

    int c = 30;
    int d = 40;

    int e = 50;
    int f = 60;

    sum = a + b;
    printf("sum = %d+%d=%d\n",a,b,sum);

    sum = c + d;
    printf("sum = %d+%d=%d\n",c,d,sum);

    sum = e + f;
    printf("sum = %d+%d=%d\n",e,f,sum);

    return 0;
}
```
虽然变量和行数多了一些，但我相信这同样难不倒大家。但如果现在让你进行100+个数据两两求和并输出呢？恐怕大家会不太乐意了吧，因为按照上面这种方式处理的话太繁复了。
怎么处理好一些呢？让我们试试看自定义函数吧！
``` C
#include<stdio.h>

// 这个就是函数的定义啦            // 返回值类型：void(无返回值型)
void myAddFunc(int num1,int num2) // 函数标识符：myAddFunc
{                                 // 传入参数：int类型的num1 int类型的num2
    int sum = num1 + num2;
    printf("sum = %d+%d=%d\n",num1,num2,sum);
}

int main()
{
    int a = 10;
    int b = 20;

    int c = 30;
    int d = 40;

    int e = 50;
    int f = 60;

    myAddFunc(a,b); // 这里是函数的调用
    myAddFunc(c,d);
    myAddFunc(e,f);

    return 0;
}
```

怎么样，通过对比这两段相同作用（功能）的代码？

#### 动手试一试
1. 自定义一个加法函数，实现对两数求和并输出`sum = %d+%d=%d\n`
2. 自定义一个减法函数，实现对两数求差并输出`differance = %d-%d=%d\n`
3. 自定义一个乘法函数，实现对两数求积并输出`product = %d*%d=%d\n`
4. 自定义一个除法函数，实现对两数求商并输出`quotient = %d/%d=%d\n`
5. 在main函数中调用你定义的四个函数并校验结果。
### 为什么要用自定义函数呢
我们来看看下面这段代码：
``` C
#include<stdio.h>

int main()
{
    int lenth_1,lenth_2,lenth_3; // 正方形1的边长 正方形2的边长 正方形3的边长
    int area_1，area_2,area_3 // 正方形1的面积 正方形2的面积 正方形3的面积

    scanf("%d",&lenth_1); // 获取三个正方形的边长
    scanf("%d",&lenth_2);
    scanf("%d",&lenth_3);

    area_1 = lenth_1 * lenth_1; // 分别计算面积
    area_2 = lenth_2 * lenth_2;
    area_3 = lenth_3 * lenth_3;

    printf("area_1+area_2+area_3=%d",area_1+area_2+area_3); // 输出想要的结果

    return 0;
}
```
很明显，它的目的是计算三个正方形相加的结果。同理，如果要运算多次的话会进行大量的复制粘贴。这样子会让main函数**又臭又长**。为了避免影响代码可读性以及可维护性。让我们来试试看把这个**功能**抽象成`函数`吧。

``` C
#include<stdio.h>

void func(int l1,int l2,int l3)
{
    int area_1，area_2,area_3;

    area_1 = l1 * l1;
    area_2 = l2 * l2;
    area_3 = l3 * l3;

    printf("area_1+area_2+area_3=%d",area_1+area_2+area_3);
}

int main()
{
    int lenth_1,lenth_2,lenth_3;

    scanf("%d",&lenth_1);
    scanf("%d",&lenth_2);
    scanf("%d",&lenth_3);

    func(lenth_1,lenth_2,lenth_3);

    return 0;
}
```
看到这里你可能会觉得 “这也没缩短多少呀” 

但我们要注意到，你的main函数变得整洁了。换句话说这对我们厘清代码思路、排除错误、进行修改等行为都给予了很大的便利。因为已经把一部分操作抽象出去了。如果排错排到具体自定义函数里面，我们的精力就可以从浩如烟海的主main中抽出来。

## 自定义函数注意事项
- 由于编译器是一行一行地处理代码的，所以当我们的自定义函数在main函数以下定义的话，需要提前向编译器`声明`我有一个自定义变量。
声明的语法：
`函数标识符`+`传入参数`; 
    例如：
    ``` C
    #include<stdio.h>

    AddTwoNumber(int num1,int nun2); // 这里是函数的声明

    int main()
    {
        int sum;
        int a = 10;
        int b = 20;

        sum = AddTwoNumber(a,b);
        printf("sum = %d",sum);

        return 0;
    }

    int AddTwoNumber(int num1,int nun2)
    {
        int sum = num1 + num2;
        retuen sum;
    }
    ```
- 在编写自定义函数时一定要想清楚函数的返回值类型以及传入的参数
- 调用函数时，传入参数一定要和定义时一一对应
例如：
    ``` C
    int func(int a,double b);

    int main()
    {
        int val1;
        double val2;
        int num1 = 0;
        double num2 = 0.0;

        val1 = func(num1,num2);
        // 以下两种都是错误的
        // val2 = func(num1,num2);
        // val1 = func(num2,num1);

        return 0;
    }
    ```