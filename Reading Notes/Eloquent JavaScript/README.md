> Written with [StackEdit](https://stackedit.io/).

[toc]
## Chapter 0 - Introduction

我们有两种方式来与外部沟通，一是通过我们的感官，二则是通过计算机。

相对于所见即所得的前者，使用计算机显然是要复杂困难许多。我们并不能用日常习惯地感官方式（视觉认知、动手移动）去指引计算机工作，而是需要借用语言，计算机能理解的语言。

人类语言的复杂性使我们发展出纷繁多样的文化，而计算机语言，尽管没那么复杂，却也依然能创造一个光怪陆离的世界。

Javascript就是这样一门计算机语言。

在走入这门语言之前，Marijn已经提醒到：编程真是件很困难的事，尽管它的基本原理通常是简单直白的。编程要求你能把所知所学的碎片内容都联系在一块，形成一个融洽的整体。

所以初学者可能常常会迷失在这片无常的海洋里，感到一切都那么复杂又支离。或许怀疑自我，或许心灰意冷。

无甚他法，唯独**不要放弃**。歇息一会儿，重新阅读材料，确保自己完全理解之前所学，接着再从头来过。学习是件艰难的事，但你学会的任何东西都是自己的，也都将让你接下来的路变得容易一些。

> 子曰：不愤不启，不悱不发 ；举一隅不以三隅反，则不复也。

程序可以指代很多东西：一段代码、一块数据、或一种驱使电脑工作的力量。

而计算机则是承载程序的宿主。它并不聪明，却让人觉得无所不能。其实这仅仅是因为它能在非常短的时间内处理大量的简单任务而已。

编程的艺术在于**控制程序的复杂度，让它处于自己的掌控之中**。但不少程序员却因此走了极端，从而只愿意生活在程序的舒适区中，恒久地采用所谓“最佳实践”的方案与技术，并将那些愿意冒险的人视作坏的程序员。

然而，电子世界不正因为程序与技术的多样性而显得如此熠熠生辉吗？它确实遍布危险，让新手们充满困惑。但这只是意味着你需要在这条道路上**保持谨慎与理智**。如此，我们将会明白，这个虚幻的空间里总是存在挑战与未知。亦可赛艇，不是吗？

过去的计算机语言可并非现在这样。从机器码到汇编语言，从汇编语言到如今的JavaScript。复杂和细枝末节的东西被逐渐剔除，只留下了我们重视的部分。

一门好的计算机语言，能让程序员们站在一个较高层次来编程，消除不感兴趣的末节，提供一些有用的构建模块（如`while`或`console.log`），并允许我们可以定义自己的模块（如`sum`和`range`函数）。

最后，Marijn谈到他为什么选用JavaScript来教授编程。是的，尽管JavaScript显得变化多端，让人讨厌（比如它的弱类型和异常多的浏览器兼容性问题）。但在另一方面，JavaScript却也因这些问题成就了它自己。

它是一门**自由而普适的语言**（原文里自由指的是flexibility）。

对初学者来说，它是宽容近迂的；而它高度灵活的语言机制则可以让我们实现许多其他严格语言无法实现的技术。

如今，每一个浏览器都在使用JavaScript，所以你大概可以在任何一个地方运行起你的程序。除此之外，在数据库和后台开发方面的长足发展，更是让它的适用范围愈发增广了。

这些都让如今的JavaScript看起来是那么茁壮富有生气，不是吗？

所以，欢迎来到编程世界。

## Chapter 1 - Values, Types, and Operators
 
实际上，一切数据最基础的单位都是比特。比特由二进制表示，只能取0或1。

###  Values

想象一下，当一台计算机中储存了数以百亿计比特的数据时，我们应怎样做才能避免自己迷失在这片数据之海呢？

在JavaScript中，数据被分成了一个个片段（chunks）来表示信息，这被称为值（values）。值本质上都是由比特构成，但不同的值可能会扮演不同的角色。每个值都有从属的类型，用以决定它本身的角色。

在JavaScript中，值有六种基础类型：

1. numbers
2. strings
3. Booleans
4. objects
5. functions
6. undefined values

想要使用这些值，只需简单地唤起它们的名字就行，既不需要什么施法材料，也不需要贡献祭品。但它们并非凭空而生，被召唤出来的值都会以比特形式储存在某一物理位置中。幸运的是，当你不再需要某些值时，它们便会被回收。由此空闲出来的比特将会为新值提供空间。

### Numbers

数值就是数值，没什么需要特别解释的。

JavaScript用64比特的信息来表示一个数值。也就是说在理论上，JavaScript可以表示2^64（18e18）长度的整数（whole numbers/integers）。但事实并非如此，因为JavaScript的数值信息中还需要包含正负号（占用了1比特空间）以及小数点的位置信息，所以实际中它可以表示的整数范围会缩小到9e15，依然大得惊人。

尽管JavaScript能保证9e15范围内整数计算的精确性，却依然无法确保小数（fractional numbers）计算的准确。受到64位比特储存空间的限制，许多小数的计算都将会取**近似值**（比如π）。这是我们应该注意到的地方。

### Arithmetic

Javascript的四则运算规则和通常我们熟知的规则无甚差别，如果感到不确定，添加一个**小括号**提高优先级即可。四则运算操作符（operators）分别是

1. Addition: +
2. Minus: -
3. Multiplication: *
4. Division: /

需要注意的是**%**操作符代表的是取余数，它的优先级和乘除操作符一致。

``` javascript
// Modulo / Remainder
212 % 100
// 12
```

### Special Numbers

JavaScript中有3种特别的数值，分别是

1. 正无穷：`Infinity`
2. 负无穷：`-Infinity`
3. 非数值：`NaN`

正无穷和负无穷很好理解。类似于Infinity - 1的简单四则操作依然会得到Infinity。但基于无穷的运算并没有强健的数学基础，便容易引致`NaN`的出现。

``` javascript
Infinity / Infinity
// NaN
Infinity - Infinity
// NaN
```

除此之外，其他会造成结果不精确、无意义的运算也会得到`NaN`

``` JavaScript
0 / 0
// NaN
```

### Strings

字符串类型用来表示文本。

``` javascript

"Hello World!"
'Hello Moto!'
```

成对出现的双引号或单引号都是用来说明这段数据属于字符串类型。

有些信息难以被直接放入字符串数据中，比如*换行*或者*添加引号*。

这时，我们需要使用转义符号`\`。`\`后紧跟着的字母会具有特别的含义。如`\n`表示换行，`\"`表示这就是一个双引号,`\\`表示这就是一个反斜杠。

```  javascript
"This is the first line\nAnd this is the second"
/*
This is the first line
And this is the second
*/
"A newline character is written like \"\\n\"."
// “A newline character is written like "\n"
```

此外，字符串不能进行四则运算，但可以使用`+`操作符来表示前后链接。

``` javascript
"He" + "llo"
// "Hello"
```

### Unary Operators

并非所有的操作符都是符号，有些也会以单词形式存在，例如`typeof`。这个操作符被用来展现数据的类型。

``` javascript
typeof 4.5
// number
typeof "x"
// string
```

我们之前见过的操作符都会对两个值进行操作，而`typeof`不同，它只会使用一个值。因此，它被视为一元操作符（unary operator），而其他的则被称作二元操作符（binary operator）。

减法操作符可以同时被用做一元操作符和二元操作符。

``` javascript
- （5 - 2）
// -3
```

### Boolean Values

布尔类型只包含两个值: `true`和`false`，用来表示对立关系。

**比较操作（comparisons）**是生成布尔值的一种方法。

``` javascript
5 > 1
// true
2 > 3
// false
```

字符串类型也同样可以进行比较，但需遵守以下两点规则：

1. 字符串中的字母大小按字母表排序，越靠后的字母越大。
2. 大写字母恒小于小写字母。

``` javascript
"a" > "b"
// false
"ac" > "ab"
// true
"a" > "A"
// true
"a" > "Z"
// true
```

事实上，这种比较是基于Unicode标准。这个标准为每一个字符（包括了其他语言，如希腊语，阿拉伯语等）都指定了一个数字。由此使得计算机储存字符信息成为可能。

类似的比较操作符还有：

+ 大于等于：`>=`
+ 小于等于：`<=`
+ 等于：`==`
+ 不等于：`!=`

在JavaScript中，只有一个值**不等于它本身**，那就是`NaN`

``` javascript
NaN == NaN
// false
```

由于NaN表示无意义的计算结果，所以它无法和其他无意义的计算结果相等。

### Logical Operators

另一种生成布尔值的方法就是使用逻辑比较符，前三种分别是：

+ 和：`&&`
+ 并：`||`
+ 非：`!`

第四种逻辑操作符比较有意思，叫三元操作符（ternary operator）：

`[Boolean] ? [value] :  [value]`

这也被称作条件操作符（conditional operator），它将根据问号前的布尔值来选择冒号左右的值。

``` javascript
true ? "hehe" : "meme"
// "hehe"
false ? "hehe" : "meme"
// "meme"
```

### Undefined Values

未定义类型包含了两个特别的值：`null`和`undefined`，被用来表示*缺失有意义的值*。未定义类型不包含任何信息。

在许多操作结束后，由于没有产生有意义的值，所以结果会以`undefined`来代替。这样做仅仅是因为这些操作必须有一个值而已……

为方便理解，`undefined`和`null`在大多数情况下可以被视作同义词。

#### Automatic Type Conversion

之前曾提到过，由于JavaScript具有高度灵活的语言机制，基本上它可以接受并运行你给出的任何代码，甚至是那种看起来奇奇怪怪的。来看看Marijn给的例子：

``` JavaScript
console.log(8 * null)
// → 0
console.log("5" - 1)
// → 4
console.log("5" + 1)
// → 51
console.log("five" * 2)
// → NaN
console.log(false == 0)
// → true
```

当操作符应用在“错误”的数据类型上时，JavaScript会默默地进行数据类型的转化。而它的转化规则却通常是我们不喜欢的……这个过程被称之为类型转换（type coercion）。具体的转化规则其实在《JavaScript权威指南》上讲得比较清楚。

所以我们该如何避免这种烦人的类型转换发生呢？

那就是用`===`代替`==`，`===`符号不仅会检查**值是否相等**，也会检查**数据类型是否一致**。

#### Short-circuiting of Logical Operators

`&&`和`||`逻辑操作符在处理不同类型的值时用的转换方法比较迷离。

`&&`会将左边的值转化为布尔型，若为`false`,那将返回左边的值；若为`true`，那将返回右边的值。

`||`同样是将左边的值转化为布尔型，若为`true`，将返回左边的值；若为`false`，将返回右边的值。

根据这两位的谜之转换方法，我们就能使用一个被称作**短路评估(short-circuit evaluation)**的技术。

在`true || X`中，无论X如何毁天灭地，JavaScript都不会在乎，它总是返回true。

同样，在`false && X`中，无论X如何破碎星辰，JavaScript也都无视，它总是返回false。

这点也同样适用于三元操作符，JavaScript将无视那个被抛弃的可怜孩子……

## Chapter 2 - Program Structure

这章我们终于要来写点真正的小程序了。

### Expressions and statements

我们将一段能创造值的代码片段称为**表达式（expression）**。一个直接写出的值（类似于`11``,"xixi"`）即是表达式的一种。

通过操作符产生的值依然是表达式。这样的做法显现了程序语言*优雅*的一面：我们可以通过组合不同的表达式来表示出任意复杂度的计算。

如果说表达式可以比做人类句子中的成分，那**语句（statement）**即代表了完整的句子。程序其实可以说就是句子的集合。

最简单的语句可以仅仅是一个**以分号做结尾**的表达式：

``` javascript
110;
```

但这样简单的语句的确一没什么意义。我们需要语句的**根本原因**，是在于它能对整个程序产生切实影响（side effects）。譬如，改变程序某处的状态以对后续语句造成影响。而简单的表达式，不过是创造出了一个在诞生之后便泯灭于虚空的值罢了。

在某些情况下，JavaScript允许我们在语句结束后不使用分号做结尾。但此间的规则挺有些复杂（权威指南中有提），所以就目前来说，适宜的方式还是在一段语句结束后**手动添加`;`**。

### Variables

我们通过操作符来从旧值中生成新值，但却无法保留它们。所以，如何“挽留”住一些创生后即可能泯灭的值？

JavaScript使用了**变量（variables）**来勾连和保存值。

``` javascript
var love = "broken heart";
```

关键词（keyword）`var`表明我们要在接下来的语句中定义一个变量，紧随其后的则是这个变量的名字。

``` javascript
var love
```
变量命名的规则：

+ 不能以**数字**开头
+ 不能使用除`$`和`_`之外的符号

如果想**立即**给这个变量赋值，那么就接着使用`=`操作符和一个表达式。

``` javascript
var love = "forever"
```

变量被赋值以后，并不意味它就固定了，我们随时可以用`=`操作符来改变它连接的值。

``` javascript
var love = "forever"
console.log(love)
// "forever"
var love = "nevermore"
console.log(love)
// "nevermore"
```

我们应该把变量比作一只**章鱼**，而非**盒子**。**它并不包含值，而是抓住值**——两个变量可以指向同一个值。

程序只能使用它**保存过的值**。所以如果我们想保存一个值，那就“长出一只触手”去抓住它，或是让已有的“某只触手”改变目标。

一个没有被赋值的变量被称为*空变量*，其默认值为`undefined`。

我们可以一次性定义多个变量，使用`,`隔开即可。

``` javascript
var love = "forever", hurt = "without you"
```

### Keywords and Reserved Words

关键字和保留字都是禁止用来作变量名的，它们在JavaScript中有着特殊含义(关键字)或留作日后版本的JavaScript使用(保留字)。

> break case catch class const continue debugger
default delete do else enum export extends false
finally for function if implements import in
instanceof interface let new null package private
protected public return static super switch this
throw true try typeof var void while with yield

这时候不得不说，有了IDE，什么都不怕……

### The environment

在某个给定时间内存在的变量与它们值的集合被称为**环境(environment)**。当创建新程序时，初始环境并非是空的。它总是包含了一些语言标准要求的起始变量以及一些提供和周围系统进行交互渠道的变量。譬如：

在浏览器中，有一些变量会负责监视和影响已经加载好的页面，并读取鼠标和键盘的输入。

### Functions

在初始环境中被预置的值大多是**函数类型**。函数是一段被包裹进值里面的小程序。这些值可以被**执行(apply)**以激活这段程序。譬如`alert`变量，它所包裹函数的功能是显示一条对话框:

``` javascript
alert("love you!");
// 在浏览器中出现一个包含"love you!"文本的对话框
```

执行一个函数的行为可以被称为*Invoking(祈唤)，calling(调用)或applying(应用)*。

我们通过在一个可以通过**在某个创建函数类型值的表达式后添加`()`**的方式来执行一个函数。

`()`中的值会被传递进函数所包裹的程序中，这就是所谓的**参数(parameters)**。`alert`函数只需要一个任意类型的参数。但其他函数可能需要多个参数，参数的类型也可能不尽相同。

### The console.log function

虽然`aleart`函数作为一个呈现输出结果的端口时比较有用，但这种弹框方式的确让人感到恼火。所以我们通常使用`console.log`函数，它可以将其参数传递给一些文本输出设备。在浏览器中，这个设备被称为**控制台(console)**。如何打开浏览器的控制台？……

``` javascript
var love = "forever"
console.log("love you", love)
// love you forever
```

我们在这里发现了一个有趣的问题：变量名不是不可以包含`.`吗？所以这里的`.`别有意涵，`console.log`表达式的真正含义是：

返还console变量所指代值里的log属性。

第四章里Marijn会详细介绍这部分内容。

### Return values

类似于`alert`和`console.log`的函数会对程序造成切实影响(side effect)，但并不是所有函数都是如此。

有些函数被执行后将产生一个值，这时它们的作用就类似于一个**表达式**，譬如取最大值函数`Math.max`：

``` javascript
console.log(Math.max(2, 4));
// 4
```

函数运行后产生值的过程被称作**返回值(return values)**。回顾一下，**在JavaScript中任何一个创生值的东西都被称作表达式**。这意味着返回值的函数可以被用来与其他表达式进行组合，包裹在一段更长的表达式中。

``` javcascript
console.log(Math.min(2, 3) + 5);
// 7
```

### Prompt and Confirm

除了`alert`函数，浏览器还提供了其他一些会激活提示框的函数。

+ `prompt`函数
+ `confirm`函数

这两种函数都已经比较少用了，大部分原因在于我们无法良好地控制提示框的最终样式。

用来玩玩小程序还是不错的（狗日的整蛊弹框链接……）。

### Control Flow

一般来说，程序执行语句的顺序是自上而下线性的。可以用简单的直线箭头表示。示例：

``` javascript
var the_year = Number(prompt("How long do you have fell in love with her/him?","..."))
alert("I got it. It is " + the_year + ", right?")
```

`Number`函数的功能是将参数的类型转化为数值，类似的函数还有`Boolean`或者`String()`。

![Straight line](http://eloquentjavascript.net/img/controlflow-straight.svg)

### Conditional Execution

条件执行是除直线流外的另一种程序运行方式。程序将基于条件中表达式的布尔值来选择运行那一条程序。

![conditional Execution](http://eloquentjavascript.net/img/controlflow-if.svg)

JavaScript使用`if`关键词来创建条件执行，在最简单的情况下，我们可能只想让程序在满足一个也是唯一一个条件时执行语句，看看Marijn的例子：

``` javascript
var theNumber = Number(prompt("Pick a number", ""));
//只有输入可以被转化为数值时才进行平方操作
if (!isNaN(theNumber))
  alert("Your number is the square root of " + theNumber * theNumber);
```

我们当然不会时时刻刻只想有一个备胎供程序选择，备胎代代无穷已，不是吗？所以下列的条件结构就很自然了：

``` javascript 
var hehe = Number(promt("Write your favorite numer", "0"))

var hehe = Number(prompt("Write your favorite numer", "0"));

if (hehe < 10)
	alert("xixi");
else if (hehe < 100)
	alert("meme");
else
	alert("memeda");
```

#### While and Do Loops

试想我们需要输出12以内的所有偶数，我们需要怎么办？显然，一个一个`console.log()`并不是好办法。我们写程序的目的不就是为了**do less**么？

这时候，就需要**循环结构(loop)**登场了。

![loop](http://eloquentjavascript.net/img/controlflow-loop.svg)

JavaScript通过关键词`while`调用循环，它的格式为：

``` javascript
while (control) {

}
```

还是Marijn的例子：

``` javascript
var number = 0;
while (number <= 12) {
  console.log(number);
  number = number + 2;
}
// 0
// 2
// … etcetera
```

只要小括号中的表达式值为`true`，`while`循环将会反复执行大括号内的语句。

大括号包裹我们所想要执行的语句。它的作用类似于小括号与表达式的关系（小括号可以将数条表达式包裹起来形成一条语句）：一系列语句被包裹在大括号中，形成一个**区块(block)**。

Marijn出于**简洁性(brevity)**的考虑，在书写单语句的循环和条件结构时都不使用大括号。而通常，我们会出于一致性和省事的想法，对这些结构里的语句都用上大括号。

在示例中，`number`变量起到跟踪器的作用。每轮循环结束时，它都会增加2，并在新循环开始前与条件进行比较，从而控制程序循环的次数。

Marijn给出了另一个计算2^10的循环程序例子：

``` javascript
var result = 1;
var counter = 0;
while (counter < 10) {
  result = result * 2;
  counter = counter + 1;
}
console.log(result);
// → 1024
```

我们同样可以使用1作为跟踪变量的起始值，但Marijn会在第四章里解释为什们咱们应习惯从0开始。

`do`循环和`while`循环的作用是类似的。它们唯一的区别是`do`循环会至少执行区块中的语句一次，然后在下一轮循环开始前才会和循环条件进行比较。

Marijn的例子：

``` javascript
do {
  var yourName = prompt("Who are you?");
} while (!yourName);
console.log(yourName);``````
```

在此例中，`!`操作符会在求反操作前强制将字符串转化成布尔值。而只有非`''`的字符串会被转换为`true`值。所以这个程序的含义就是：除非你输入了任何字符，它将反复地要求你写点东西。

### Indenting Code

在示例程序中，我们应该已经留意了一些字符缩进现象。在JavaScript中，这其实不是必须的，甚至分句断行都是可选的。如果乐意，我们可以在一行里书写所有代码。但在复杂的程序里，对不同区块的代码进行合理缩进会为我们提供一个良好的可视形象。这和没人喜欢在垃圾堆里工作是一个道理。

### for loops

回顾下`while`循环：首先，创建一个计数变量；然后是while循环，在循环条件中进行比对计数变量和条件的比较；最后，在循环区块最后改变计数变量的值。

由于它的应用实在是太普遍了，所以JavaScript提供了一个优化版的循环结构，那就是`for`循环：

``` javascript
for (track;control;update) {

}
```
Marijn的例子：

``` javascript
for (var number = 0; number <= 12; number = number + 2)
  console.log(number);
// → 0
// → 2
//   … etcetera
```

`for`关键字后的小括号里必须包含三个部分，用分号隔开。第一部分的作用是初始化计数变量，第二部分的作用是创建循环条件，第三部分的作用是设置每次循环结束后更新计数变量值的方式。

Marijn给出了`for`循环实现计算2^10值的方式：

``` javascript
var result = 1;
for (var counter = 0; counter < 10; counter = counter + 1)
  result = result * 2;
console.log(result);
// → 1024

// 注意！虽然Marijn没用大括号包裹for循环区块，他至少还是用了缩进的方式来表达`result = result * 2;`从属于`for`循环。
```

### Breaking Out of a Loop

让循环条件表达式产生的值为`false`可不是唯一让我们退出循环的方式。我们还可以使用'break'来强制中断循环。

``` javascript
for (var love = 0; ; love++) {
	if (love > 23) 
		break;
	console.log("love is worth " + love);
}
```

如果木有`break`，我们的这个`for`循环将会变成一个**无限循环(infinite loop)**，程序将会执行到本宇宙时间的尽头之后……嗯，其实一般是以浏览器崩溃作为结束。

`continue`的作用和`break`有些类似，当它在区块中被执行时，会跳过本次循环之后的语句，进入新一轮循环。

### Updating variables succinctly

在循环中，我们经常需要更新一些变量的值。

二笔青年：

``` javascript
trackPlus = trackPlus + 1
trackMinus = trackMinus - 1
```

普通青年：

``` javascript
trackPlus += 1
trackMinus -= 1
```

文艺青年：

``` javascript
trackPlus++
trackMinus--
```

### Dispatching on a value with switch

我们会经常遇到Marijn提到的如此代码形状：

``` javascript
if (variable == "value1") action1();
else if (variable == "value2") action2();
else if (variable == "value3") action3();
else defaultAction();
```

对此，我们可以用`switch`结构来更直观的构建。但JavaScript继承来的`switch`结构比C/JAVA要傻嗨多了（作者强力吐槽）……

``` javascript
switch (prompt("What is the weather like?")) {
  case "rainy":
    console.log("Remember to bring an umbrella.");
    break;
  case "sunny":
    console.log("Dress lightly.");
  case "cloudy":
    console.log("Go outside.");
    break;
  default:
    console.log("Unknown weather type!");
    break;
}

```

注意"sunny"那里并没有`break`。在'switch'结构中，语句只会在遇到break时才会停止执行。这让我们的条件可以共享一些语句（晴天既适合外出又适合穿轻薄些），但也可能制造出一些我们不想有的意外……

### Capitalization

命名变量还是挺有点技术含量的，以下是比较常见的变量命名方式

1. fuzzylittleturtle
2. fuzzy_little_turtle
3. FuzzyLittleTurtle
4. fuzzyLittleTurtle

Marijn推荐2，而4是常见的驼峰命名法，也有很多人喜欢。其他的就比较蠢蠢了。

有时候我们也会遇到变量首字母大写的情况，比如`Number`。此时JavaScript会将其视为一个**构造函数(contruct)**，具体会在第六章说。

### Comments

程序的注释一般用来抒发潜藏的诗意情感……偶尔用来让自己的代码更清晰明了，或解释某些复杂区域的作用方式。

JavaScript有两种注释方式：

+ 单行注释

``` javascript
var xxx = 'love'
`// I love xxx`
```

+ 多行注释

``` javascript
/* 
	I love xxx
		but
			never more.
*/

console.log('I love &nbsp;')
```

### Summary

程序是建立在语句之上的。有时候语句中会包含更多的语句。此外，语句中也经常会有表达式，而一个表达式也可能会由其他表达式组合而成。

一般来说，程序的执行是自上而下线性的。但我们可以用**条件结构(if, else, switch)**和**循环结构(while, do, for)**来改变程序的执行顺序。

变量可以为数据命名，也有助于我们记录程序状态的变化。环境是已定义变量的集合，JavaScript总是会在初始时创建一些符合标准的有用变量。

函数是一类用来**封装(encapsulate)**小段程序的值。调用函数被看做是表达式，但只是有可能会产生值。

### Excercise

和Marign的一对比，我的好蠢……

## Chapter 3 - Fucntions

函数是JavaScript语言的润滑剂。将小段程序包裹进一个值的概念大有用武之地：构建更大型程序、减少重复、为不同子程序命名并将它们分隔开。

其中最有用的能力大概就是创造新的词语吧。成人的日常字典有20000个词语，而大概不会有哪门程序语言会内建有20000条默认命令。所以，借助函数，我们可以手动来定义一些新词语，拜托重复性的工作。

### Defining a function

定义一个函数的方式很简单，将一个类型为函数的值勾连到一个变量上即可。

Marijn的例子：

``` javascript
var square = function(x) {
  return x * x;
};

console.log(square(12));
// → 144
```

使用`function`关键字创建一个函数。一个函数中包含了**参数(parameters)**和在调用时被执行的**主体(body)**。就算只有一条语句，主体也必须被大括号包裹，这点和之前的结构有所不同。

函数的参数数量是任意的，看看marijn的例子：

``` javascript
var makeNoise = function() {
  console.log("Pling!");
};

makeNoise();
// → Pling!

var power = function(base, exponent) {
  var result = 1;
  for (var count = 0; count < exponent; count++)
    result *= base;
  return result;
};

console.log(power(2, 10));
// → 1024
```
一些函数可以产生新值。我们使用`return`语句来决定这个值是什么。当读取到`return`语句时，函数会直接结束，然后返还return后的值。如果值为空，那就返还`undefined`。

### Parameters and scopes

参数的行为和变量很类似。但参数值是由函数的调用者(caller)决定的，而不是由函数自己决定。

**作用域(scope)**是一个比较重要的概念。函数的**参数**及其内部**使用`var`定义的变量**，被称作为本地的(local)。即意是它们只能在函数内部被读取调用，多个相同函数的本地变量是互不干扰的。

在函数之外定义的变量被称作全局的(global)，这指的是它们在整个程序里都是可见的，可以被任意函数访问（只要函数内部没有定义同名变量）。

Marijn给的一个简单示例：

``` javascript
var x = "outside";

var f1 = function() {
  var x = "inside f1";
};
f1();
console.log(x);
// → outside

var f2 = function() {
  x = "inside f2";
};
f2();
console.log(x);
// → inside f2
```

本地作用域这种有趣的特性避免了函数间可能产生的意外交互。试想如果所有变量都是全局的，那我们恐怕就很容易一失足成千古恨了。

### Nested scope

当然，作用域的内容可不仅仅本地和全局这么简单，因为函数内也还能嵌套函数，由此可以创造多个不同层级的作用域。

看看Marijn的例子：

``` javascript
var landscape = function() {
  var result = "";
  var flat = function(size) {
    for (var count = 0; count < size; count++)
      result += "_";
  };
  var mountain = function(size) {
    result += "/";
    for (var count = 0; count < size; count++)
      result += "'";
    result += "\\";
  };

  flat(3);
  mountain(4);
  flat(6);
  mountain(1);
  flat(1);
  return result;
};

console.log(landscape());
// → ___/''''\______/'\_
```

`flat`和`mountain`函数可以读取到`landscape`函数内的`result`变量，因为它们位于定义`result`变量的函数下一层。但它们互相间不能读取`count`变量，答案很显然，它们的作用域是平行的。此外，`landscape`外部的环境不能读取到其内部的一切变量。

简言之，**每一层本地作用域可以读取到全部在其上层的作用域**。变量是否可见取决于其在程序中的位置，这被称作静态作用域(lexical scoping)。

在JavaScript中，**唯有函数可以创造一层新作用域**，类似于使用括号创造新区块的方式是没用的。

``` javascript
var something = 1;
{
  var something = 2;
  // Do stuff with variable something...
}
// Outside of the block again...
```

Marijn用这个示例告诉我们，被大括号包裹的`something`变量依然指代外部的那个变量。

下个版本的JavaScript将会引入`key`关键字来解决这个问题。

### Functions as values

乍看下，函数变量的作用似乎仅仅是用来命名一段程序。这让我们很容易将函数值和它的名字搞混淆。

但这二者显然是不同的。函数值可以做和其他类型值一样的事：将之用于表达式而非直接调用它；将之储存到其他地方；将之作为参数传入到其他函数中……一个勾连了函数值的变量仍然是个正常的变量，它同样还能被指派去关联其他值。

Marijn的例子：

``` javascript
var launchMissiles = function(value) {
  missileSystem.launch("now");
};
if (safeMode)
  launchMissiles = function(value) {/* do nothing */};
```

第五章会细说如何将函数值传入到其他函数中。

### Declaration notation

另一种定义函数的简单表示方法如下：

``` javascript
function meme() {
	return 'xixi'
}
```

看起来好像和之前差不多，不过确实有一个非常微妙的区别。将这种函数定义方式应用在**条件或循环结构**中时，不同的平台会有着不同的处理方式，以至于最近的标准已经明确ban掉了。

Marijn例子：

``` javascript
function example() {
  function a() {} // Okay
  if (something) {
    function b() {} // Danger!
  }
}
```
如果想确保程序能正确运行，那么就只在函数或程序的外层区块中使用这种方式。

此外，我们再看看这段Marijn的代码：

``` javascript
console.log("The future says:", future());

function future() {
  return "We STILL have no flying cars.";
}
```

函数定义脱离了正常程序的从上至下执行流程。它们会在概念上移动到所属作用域的最顶部，这样可以让作用域的所有代码能使用它。爽歪歪。。。


### The call stack

深入看看函数的控制流，Marijn例子：

``` javascript
function greet(who) {
  console.log("Hello " + who);
}
greet("Harry");
console.log("Bye");
```

这个流程近似于：

```
top
   greet
        console.log
   greet
top
   console.log
top
```

由于**函数会在结束时跳转回到调用它的位置，所以计算机必须记住函数是在哪（上下文context）被调用的**。第一个`console.log`函数跳转回了`greet`函数，第二个`console.log`函数跳转回了程序底部。

计算机储存上下文的地方被称为**调用栈(call stack)**。每当一个函数被调用时，调用栈最顶部就会储存上一个上下文，当函数结束返还时，这个上下文就会从栈上被移除，并用之来让程序继续执行。

栈的使用将会占据物理储存空间。所以如果栈变得过大时，将可能出现"out of stack space"、"too much recursion"等提示。

Marijn给了一个玄学例子：

``` javascript
function chicken() {
  return egg();
}
function egg() {
  return chicken();
}
console.log(chicken() + " came first.");
// → ??
```

### Optional Arguments

JavaScript的机制允许函数在调用时被输入任意数量的参数。多余的参数会被无视，而如果参数不够的话则空缺的参数值会被`undefined`替代。

从好的方面说，JavaScript让我们的函数可以拥有可选参数值。

Marijn例子：

``` javascript
function power(base, exponent) {
  if (exponent == undefined)
    exponent = 2;
  var result = 1;
  for (var count = 0; count < exponent; count++)
    result *= base;
  return result;
}

console.log(power(4));
// → 16
console.log(power(4, 3));
// → 64
```

第四章将会讲解如何在函数内获取完整参数列表，这种操作将使得函数接受任意数量的参数成为可能，譬如Marijn所说：

``` javascript
console.log("R", 2, "D", 2);
// → R 2 D 2
```

### Closure

在JavaScript中，函数每次被调用都将重新创造本地变量。这给我们留出了一个问题：当函数执行结束后，如果我们想保留这个本地变量，需要怎么做？

Marijn给出了一个例子：

``` javascript
function wrapValue(n) {
  var localVariable = n;
  return function() { return localVariable; };
}

var wrap1 = wrapValue(1);
var wrap2 = wrapValue(2);
console.log(wrap1());
// → 1
console.log(wrap2());
// → 2
```

`warpValue`函数首先定义了一个本地变量`localVariable`，然后返回一个返还`localVariable`变量的函数。

从`wrap1`和`wrap2`上看，我们成功地保留住了宝贵的本地变量（同时也证明了一个函数每次都调用都将会创造新的本地变量，不同调用产生的同名本地变量不会相互干扰）。

这种能够引用函数内部本地变量某个具体值的特性被称作**闭包(closure)**。一个封装了一些本地变量的函数被称作一个闭包- -除了妈妈不用再担心我没法保存函数内本地变量之外，我们还可以用闭包做很多有意思的事。

比如Marijn的这个无聊例子：

``` javascript
function multiplier(factor) {
  return function(number) {
    return number * factor;
  };
}

var twice = multiplier(2);
console.log(twice(5));
// → 10
```

理解这样的程序行为比较困难，不过Marijn给了一个很形象的解释：把`function`关键字看做是一个冷冻仓，它的作用是暂时冻结其内部的代码，并将之打包（成为函数值）。所以当我们看到`return function(...) {...}`这样的结构时，就可以将之视为要返还一些留待稍后使用的东西。哎哟不错哦。

### Recursion

