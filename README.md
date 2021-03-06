# JBootstrap
通过对Bootstrap源码进行进一步定制，编译出合适自己使用的Bootstrap框架。

|  #  | Bootstrap版本更新 |   更新时间   |
| :-: | :--------------: | :--------: |
|  1  |      5.1.0       | 2021-08-31 |
|  2  |      5.1.1       | 2021-09-21 |

## 内容
1. `$enable-important-utilities`设置为true，**即不添加!important修饰**
2. 创建了 `create-spacers($step, $steps)`函数用于创建 `$spacers`变量，覆盖原有的 `$spacers`

   |  参数  |    描述    |
   | :----: | :-------: |
   | $step  |     步    |
   | $steps | 步数( > 0) |

   调用：`$spacers: create-spacers(.25, 32);`
   注意：该变量将会影响**间距**、**填充**等样式
3. 创建了 `create-sizing($step)`函数用于创建 `$sizing`变量，并修改 ` _utilities.scss`中的"width"和"height"两个key，改为 `$sizing`

   |  参数  |      描述      |
   | :----: | :-----------: |
   | $step  | 步长(100的约数) |

   调用：`$sizing: create-sizing(5);`
   注意：该变量将会影响**宽**和**高**的比例样式选项
4. 修改$font-sizes变量，修改为如下：
   ```SCSS
   $font-sizes: (
        1: $h1-font-size,
        2: $h2-font-size,
        3: $h3-font-size,
        4: $h4-font-size,
        5: $h5-font-size,
        6: $h6-font-size,
        7: $font-size-base * .9,
        8: $font-size-base * .85,
        9: $font-size-base * .8,
       10: $font-size-base * .75
   );
   ```
5. 添加JBootstrap独特的主类：`jb-container`，某标签在使用JBootstrap提供的样式时需要被包含在`jb-container`类标签中。
6. 控制`input`样式的类（其父类需添加`jb-container`类名）
   | 类名 | 描述 |
   | :-: | :--- |
   | form-number-btn-none | 去掉input类型为数字时输入框右边的数字调节按钮 |