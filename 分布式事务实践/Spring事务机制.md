## Spring事务机制

内容：

- Spring事务机制：事务抽象、事务传播、事务隔离
- 代码方式与标签方式的事务实现
- JPA、JMS事务实例

### Spring事务管理

Spring事务管理是通过spring-tx库进行管理

- 提供的统一的API接口支持不同的资源
- 提供声明式事务管理
- 方便的与Spring框架集成
- 多个资源的事务管理、同步

### Spring事务抽象

- PlatformTransactionManager: 事务管理器的接口
- TransactionDefinition: 事务定义的接口
- TransactionStatus: 事务运行的状态

![image-20201124213708617](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124213708617.png)

![image-20201124214122319](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124214122319.png)

**Spring事务抽象—事务隔离机制**

```
TransactionDefinition.ISOLATION_DEFAULT //默认隔离机制，就是数据库隔离机制是什么，事务隔离机制就是什么
TransactionDefinition.ISOLATION_READ_COMMITTED //二个事务，一个事务可以读取另一个事务已经提交的数据
TransactionDefinition.ISOLATION_READ_UNCOMMITTED //一个事务可以读取另一个事务还未提交的数据，就是脏读
TransactionDefinition.ISOLATION_REPEATABLE_READ	//一个事务读一个数据多次，读的数据是一样的，可重复读。(比如一个事务执行时间过长，第一次读取数据后，另一个事务对数据进行修改，而该事务第二次读取该数据仍然是读取第一次数据的值。)
TransactionDefinition.ISOLATION_SERIALIZABLE //所有的读写操作都是线性的，即使读一条数据都是排队执行。
```

**Spring事务抽象—事务传播机制**

如果有两个业务Bean,其中一个Service的方法调用另一个Service的某个方法，这两个方法都是在事务里面执行的，调用者的方法在一个事务调用在另一个事务的被调用者的方法，两个方法的调用是通过事务传播机制进行传播的。

```
TransactionDefinition.PROPAGATION_REQUIRED(Default) //如果ServiceA的一个方法调用ServiceB的一个方法，如果ServiceA已经在一个事务当中，ServiceB的这个方法不需要在新建一个事务
TransactionDefinition.PROPAGATION_SUPPORTS //调用的方法在事务中执行，就在事务中执行，没有就不在事务中执行
TransactionDefinition.PROPAGATION_MANDATORY //调用的方法必须在事务中执行，没有就会报错
TransactionDefinition.PROPAGATION_REQUIRES_NEW //不管在调用我那个方法的方法有没有在事务执行，我要在启一个事务。（只在JTA事务用）
TransactionDefinition.PROPAGATION_NOT_SUPPORTED //用于JTA事务，调用我那个方法的方法在事务执行，将该事务挂起，在非事务状态下执行。
TransactionDefinition.PROPAGATION_NEVER //不会在事务中执行
TransactionDefinition.PROPAGATION_NESTEDED //嵌套事务，在JDBC3.0中使用
```

![image-20201124223805213](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124223805213.png)

![image-20201124224047583](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124224047583.png)

![image-20201124224243283](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124224243283.png)

![image-20201124224513689](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124224513689.png)

![image-20201124224608006](C:\Users\Ally\AppData\Roaming\Typora\typora-user-images\image-20201124224608006.png)

**PlatformTransactionManager的常见实现**

- DataSourceTransactionManager
- JpaTransactionManager
- JmsTransactionManager
- JtaTransactionManager

### Spring事务实例

- 代码方式、标签方式实现事务
- JPA事务管理
- 使用H2数据库(支持事务)

### Spring JMS 事务实例

- Spring Boot中使用JMS
- Spring Boot ActiveMQ Starter
- 内置的可运行的ActiveMQ服务器
- 实现读写ActiveMQ的事务