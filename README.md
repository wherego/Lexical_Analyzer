# Lexical_Analyzer

c++写的一个简单词法分析器

## 词法分析器需要实现的功能：

- 预处理功能，源程序中可能包含对程序执行无意义的符号，要求将其剔除。

```
首先，编制一个源程序的输入过程，从键盘、文件或文本框输入若干行语句，依次存入输入缓冲区（字符型数据）；

然后编制一个预处理子程序，去掉输入代码中的回车符、换行符和跳格符等编辑性文字；`

把多个空白符合并为一个；

去掉注释。
```

- 实现词法分析功能

```
输入：所给文法的源程序字符串。
输出：二元组构成的序列。 具体实现时，可以将单词的二元组用结构进行处理。
```

- 待分析的c语言子集的语法
````

关键字：main if then while do static int double struct break else long switch case typedef char return const float short continue for void default sizeof do

运算符和界符： + - * / : := < <> <= > >= = ; ( ) #

其他标记ID和NUM通过一下正规式定义其他标记： ID→letter(letter|digit) NUM→digit digit letter→a|...|z|A|...|Z digit→0|...|9...

空格由空白、制表符和换行符组成 空格一般用来分隔ID、NUM、专用符号和关键字，词法分析阶段通常被忽略 ```

- 各种单词符号对应的种别码

Symbol  | Code | Symbol   | Code | Symbol | Code
------- | ---- | -------- | ---- | ------ | ----
#           | 0    | char        | 16   | !=          | 32
main     | 1    | return     | 17   | <           | 33
if           | 2    | const      | 18   | <>         | 34
then      | 3    | float       | 19   | <=         | 35
while     | 4    | short      | 20   | >            | 36
do         | 5    | continue | 21   | >=         | 37
static     | 6    | for          | 22   | =            | 38
int         | 7    | void        | 23   | default   | 39
double  | 8    | sizeof     | 24   | do           | 40
struct    | 9    | ID           | 25   | ;               | 41
break    | 10  | NUM      | 26   | (               | 42
else       | 11  | +            | 27   |  )              | 43
long      | 12  | -             | 28   |        |
switch   | 13  | *             | 29   |        |
case      | 14  | /             | 30   |        |
typedef | 15  | !             | 31   |        |

#### 流程图

![](http://7xwme1.com1.z0.glb.clouddn.com/workflow.jpg)
