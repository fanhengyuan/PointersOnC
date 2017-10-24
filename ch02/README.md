1.编译和链接
  （1）编译并链接一个C语言的程序时，使用gcc加C语言文件名即可，中间会产生.o的目标文件，
  当链接完成之后就会被删除。
  （2）编译并链接几个C语言程序时：使用gcc加几个C语言文件名即可，中间用空格分隔，此时不
  会删除产生的目标文件，这样就可以允许在对某些程序修改之后，只对其中的修改后的程序进行编
  译。
  （3）编译一个C语言程序，并把他和目标文件进行链接时，使用gccC语言文件名和目标文件名。
  （4）编译一个C语言程序，并产生一个目标文件时，使用gcc -c加C语言文件名
  （5）编译几个C语言程序，并分别为每个文件产生一个目标文件时，使用gcc -c加几个C语言文件
  名。
  （6）链接几个目标文件，使用gcc加几个目标文件
  
2.代替使用注释的方法
```c
    #if 0
      statement
    #endif
```

3.三字母词
  三字母词就是用几个字符序列合起来表示李另一个字符  
```c
  ??(  [    ??<  (   ??=  #
  ??)  ]    ??>  )   ??/  \
  ??!  |    ??'  ^   ??-  ~
```
  
4.\r与\n的区别
  \r ： return 到当前行的最左边。
  \n： newline 向下移动一行，并不移动左右。
  Linux中\n表示回车+换行；
  Windows中\r\n表示回车+换行。
  Mac中\r表示回车+换行。
  历史：
  回车和换行这两个概念的来历和区别。在计算机还没有出现之前，有一种叫做电传打字机的玩意，
  每秒钟可以打10个字符。但是它有一个问题，就是打完一行换行的时候，要用去0.2秒，正好可
  以打两个字符。要是在这0.2秒里面，又有新的字符传过来，那么这个字符将丢失于是，研制人员
  想了个办法解决这个问题，就是在每行后面加两个表示结束的字符。一个叫做“回车(return)”，
  告诉打字机把打印头定位在左边界；另一个叫做“换行(newline)”，告诉打字机把纸向下移一行。
  这就是“换行”和“回车”的来历，从它们的英语名字上也可以看出一二。
  
5.C\C++的转义字符
  所有的ASCII码都可以用“\”加数字（一般是8进制数字）来表示。而C中定义了一些字母前加"\"
  来表示常见的那些不能显示的ASCII字符，如\0,\t,\n等，就称为转义字符，因为后面的字符，
  都不是它本来的ASCII字符意思了。
  转义字符 意义 ASCII码值(十进制)
  
```
  \a 响铃(BEL) 007
  \b 退格(BS) 008
  \f 换页(FF) 012
  \n 换行(LF) 010
  \r 回车(CR) 013
  \t 水平制表(HT) 009
  \v 垂直制表(VT) 011
  \\ 反斜杠 092
  \? 问号字符 063
  \' 单引号字符 039
  \" 双引号字符 034
  \0 空字符(NULL) 000
  \ddd 任意字符 三位八进制
  \xhh 任意字符 二位十六进制
```
  
  注：
  1.\v垂直制表和\f换页符对屏幕没有任何影响，但会影响打印机执行响应操作。 
  2.\n其实应该叫回车换行。换行只是换一行，不改变光标的横坐标；回车只是回到行首，不改变光标的纵坐标。
  3.\t 光标向前移动四格或八格，可以在编译器里设置
  4.\' 在字符里（即单引号里）使用。在字符串里(即双引号里)不需要，只要用 ' 即可。
  5.\? 其实不必要。只要用 ? 就可以了（在windows VC6 和tc2 中验证）。
  
6.为了防止编译链接时产生多重重定义的错误，可以在每个文件的函数定义的前后加入如下的代码：
```c
    #ifndef  XXXX
    #define XXXX    
        函数定义
    #endif
```