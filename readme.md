gcc(gnu compiler collection)处理过程：
1. hello.c ->预处理器(cpp:处理#的头文件) -> hello.i 
2. hello.i ->编译器(ccl) -> hello.s(汇编文件)
3. hello.s ->汇编器(as:处理汇编文件) ->hello.o(relocatable object file:二进制文件)
4. hello.o + printf.o + XXX.o -> 链接器(ld:loader ) -> hello (executable object file,可执行目标文件如 xx.exe)




编译器(ccl)处理过程：

1.前端:

      1.1词法分析器：
      
      
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
    
      1.2解析器:
         解析时产生的树状结构被称为 抽象的语法树，或者称之为 AST
      
2.中间端：略

3.后端：代码生成器或者表达式解析器
        3.1 代码生成器：接收一个 AST ,然后生成相应的代码或者汇编代码
        
4.写入汇编文件(.s 或 .asm)





专业名词:

汇编(assembly),抽象语法树(Abstract_syntax_tree:AST)

参考资料：
1. <a href="http://blog.jobbole.com/114466/">人人都能读懂的编译器原理</a>
2. <a href="http://blog.jobbole.com/96225/">帮 C/C++ 程序员彻底了解链接器</a>
3. <a href="https://github.com/nlsandler/write_a_c_compiler">自己编写一个c 编译器</a>
 

