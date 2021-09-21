# JBootstrap
通过对Bootstrap源码进行进一步定制，编译出合适自己使用的Bootstrap框架。

## 修改
1. $enable-important-utilities设置为true，**即不添加!important修饰**
2. 创建了create-spacers($step, $steps)函数用于创建<font color=#FF000>$spacers</font>变量，覆盖原有的$spacers
   * $step —步
   * $steps —步数(>0)

   调用：$spacers: create-spacers(.25, 32);  
   注意：该变量将会影响**间距**、**填充**等样式
