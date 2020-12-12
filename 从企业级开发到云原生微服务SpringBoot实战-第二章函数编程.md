#### 函数编程

Lambda表达式是一种匿名函数，在函数编程里，它可以作为参数进行传递。

`Lambda表达式`

`Comparator<Person> a = (Person b, Person c) -> b.getWeight.compareTo(c.getWeight());`

- （Person b,Person c）为Lambda表达式的参数列表
- -> 用来分开Lambda参数和Lambda体
- 右侧是Lambda体

规则：

1. Lambda表达式可以有0到多个参数，如() -> {}
2. Java编译器有类型推断(Type Inference)的能力，参数的类型可以省略
3. Lambda只有一个参数，则可以省略(),如a -> a + 1
4. Lambda体需要用{},If Lambda只有一句表达式，则可以省略{}
5. Lambda体中如果用return,则用{}包起来

方法引用

在Java中，方法引用使用::表示

- 构造器方法引用：类名::new
- 静态方法引用：类名::静态方法
- 实例方法引用：实例对象名::实例方法
- 引用特定类的任意对象的方法：类型名::实例方法

Stream

是用声明式的方式来操作数据集合的一个Java API

Stream开发：

1. 从数据源获得Stream
2. 中间操作：组成处理管道
3. 终结操作：从管道中产生处理结果

Optional类是可以解决空指针异常的问题。



