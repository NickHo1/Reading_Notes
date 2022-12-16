# 第三章 数据和C

## 复习题

1. 指出下面各种数据使用的合适数据类型（有些可使用多种数据类型）：　　

a．East Simpleton的人口　　

b．DVD影碟的价格　　

c．本章出现次数最多的字母　

d．本章出现次数最多的字母次数

答：

a．int类型，也可以是short类型或unsigned short类型。人口数是一个整数。　

b．float类型，价格通常不是一个整数（也可以使用double类型，但实际上不需要那么高的精度）。

c．char类型。　

d．int类型，也可以是unsigned类型。



2. 在什么情况下要用long类型的变量代替int类型的变量？

int 类型的数据范围通常是 -2147483648 到 2147483647。如果需要存储的数据超出了这个范围，则应使用 long 类型的变量。



3. 使用哪些可移植的数据类型可以获得32位有符号整数？选择的理由是什么？

如果要正好获得32位的整数，可以使用int32_t类型。要获得可存储至少32位整数的最小类型，可以使用int_least32_t类型。如果要为32位整数提供最快的计算速度，可以选择int_fast32_t类型



4. 指出下列常量的类型和含义（如果有的话）：　

a．'\b'　

b．1066　

c．99.44　

d．0XAA　　

e．2.0e30

答：

a.'\b' 是一个字符常量，表示退格符。

b. 1066 是一个整数常量，表示数字 1066。

c. 99.44 是一个浮点常量，表示数字 99.44。

d. 0XAA 是一个十六进制整数常量，表示数字 170。

e. 2.0e30 是一个科学计数法表示的浮点常量，表示数字 2.0 × 10^30。



5. Dottie Cawm编写了一个程序，请找出程序中的错误。

```c
include <stdio.h>
main
(
     float g; h;
     float tax, rate;

     g = e21;
     tax = rate*g;
)
```

这段程序中存在几个错误：

1. 在函数 main 的参数列表中缺少括号。应该是：main()。
2. 变量 g 和 h 在定义时没有指定类型，应该在每个变量前添加 float 关键字，如：float g, h;。
3. 变量 rate 在定义之前就被使用了，应该在使用前先定义。
4. 变量 g 被赋值为 e21，但 e21 没有被定义。应该使用有意义的值或常量来赋值。
5. 函数 main 的大括号没有正确的配对。应该是：

```c
#include<stdio.h>
int main() { 
float g, h;
float tax, rate;
rate = 0.15;  // 初始化 rate 变量
 g = 10000;    // 初始化 g 变量
 tax = rate*g; // 计算 tax 变量的值
return 0;
}
```



8. 假设程序的开头有下列声明：

```c
int imate = 2;
long shot = 53456;
char grade = 'A';
float log = 2.71828;
```

把下面printf()语句中的转换字符补充完整:

```c
printf("The odds against the %__ were %__ to 1.\n", imate, shot);
printf("A score of %__ is not an %__ grade.\n", log, grade);
```

答：

```c
printf("The odds against the %d were %ld to 1.\n", imate, shot);
printf("A score of %f is not an %c grade.\n", log, grade);
```



9. 假设ch是char类型的变量。分别使用转义序列、十进制值、八进制字符常量和十六进制字符常量把回车字符赋给ch（假设使用ASCII编码值）。

使用转义序列把回车字符赋给 ch：

ch = '\n';

使用十进制值把回车字符赋给 ch：

ch = 10;

使用八进制字符常量把回车字符赋给 ch：

ch = '\012';

使用十六进制字符常量把回车字符赋给 ch：

ch = '\x0a';



10. 修正下面的程序（在C中，/表示除以）。

```c
void main(int) / this program is perfect /
{
     cows, legs integer;
     printf("How many cow legs did you count?\n);
     scanf("%c", legs);
     cows = legs / 4;
     printf("That implies there are %f cows.\n", cows)
}
```

这段程序中存在几个错误：

1. main 函数声明中的 int 类型是无效的，应删除 int 类型。main 函数应声明为 int main(void) 或者 int main(int argc, char *argv[])。
2. 注释错误：在C语言中注释应该为：/**/
3. 在声明变量 cows 和 legs 时缺少类型。应该声明为：int cows, legs;。
4. printf 语句中缺少右括号。应该修改为：printf("How many cow legs did you count?\n");
5. scanf 语句中使用了 %c 转换字符，但是应该使用 %d 转换字符来读取整数。
6. printf 语句中使用了 %f 转换字符，但是应该使用 %d 转换字符来输出整数。

修正这些错误后，程序应该像这样：

```c
#include <stdio.h>

int main(void)/*this program is perfect*/
{
int cows, legs;
printf("How many cow legs did you count?\n");
scanf("%d", &legs);
cows = legs / 4;
printf("That implies there are %d cows.\n", cows);
 return 0;
}
```



11. 指出下列转义序列的含义：　

a．\n　

b．\\　

c．\"　

d．\t

a. \n 是一个转义序列，表示换行符。

b. \ 是一个转义序列，表示一个反斜杠字符。

c. " 是一个转义序列，表示一个双引号字符。

d. \t 是一个转义序列，表示一个制表符。



## 编程练习

1. 通过试验（即编写带有此类问题的程序）观察系统如何处理整数上溢、浮点数上溢和浮点数下溢的情况。

​	整数上溢是指将一个整数值超过该类型变量能够表示的最大值的情况。浮点数上溢是指将一个浮点数值超过该类型变量能够表示的最大值的情况。浮点数下溢是指将一个浮点数值低于该类型变量能够表示的最小值的情况。

```c
#include <stdio.h>

int main(void)
{
// 整数上溢
int a = 2147483647;
printf("a = %d\n", a);
a = a + 1;
printf("a = %d\n", a);

Copy code
 // 浮点数上溢
 float b = 3.4e38;
 printf("b = %f\n", b);
 b = b * 10;
 printf("b = %f\n", b);

 // 浮点数下溢
 float c = -3.4e38;
 printf("c = %f\n", c);
 c = c / 10;
 printf("c = %f\n", c);

 return 0;
}
```

​	运行程序后，可以看到整数上溢会导致变量 a 的值变成负数；浮点数上溢会导致变量 b 的值变成正无穷大；浮点数下溢会导致变量 c 的值变成负无穷大。

2. 编写一个程序，要求提示输入一个ASCII码值（如，66），然后打印输入的字符。

下面是一个程序的示例，它提示用户输入一个 ASCII 码值，然后打印输入的字符：

```c
#include <stdio.h>

int main(void)
{
	int ascii_code;
	printf("Enter an ASCII code: ");
 	scanf("%d", &ascii_code);

 	printf("The character for ASCII code %d is %c\n", ascii_code, ascii_code);

 return 0;
}
```

运行程序后，会提示用户输入 ASCII 码值。例如，如果输入 66，则会打印字符 'B'。



3. 编写一个程序，发出一声警报，然后打印下面的文本：

```c
Startled by the sudden sound, Sally shouted,
"By the Great Pumpkin, what was that!"
```

```c
#include <stdio.h>

int main(void)
{
printf("\aStartled by the sudden sound, Sally shouted,\n");//使用转义序列 \a
printf(""By the Great Pumpkin, what was that!"\n");
 return 0;
}
```



4. 编写一个程序，读取一个浮点数，先打印成小数点形式，再打印成指数形式。然后，如果系统支持，再打印成p记数法（即十六进制记数法）。按以下格式输出（实际显示的指数位数因系统而异）：

```c
Enter a floating-point value: 64.25
fixed-point notation: 64.250000
exponential notation: 6.425000e+01
p notation: 0x1.01p+6
```

```c
#include <stdio.h>

int main(void)
{
double value;

 printf("Enter a floating-point value: ");
 scanf("%lf", &value);

 printf("fixed-point notation: %f\n", value);
 printf("exponential notation: %e\n", value);
 printf("p notation: %a\n", value);

 return 0;
}
```



5. 一年大约有3.156×107秒。编写一个程序，提示用户输入年龄，然后显示该年龄对应的秒数。

```c
#include <stdio.h>

int main(void)
{
int age;
long seconds;

 printf("Enter your age: ");
 scanf("%d", &age);

 seconds = age * 3.156e7;
 printf("Your age in seconds is %ld\n", seconds);

 return 0;
}
```



6. 1个水分子的质量约为3.0×10−23克。1夸脱水大约是950克。编写一个程序，提示用户输入水的夸脱数，并显示水分子的数量。

```c
#include <stdio.h>

int main(void)
{
double quarts;
long molecules;

 printf("Enter the number of quarts of water: ");
 scanf("%lf", &quarts);

 molecules = quarts / (3.0e-23 / 950.0);
 printf("The number of water molecules is %ld\n", molecules);

 return 0;
}
```

程序首先读取用户输入的水的夸脱数，然后使用常量 3.0e-23 和 950 计算出一夸脱水中的水分子数量。最后，使用 printf 函数打印水分子的数量。



7. 1英寸相当于2.54厘米。编写一个程序，提示用户输入身高（/英寸），然后以厘米为单位显示身高。

```c
#include <stdio.h>

int main(void)
{
double inches;
double cm;

 printf("Enter your height in inches: ");
 scanf("%lf", &inches);

 cm = inches * 2.54;
 printf("Your height in centimeters is %.2f\n", cm);

 return 0;
}
```



8. 在美国的体积测量系统中，1品脱等于2杯，1杯等于8盎司，1盎司等于2大汤勺，1大汤勺等于3茶勺。编写一个程序，提示用户输入杯数，并以品脱、盎司、汤勺、茶勺为单位显示等价容量。思考对于该程序，为何使用浮点类型比整数类型更合适？

```c
#include <stdio.h>

int main(void)
{
double cups;
double pints, ounces, tablespoons, teaspoons;

 printf("Enter the number of cups: ");
 scanf("%lf", &cups);

 pints = cups / 2.0;
 ounces = cups * 8.0;
 tablespoons = cups * 16.0;
 teaspoons = cups * 48.0;

 printf("%.2f cups is equivalent to:\n", cups);
 printf("%.2f pints\n", pints);
 printf("%.2f ounces\n", ounces);
 printf("%.2f tablespoons\n", tablespoons);
 printf("%.2f teaspoons\n", teaspoons);

 return 0;
}
```

使用浮点类型比整数类型更合适的原因是，浮点类型能够表示小数值，而整数类型只能表示整数值。在这个程序中，计算品脱、盎司、汤勺和茶勺的等价容量时，需要使用小数值。如果使用整数类型，则无法准确地计算出等价容量。例如，当输入杯数为 0.5 时，品脱数应该是 0.5，但如果使用整数类型，则品脱数会被视为 0。因此，使用浮点类型能够更准确地计算出等价容量。