# Poirot
#C语言学习史
#include<stdio.h>
int main()
{
	extern int g_val;//全局变量的作用域为整个工程
	printf("g_val=%d\n", g_val);
	return 0;
}

#include<stdio.h>
#define MAX 10//其定义的标识符常量
int main()
{
	int arr[MAX] = { 0 };
	printf("%d\n", MAX);
	return 0;
}

#include<stdio.h>//枚举常量—一一列举
//枚举关键字enum
enum Sex
{
	female, male, secret//枚举常量
	};
int main()
{
	//enum Sex s = female;

	printf("%d\n", male);
	printf("%d\n", female);
	printf("%d\n", secret);
	return 0;
}
#include<stdio.h>
#include<string.h>
int main()
{
	char arr1[] = "abc";
	char arr2[] = { 'a','b','c'};
	printf("%d\n", strlen(arr1));//输出字符型数组1的字符串长度

printf("%d\n", strlen(arr2));//随机值
return 0;
}
#include<stdio.h>
int main()
{
	int a = 1;
	int b = a << 2;//左移二进制数a的两位操作符，此时b为4
	printf("%d\n", b);
	printf("%d\n", a);
	return 0;
}


#include<stdio.h>
int main()
{
	int a = 6;
	int b = 5;
	int c = a | b;//按位或
	int d = a & b;//按位与
	printf("%d", c);
	printf("%d", d)
	return 0;
}

#include<stdio.h>
int main()
{
	int a = 10;
	printf("%d\n", !a);//!逻辑反操作
	printf("%d\n", sizeof(a));//4,变量大小时可以省略小括号
	printf("%d\n", sizeof(int));//sizeof计算的是变量或者类型所占空间的大小，单位是字节
	int arr[10] = { 0 };
	//10*sizeof(int)=40
	printf("%d\n", sizeof(arr));//求出其数组的空间大小40
	int c=0;
	c = sizeof(arr) / sizeof(arr[0]);//数组的总空间大小除以每一个数组元素的大小就等于此数组中元素的个数
	printf("c=%d\n", c);			
	return 0;

}

#include<stdio.h>
int main()
{

	int a = 10;
	int d = 6;
	int b = a++;//后置加加，先把a赋值给b然后再自加，即先使用后加加
	int c = ++d;
	printf("a=%d b=%d\n", a, b);
	printf("c=%d d=%d\n", c, d);
	return 0;
}


#include<stdio.h>
int main()
{
	int a = (int)3.14;//强制类型转换将double类型转换为int整形
	int b = 0;
	int c = 5;
	int e = 6;
	printf("%d\n", b && c);//逻辑与，逻辑或
	printf("%d", c || e);
	return 0;
}



#include<stdio.h>
void test()
{
	static int a = 1;//静态的修饰局部变量，局部变量的生命周期变长
	a++;
	printf("a=%d\n", a);

}

int main()
{
	int i = 0;
	while (i < 5)
	{
		test();
		i++;
	}


	return 0;
}



//define 定义标识符常量和宏
#include<stdio.h>
#define MAX 100
int Max(int x, int y)
{
	if (x > y)
		return x;
	else
		return y;

}
#define MAX(X,Y) (X>Y? X:Y)//定义的这个宏会替换成后面这个表达式
int main()
{
	//int a = MAX;
	int a = 19;
	int b = 20;
	//函数
	int  max = Max(a, b);
	printf("max=%d\n", max);
	//宏的方式
	max = MAX(a, b);//里面的实参传递给形参
	printf("max=%d\n", max);
	return 0;
}


//有一种变量是用来存放地址的-指针变量
#include<stdio.h>
int main()
{
	int a = 10;//在内存中创建一个空间，将此空间命名为a，且该空间内存储的数据为10
	int *p = &a;//在内存中创建另一个空间，将此空间命名为p，该空间内存储a的地址符
	//*p = 20;//*解引用操作符，即把a空间内的数据变成了20
	printf("%d\n", a);//输出数值a
	printf("%p\n", p);//输出%p为取地址符 a的地址已经存储到P里面去了
	//printf("%d\n", sizeof(p));//32个平台上指针大小是4个字节，64个平台大小上是8个字节
	return 0;
}
#include<stdio.h>
#include<string.h>
//创建一个结构体
struct Book
{
	char name[20];
	short price;
};
int main()
{    //利用结构体类型创建一个该类型结构体变量
	struct Book b1 = { "C语言程序设计",55 };
	//struct Book *pb = &b1;
	strcpy(b1.name, "C++");//字符串拷贝-库函数
	printf("书名：%s\n", b1.name);
	//printf("价格：%d元\n",b1.price);
	//b1.price = 25;
	//printf("修改后价格：%d元\n",b1.price);
	//结构体指针->成员
	//结构体变量.成员
	printf("书名：%s\n", pb->name);
	printf("价格：%d\n", pb->price);
	printf("%s\n", (*pb).name);
	printf("%d", (*pb).price);
	return 0;
}
