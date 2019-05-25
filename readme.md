gcc(gnu compiler collection)处理过程：
1. hello.c ->预处理器(cpp:处理#的头文件) -> hello.i 
2. hello.i ->编译器(ccl) -> hello.s(汇编文件)
3. hello.s ->汇编器(as:处理汇编文件) ->hello.o(relocatable object file:二进制文件)
4. hello.o + printf.o + XXX.o -> 链接器(ld:loader ) -> hello (executable object file,可执行目标文件如 xx.exe)

编译器(ccl)处理过程：







专业名称:
汇编(assembly),
