## 关于qj分享所得收获

#### 1、为何在头文件当中不写函数实现

答：

| 优点       |
| ---------- |
| 函数模块化 |

| 缺点             |
| ---------------- |
| 会出现重定义现象 |



会出现重定义现象

因为在多个源文件当中包含了相同的头文件，并且这些源文件都尝试定义同一个函数。通过分析C/C++语言的编译和链接的过程即可发现问题所在。
在编译阶段，编译器会读取源文件中的代码，并根据头文件中的声明来确定函数的原型。
在链接阶段，所有编译生成的目标文件(.obj/.o文件)会被链接到一起形成可执行文件或库。在链接阶段，链接器会检查函数的定义是否唯一。

现在在链接阶段，链接阶段链接器会发现多个源文件中都有同一个函数的定义，从而导致重定义错误。

