# Shiro

核心API:

Subject: 用户主体(把操作交给SecurityManager)

SecurityManager:安全管理器(关联Realm)，管理所有Subject，可以配合内部安全组件。(类似于SpringMVC中的DispatcherServlet)

Realm:Shiro连接数据的桥梁，用于进行权限信息的验证，一般需要自己实现。

```
* Shiro内置过滤器：可以实现权限相关的拦截器
* 常用的过滤器：
*      anon:无需认证(登录)可以访问
*      authc:必须认证才可以访问
*      user:如果使用rememberMe的功能可以直接访问
*      perms:该资源必须得到资源权限才可以访问
*      role:该资源必须得到角色权限才可以访问
```