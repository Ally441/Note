## SpringBoot

SpringBoot自动运行方式：

1. main方法启动SpringBoot
2. 在SpringBoot根目录下运行mvn spring-boot:run
3. java -jar xxx.jar

@SpringBootApplication:是一个组合注解，相当于@EnableAutoConfiguration,

@ComponentScan和@SpringBootConfiguratio三个注解

SQL语句要么全大写，要么全小写

##### Druid

是阿里开源项目的一个数据库连接池，是一个JDBC组件，包括三个部分：

1. DruidDriver:代理Driver,能够提供基于Filter-Chain模式的插件体系
2. DruidDataSource：高效可管理的数据库连接池
3. SQLParser:支持所有JDBC兼容的数据库

在监控、可扩展、稳定性和性能方面具有明显优势

@Configuration: Spring中有很多XML配置文件，文件会配置很多的bean,在类上添加@Configuration注解，可以理解该类为一个XML配置文件

@Bean：等同于XML配置文件中的<bean>配置，SpringBoot会把加上该注解的方法的返回值装载进Spring IoC容器，方法的名称对应<bean>标签的id属性值



##### HikariCP

是数据库连接池，史称最快的。

HikariCP为什么快？

1. 代码量非常小
2. 稳定性、可靠性强
3. 速度快







