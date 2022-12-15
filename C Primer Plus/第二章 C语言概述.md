# 第二章 C语言概述



## 复习题

1. C语言的基本模块是什么？

C语言的基本模块通常指的是C语言的函数。C语言的函数可以被定义为由一系列语句组成的独立的、可重复使用的代码块，它们可以被程序的其他部分调用来完成特定的任务。



2.什么是语法错误？写出一个英语例子和C语言例子。

语法错误（syntax error）是指程序中出现的不符合语言语法规则的错误。

下面是一个英语语法错误的例子：

"I goes to the store."

在这个例子中，使用了错误的动词形式，应该是"I go to the store."

C语言中的一个语法错误的例子是：

```c
Copy code
#include <stdio.h>

int main()
{
  printf("Hello world!\n);
  return 0;
}
```

在这个例子中，`printf()`函数的结束括号缺失了，应该是这样：

```c
Copy code
#include <stdio.h>

int main()
{
  printf("Hello world!\n");
  return 0;
}
```

如果程序中存在语法错误，编译器在编译程序时将会报错，并指出错误所在的位置。



3.什么是语义错误？写出一个英语例子和C语言例子。

语义错误（semantic error）是指程序中出现的不符合语言语义规则的错误。语义错误与语法错误不同，它不会导致编译错误，但会导致程序的错误行为。

下面是一个英语语义错误的例子：

"I give my mom a hug and a kiss on the cheek."

在这个例子中，由于逻辑上的错误，导致了语义错误。通常，人们会在脸颊上亲吻，而不是在肩膀上。因此，正确的表述应该是"I give my mom a hug and a kiss on the cheek."

C语言中的一个语义错误的例子是：

```c
Copy code
#include <stdio.h>

int main()
{
  int x = 10;
  int y = 5;
  int z = x / y;

  printf("%d\n", z);
  return 0;
}
```

在这个例子中，程序错误地将`x`和`y`的值相除，应该是将`x`和`y`的值相乘。因此，正确的代码应该是这样：

```c
Copy code
#include <stdio.h>

int main()
{
  int x = 10;
  int y = 5;
  int z = x * y;

  printf("%d\n", z);
  return 0;
}
```

语义错误往往比语法错误难以查找和修复，因为它们不会导致编译错误，程序可能会按照错误的方式运行，导致结果不正确或程序崩溃。



4.Indiana Sloth编写了下面的程序，并征求你的意见。请帮助他评定。

```c
include studio.h
int main{void} /* 该程序打印一年有多少周 /*
(
     int s

     s := 56;
     printf(There are s weeks in a year.);
     return 0;
```

这份代码存在多个错误。

首先，`#include`语句中的关键字`include`和文件名`studio.h`应该写成一行，并且文件名应该写成`stdio.h`。

```
#include <stdio.h>
```

其次，`main`函数的声明应该是`int main(void)`，而不是`int main{void}`。

```
int main(void)
```

此外，`main`函数内部的注释应该使用`/*`和`*/`来定义，而不是`/* 该程序打印一年有多少周 /*`。

```
/* 该程序打印一年有多少周 */
```

最后，`printf`函数的调用应该使用格式字符串来指定输出内容，并且字符串末尾应该使用双引号而不是单引号。

```
printf("There are %d weeks in a year.\n", s);
```

因此，修正后的代码应该是这样的：

```c
#include <stdio.h>

int main(void)
{
  /* 该程序打印一年有多少周 */
  int s;

  s = 56;
  printf("There are %d weeks in a year.\n", s);
  return 0;
}
```



5.假设下面的4个例子都是完整程序中的一部分，它们都输出什么结果？

```c
a. printf("Baa Baa Black Sheep.");
   printf("Have you any wool?\n");
b. printf("Begone!\nO creature of lard!\n");
c. printf("What?\nNo/nfish?\n");
d. int num;
   num = 2;
   printf("%d + %d = %d", num, num, num + num);
```

对于这四个例子，它们的输出结果如下：

a.

```c
Baa Baa Black Sheep.Have you any wool?
```

b.

```c
Begone!
O creature of lard!
```

c.

```c
What?
No/nfish?
```

d.

```c
2 + 2 = 4
```

对于第一个例子，由于没有使用换行符，因此输出的两行字符串会连在一起。

对于第二个例子，由于使用了换行符，因此输出的两行字符串会在不同的行上。

对于第三个例子，由于输出的字符串中含有转义序列`\n`，因此输出的字符串中会出现换行符。

对于第四个例子，由于使用了格式字符串来指定输出内容，因此程序会根据格式字符串的规定，将变量`num`的值插入到输出字符串中。



6.在main、int、function、char、=中，哪些是C语言的关键字？

在这些单词中，`int`、`char`和`function`都是C语言的关键字。

C语言的关键字（keywords）是C语言中已经被预定义的、具有特殊含义的单词，它们不能被用作用户定义的变量名或函数名。

C语言中共有32个关键字，它们分别是：`auto`、`break`、`case`、`char`、`const`、`continue`、`default`、`do`、`double`、`else`、`enum`、`extern`、`float`、`for`、`goto`、`if`、`inline`、`int`、`long`、`register`、`restrict`、`return`、`short`、`signed`、`sizeof`、`static`、`struct`、`switch`、`typedef`、`union`、`unsigned`、`void`、`volatile`、`while`。

`main`和`=`都不是C语言的关键字。

`main`是C语言程序的入口函数，它是用户定义的，不属于C语言的关键字。

`=`是赋值运算符，它用来将右侧表达式的值赋给左侧变量，也不属于C语言的关键字。



7.如何以下面的格式输出变量words和lines的值（这里，3020和350代表两个变量的值）？

```c
There were 3020 words and 350 lines.
```

下面是在 C 语言中以给定格式输出变量值的示例代码：

```c
#include <stdio.h>

int main() {
  int words = 3020;
  int lines = 350;
  printf("There were %d words and %d lines.\n", words, lines);
  return 0;
}
```

在这个程序中，我们声明了两个变量：`words` 和 `lines`。然后，我们使用 `printf()` 函数来输出变量值，并指定了输出格式。

在格式字符串中，`%d` 指示 `printf()` 函数将在该位置输出一个整数。因此，我们在格式字符串中指定了两个 `%d` 占位符，以便输出 `words` 和 `lines` 两个变量的值。

如果运行上面的代码，它会产生如下输出：

```c
There were 3020 words and 350 lines.
```

在这个例子中，我们使用了 `printf()` 函数来指定格式并输出变量值。我们通过指定 `%d` 占位符来指定了输出格式，以便将变量值输出到指定位置。



8.考虑下面的程序：

```c
#include <stdio.h>
int main(void)
{
      int a, b;

      a = 5;
      b = 2; /* 第7行 */
      b = a; /* 第8行 */
      a = b; /* 第9行 */
      printf("%d %d\n", b, a);
      return 0;
}
```

请问，在执行完第7、第8、第9行后，程序的状态分别是什么？

答：

程序中定义了两个变量`a`和`b`，它们的初始值都是0。

在执行第7行后，变量`b`的值被改为2，所以程序的状态是这样的：

```c
a = 5;
b = 2;
```

在执行第8行后，变量`b`的值被改为变量`a`的值，即5，所以程序的状态是这样的：

```c
a = 5;
b = 5;
```

在执行第9行后，变量`a`的值被改为变量`b`的值，即5，所以程序的状态是这样的：

```c
a = 5;
b = 5;
```

综上所述，在执行完第7、第8、第9行后，程序的状态是这样的：

```c
a = 5;
b = 5;
```

因此，程序的输出结果是：

```c
5 5
```



9．考虑下面的程序：

```c
#include <stdio.h>
int main(void)
{
      int x, y;

      x = 10;
      y = 5;        /* 第7行 */
      y = x + y;    /*第8行*/
      x = x*y;      /*第9行*/
      printf("%d %d\n", x, y);
      return 0;
}
```

请问，在执行完第7、第8、第9行后，程序的状态分别是什么？

答：

程序中定义了两个变量`x`和`y`，它们的初始值都是0。

在执行第7行后，变量`x`的值被改为10，变量`y`的值被改为5，所以程序的状态是这样的：

```c
x = 10;
y = 5;
```

在执行第8行后，变量`y`的值被改为`x`加上`y`的值，即10 + 5 = 15，所以程序的状态是这样的：

```c
x = 10;
y = 15;
```

在执行第9行后，变量`x`的值被改为`x`乘上`y`的值，即10 * 15 = 150，所以程序的状态是这样的：

```c
x = 150;
y = 15;
```

综上所述，在执行完第7、第8、第9行后，程序的状态是这样的：

```c
x = 150;
y = 15;
```

因此，程序的输出结果是：

```c
150 15
```



## 编程练习

1．编写一个程序，调用一次printf()函数，把你的名和姓打印在一行。再调用一次printf()函数，把你的名和姓分别打印在两行。然后，再调用两次printf()函数，把你的名和姓打印在一行。输出应如下所示（当然要把示例的内容换成你的名字）：

```c
#include <stdio.h>

int main(void)
{
  // 第1次打印
  printf("Nick Ho\n");

  // 第2次打印
  printf("Nick\n");
  printf("Ho\n");

  // 第3次和第4次打印
  printf("Nick Ho\n");
  printf("Nick Ho\n");

  return 0;
}
```

在这个程序中，我们首先调用了一次 `printf()` 函数，打印出名和姓。然后，我们再次调用了两次 `printf()` 函数，分别打印出名和姓。最后，我们再次调用了两次 `printf()` 函数，将名和姓打印在一行。

如果运行上面的代码，它会产生如下输出：

```c
Nick Ho
Nick
Ho
Nick Ho
```

在这个代码中，我们首先调用了一次 `printf()` 函数，将名和姓打印在一行。然后，我们再次调用了两次 `printf()` 函数，分别打印出名和姓。最后，我们再次调用了两次 `printf()` 函数，将名和姓打印在一行。

在这个代码中，我们使用了 `\n` 字符来换行。在格式字符串中，`\n` 字符表示换行符，它会使 `printf()` 函数在输出时换行。因此，我们可以使用 `\n` 字符来控制换行

2. 编写一个程序，打印你的姓名和地址。

```c
#include <stdio.h>

int main(void)
{
  // 打印姓名和地址
  printf("My name is NickHo.\n");
  printf("My address is HongKong\n");

  return 0;
}
```

在这个程序中，我们首先调用了 `printf()` 函数来打印姓名，然后再次调用 `printf()` 函数来打印地址。

如果运行上面的代码，它会产生如下输出：

```c
My name is NickHo.
My address is HongKong
```

在这个例子中，我们使用了两次 `printf()` 函数来打印姓名和地址。我们通过调用 `printf()` 函数并指定要输出的内容来实现这一目的。在这个程序中，我们没有使用任何特殊的格式字符串，只是指定了要输出的字符串。

3. 编写一个程序把你的年龄转换成天数，并显示这两个值。这里不用考虑闰年的问题。

```c
#include <stdio.h>

int main(void)
{
  // 定义年龄和天数的变量
  int age, days;

  // 计算天数
  age = 25;
  days = age * 365;

  // 打印年龄和天数
  printf("My age is %d and my age in days is %d.\n", age, days);

  return 0;
}
```

在这个程序中，我们首先声明了一个名为 `age` 的变量，并将它的值初始化为 27。然后，我们计算出该变量的值表示的天数，并将结果保存在另一个变量 `days` 中。

最后，我们使用 `printf()` 函数打印 `age` 和 `days` 两个变量的值。我们在格式字符串中指定了两个 `%d` 占位符，以便将 `age` 和 `days` 两个变量的值输出到指定位置。

如果运行上面的代码，它会产生如下输出：

4. 编写一个程序，生成以下输出：

```c
For he's a jolly good fellow!
For he's a jolly good fellow!
For he's a jolly good fellow!
Which nobody can deny!
```

除了main()函数以外，该程序还要调用两个自定义函数：一个名为jolly()，用于打印前3条消息，调用一次打印一条；另一个函数名为deny()，打印最后一条消息。

```c
#include <stdio.h>

// 定义jolly()函数，用于打印前3条消息
void jolly(void)
{
  printf("For he's a jolly good fellow!\n");
}

// 定义deny()函数，用于打印最后一条消息
void deny(void)
{
  printf("Which nobody can deny!\n");
}

int main(void)
{
  // 调用jolly()函数3次
  jolly();
  jolly();
  jolly();

  // 调用deny()函数
  deny();

  return 0;
}
```

上面这段代码定义了两个函数：`jolly()` 和 `deny()`。前者用于打印 "For he's a jolly good fellow!"，后者用于打印 "Which nobody can deny!"。

在 `main()` 函数中，我们调用了 `jolly()` 函数三次，用于打印前三条消息。然后再调用一次 `deny()` 函数，用于打印最后一条消息。

每个函数的参数列表都用 `void` 表示，表示这两个函数不需要接收任何参数。

最后，在 `main()` 函数中，我们返回 0，表示程序正常结束。



5.编写一个程序，生成以下输出：

```c
Brazil, Russia, India, China
India, China
Brazil, Russia
```

除了main()以外，该程序还要调用两个自定义函数：一个名为br()，调用一次打印一次“Brazil, Russia”；另一个名为ic()，调用一次打印一次“India, China”。其他内容在main()函数中完成。

```c
#include <stdio.h>

void br() {
    printf("Brazil, Russia\n");
}

void ic() {
    printf("India, China\n");
}

int main() {
    br();
    ic();
    br();

    return 0;
}
```

上面这段代码定义了两个函数：`br()` 和 `ic()`。前者用于打印 "Brazil, Russia"，后者用于打印 "India, China"。

在 `main()` 函数中，我们调用了 `br()` 函数两次，用于打印 "Brazil, Russia" 两次。然后再调用一次 `ic()` 函数，用于打印 "India, China"。



6．编写一个程序，创建一个整型变量toes，并将toes设置为10。程序中还要计算toes的两倍和toes的平方。该程序应打印3个值，并分别描述以示区分。

```c
#include <stdio.h>

int main() {
  // 定义变量toes，并设置为10
  int toes = 10;

  // 计算toes的两倍和toes的平方
  int twice_toes = toes * 2;
  int square_toes = toes * toes;

  // 打印三个值
  printf("toes = %d\n", toes);
  printf("twice_toes = %d\n", twice_toes);
  printf("square_toes = %d\n", square_toes);

  return 0;
}
```

在这个程序中，我们定义了一个变量 `toes`，并将它的值设置为 10。然后，我们计算了 `toes` 的两倍和平方，并将结果保存到两个变量中：`twice_toes` 和 `square_toes`。

最后，我们使用 `printf()` 函数打印了这三个值，并在每个值的前面添加了一个描述性的标签，以区分这三个值。

如果运行上面的代码，它会产生如下输出：

```c
toes = 10
twice_toes = 20
square_toes = 100
```



7.许多研究表明，微笑益处多多。编写一个程序，生成以下格式的输出：

```c
Smile!Smile!Smile!
Smile!Smile!
Smile!
```

该程序要定义一个函数，该函数被调用一次打印一次“Smile!”，根据程序的需要使用该函数。

```c
#include <stdio.h>

// smile() 函数，用于打印一次 "Smile!"
void smile(void) {
  printf("Smile!");
}

int main() {
  // 调用 smile() 函数3次
  smile();
  smile();
  smile();
  printf("\n");

  // 调用 smile() 函数2次
  smile();
  smile();
  printf("\n");

  // 调用 smile() 函数1次
  smile();
  printf("\n");

  return 0;
}
```

上面这段代码定义了一个函数 `smile()`，用于打印一次 "Smile!"。在 `main()` 函数中，我们调用了这个函数三次，两次，和一次，分别打印了上面要求的三行文本。

每次调用 `smile()` 函数时，我们都使用 `printf()` 函数打印了 "Smile!"。为了让输出的每一行都有相同的格式，我们在每行的末尾都添加了换行符 `\n`。

8.在C语言中，函数可以调用另一个函数。编写一个程序，调用一个名为one_three()的函数。该函数在一行打印单词“one”，再调用第2个函数two()，然后在另一行打印单词“three”。two()函数在一行显示单词“two”。main()函数在调用one_three()函数前要打印短语“starting now:”，并在调用完毕后显示短语“done!”。因此，该程序的输出应如下所示：

```c
starting now:
one
two
three
done!
```

在这个程序中，我们定义了两个函数：`two()` 和 `one_three()`。`two()` 函数只打印 "two" 这个单词，而 `one_three()` 函数打印 "one" 和 "three"，并调用 `two()` 函数来打印 "two"。

在 `main()` 函数中，我们先打印 "starting now:"，然后调用 `one_three()` 函数，最后打印 "done!"。这些语句按顺序执行，并且按照题目要求输出了所有的文本。
