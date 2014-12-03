# Spring MVC

## SpringMVC框架介绍

Spring框架提供了构造Web应用程序的全能MVC模块。Spring MVC分离了控制器、模型对象、分派器以及处理程序对象的角色，这种分离让它们更容易进行制定。是一个标准的MVC框架。

## SpringMVC框架图

![springmvc](https://github.com/n5xm/springmvc/blob/master/WebContent/images/springmvc.jpg)

## SpringMVC接口解释

### DispatcherServlet接口：

Spring提供的前端控制器，所有的请求都有经过它来统一分发。在DispatcherServlet将请求分发给Spring Controller之前，需要借助于Spring提供的HandlerMapping定位到具体的Controller。

### HandlerMapping接口：

能够完成客户请求到Controller映射。

### Controller接口：

需要为并发用户处理上述请求，因此实现Controller接口时，必须保证线程安全并且可重用。Controller将处理用户请求，这和Struts Action扮演的角色是一致的。一旦Controller处理完用户请求，则返回ModelAndView对象给DispatcherServlet前端控制器，ModelAndView中包含了模型（Model）和视图（View）。从宏观角度考虑，DispatcherServlet是整个Web应用的控制器；从微观考虑，Controller是单个Http请求处理过程中的控制器，而ModelAndView是Http请求过程中返回的模型（Model）和视图（View）。

### ViewResolver接口：

Spring提供的视图解析器（ViewResolver）在Web应用中查找View对象，从而将相应结果渲染给客户。

## SpringMVC运行原理

1. 客户端请求提交到DispatcherServlet
1. 由DispatcherServlet控制器查询一个或多个HandlerMapping，找到处理请求的Controller
1. DispatcherServlet将请求提交到Controller
1. Controller调用业务逻辑处理后，返回ModelAndView
1. DispatcherServlet查询一个或多个ViewResoler视图解析器，找到ModelAndView指定的视图
1. 视图负责将结果显示到客户端

## SpringMVC总结

以上就是我理解的Spring MVC可能不够深刻。其实对于任何的框架来说，一个框架是一个可复用设计，框架的最大的好处就是复用。每个框架都有存在的理由，那Spring MVC的理由是什么呢？

只有各个框架之间彼此了解他们之间的优缺点，使用场合，使用原理，才能让我们的更快的成长。

## References

[SpringMVC入门教程及其原理讲解和实例代码下载](http://www.zuidaima.com/share/1751859714182144.htm)

[轻松上手SpringMVC](http://www.blogjava.net/zongbao/archive/2012/07/24/383884.html)