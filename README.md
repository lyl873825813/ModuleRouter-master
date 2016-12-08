# 组件化开发之路由设计 - ModuleRouter-master

------


如果我们把项目模块化了, 那两个组件间进行通讯或者跳转, 我们一般构建Intent的方式就不再使用了, 很简单, 因为在模块A中根本找不到模块B中的C类, 这就需要我们自定义路由规则, 绕一道弯去进行跳转, 说白了就是给你的类起一个别名, 我们用别用去引用. 其实在我准备自己去实现一个路由的时候我是google了一些解决方案的, 这些方案大致可分为两种：

 > 1.完全自己实现路由, 完全封装跳转参数

 > 2.利用隐式意图跳转

对于这两种方式我总结了一下, 个人认为第一种方式封装的太多, 甚至有些框架是RESTFul like的, 这样的封装一是学习成本太高, 二是旧项目改动起来太麻烦. 那第二种方式呢? 利用隐式意图是一种不错的选择, 而且Android原生支持, 这也是大家在尝试模块化开发时的一个选择, 不过这种方式仅支持Activity, Service, BroadcastReceiver, 扩展性太差. 综上因素, 我还是决定自己实现一个路由, 参考自上面的局限性, 我们的路由具有一下2个特点.

 > 1.上手简单, 目标是与原生方式一行代码之差就能实现Activity, Service, BroadcastReceiver调用.

 > 2.扩展性强, 开发者可以任意添加自己的路由实现, 不仅仅局限于Activity, Service, BroadcastReceiver.

