# SpringSecurity

项目下载须知：项目下载下来后可参考本文档理解项目中各个类的作用。

这篇文章不含SpringSecurity源码，仅从一个使用者的角度谈如何使用其实现用户的登录认证。

![image-20201125100147769](E:/%25E5%25A2%259E%25E5%25BC%25BA%25E5%25AD%25A6%25E4%25B9%25A0%25E8%2583%25BD%25E5%258A%259B%25E5%2592%258C%25E6%2580%259D%25E7%25BB%25B4%25E8%2583%25BD%25E5%258A%259B%25E7%259A%2584%25E8%25BD%25AF%25E4%25BB%25B6/Typora/files/JavaWeb/2020%25E5%25B9%25B411%25E6%259C%2588/20SpringSecurity/SpringSecurity.assets/image-20201125100147769.png)

![image-20201125100329615](E:/%25E5%25A2%259E%25E5%25BC%25BA%25E5%25AD%25A6%25E4%25B9%25A0%25E8%2583%25BD%25E5%258A%259B%25E5%2592%258C%25E6%2580%259D%25E7%25BB%25B4%25E8%2583%25BD%25E5%258A%259B%25E7%259A%2584%25E8%25BD%25AF%25E4%25BB%25B6/Typora/files/JavaWeb/2020%25E5%25B9%25B411%25E6%259C%2588/20SpringSecurity/SpringSecurity.assets/image-20201125100329615.png)

新建一个SpringSecurity的配置类：编程者只需要新建一个config文件夹，然后新建一个类继承WebSecurityConfigurerAdapter这个类，并且加上@EnableWebSecurity注解，就能配置安全信息。

继承了WebSecurityConfigurerAdapter之后要实现两个方法，一个是授权的，一个是认证的。

授权的意思大概是给各个URL分配不同的访问权限。

认证的的意思大概是给用户设立权限。

一个授权一个认证组合起来就完成了用户登录授权功能。过程是用户访问浏览器的URL，SpringSecurity就会查询用户的权限和查询它访问的URL对应需要什么权限，权限相匹配的话就行，不匹配就拦截（无法到达controller这一步）。整个拦截的过程都是SpringSecurity做的。用户只要动动手指，有权限就能登录得上，没有权限就登不上。

表单提交

默认表单的action属性为/login，controller里面不需要写一个专门的/login RequestMapping，因为在SpringSecurity已经集成了/login RequestMapping。

