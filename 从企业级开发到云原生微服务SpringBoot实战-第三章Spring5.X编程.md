## Spring5.X编程

### IoC容器

Spring的核心是**IoC(控制反转)容器**，**IoC容器**管理容器内的普通Java对象以及对象之间关系的绑定**(DI 依赖注入)**。容器中被管理的对象称为Bean。

Spring是通过元数据和POJO来定义和管理Bean的

- POJO:简单的Java对象
- 元数据：描述如何管理POJO的数据

Spring的**Ioc容器**是ApplicationContext,它拥有一个父接口BeanFactory,用来提供管理配置任意对象的基础功能。

`//新建一个ApplicationContext的实现，就拥有一个Spring的IoC容器`

`ApplicationContext applicationContext = new ClassPathXmlApplicationContext("context.xml");`

SpringBoot可以在不同的环境自动创建正确的**IoC容器**

- AnnotationConfigApplicationContext:默认创建的IoC容器
- 