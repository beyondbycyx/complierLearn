gcc(gnu compiler collection)处理过程：
1. hello.c ->预处理器(cpp:处理#的头文件) -> hello.i 
2. hello.i ->编译器(ccl) -> hello.s(汇编文件)

      2.1 “汇编语言”：<a href="http://www.ruanyifeng.com/blog/2018/01/assembly-language-primer.html">汇编语言入门教程</a>
      
3. hello.s ->汇编器(as:处理汇编文件) ->hello.o(relocatable object file:二进制文件)
4. hello.o + printf.o + XXX.o -> 链接器(linker ) -> hello (executable object file,可执行目标文件如 xx.exe)

      4.1 符号解析：
      4.2 重定位：



编译器(ccl)处理过程：

1.前端:

      1.1词法分析器(lexer)：
      
      
<code>
  int main() {
    int a;
    int b;
    a = b = 4;
    return a - b;
}
 
Scanner production:
[Keyword(Int), Id("main"), Symbol(LParen), Symbol(RParen), Symbol(LBrace), Keyword(Int), Id("a"), Symbol(Semicolon), Keyword(Int), Id("b"), Symbol(Semicolon), Id("a"), Operator(Assignment), Id("b"),
Operator(Assignment), Integer(4), Symbol(Semicolon), Keyword(Return), Id("a"), Operator(Minus), Id("b"), Symbol(Semicolon), Symbol(RBrace)]
</code>
    
      1.2解析器(parser):
         解析时产生的树状结构被称为 抽象的语法树，或者称之为 AST
      
2.中间端：略

3.后端：代码生成器(generator)或者表达式解析器
        3.1 代码生成器：接收一个 AST ,然后生成相应的代码或者汇编代码
        
4.写入汇编文件(.s 或 .asm)





专业名词:

汇编(assembly),抽象语法树(Abstract_syntax_tree:AST),
ESP（Extended Stack Pointer,扩展栈指针寄存器)寄存器：是指针寄存器的一种，用于存放函数栈顶指针。

参考资料：
1. <a href="http://blog.jobbole.com/114466/">人人都能读懂的编译器原理</a>
2. <a href="http://blog.jobbole.com/96225/">帮 C/C++ 程序员彻底了解链接器</a>
3. <a href="https://github.com/nlsandler/write_a_c_compiler">自己编写一个c 编译器</a>
4. <a href="https://godbolt.org/">在线compiler explorer</a> 
5. <a href='https://codeday.me/bug/20170819/56357.html'>编译器 – 构造 – 什么是编译器,链接器,加载器？</a>

工具：
1. <a href ='https://godbolt.org/'>在线compiler explorer</a>
2. <a href='http://www.cs.virginia.edu/~evans/cs216/guides/x86.html'>x86 Assembly Guide x86 汇编指引</a>
