# JBootstrap
通过对Bootstrap源码进行进一步定制，编译出合适自己使用的Bootstrap框架。

## 修改
1. `$enable-important-utilities`设置为true，**即不添加!important修饰**
2. 创建了`create-spacers($step, $steps)`函数用于创建`$spacers`变量，覆盖原有的`$spacers`
   | 参数 | 描述 |
   |:----:|:----:|
   | $step  | 步 |
   | $steps | 步数( > 0) |

   调用：`$spacers: create-spacers(.25, 32);`  
   注意：该变量将会影响**间距**、**填充**等样式
3. 创建了`create-sizing($step)`函数用于创建`$sizing`变量，并修改` _utilities.scss`中的"width"和"height"两个key，改为`$sizing`
   | 参数 | 描述 |
   |:----:|:----:|
   | $step  | 步长(100的约数) |
   
   调用：`$sizing: create-sizing(5);`  
   注意：该变量将会影响**宽**和**高**的比例样式选项
