# Go环境配置

[点击](https://golang.org/dl/)下载自己系统对应的安装包，不同系统安装方式不同，本次使用`windows`系统，傻瓜式下一步即可。

安装安装之后打开命令窗口，查看是否安装成功。在命令行中输入下面的命令

```shell
$  go version
  // go version go1.16.3 windows/amd64
```

如果能正确的输入下面的内容，表示安装成了。

如果没有正确的显示，可能需要手动配置环境变量，比如我的安装目录是`C:\Program Files\Go\bin`,把这个路径配置到`path`环境变量即可。

![image.png](https://p9-juejin.byteimg.com/tos-cn-i-k3u1fbpfcp/acb7c505fece4ce48b58a70b6a42f5f6~tplv-k3u1fbpfcp-watermark.image)

# 开发工具

强烈推荐 [GoLand](https://www.jetbrains.com/go/),只是收费的可能大部分不太能接受，喜欢免费软件的可以转向`vs code`,搭配一些插件使用起来也是不错的。

# HelloWorld
 没写`Hello, World`，就代表你还没有真正的入门，老规矩，先来一个`Hello, World`

 使用`GoLand`创建一个项目，新建一个`main.go`文件，内容如下
 ```go
 package main

import "fmt"

func main() {
	fmt.Println("Hello, World!")
} 
```

在命令行中输入
```shell
$ go run main.go
 
 #  Hello, World!

```
看到打出了` Hello, World`，完美，已经成功入门了。
#  基础语法
## 行分割符

 在`Go`程序中，每一句的结尾不需要向`Java`那样，必须以分号结尾，这些东西编译器帮我们完成，对于有强迫症，不喜欢代码中有无用的符号的人来说太合适不过了。

 但是如果想一行写多个语句的话，**就必须加上分号了**
 * 正确的写法

 ```go
 fmt.Println("我要学习Go")

 fmt.Println("先从Hello, World开始")

 ```
  * 错误的写法

 ```go
 fmt.Println("我要学习Go") fmt.Println("先从Hello, World开始")

 ```

 ## 注释
 日常开发中注释是一个很重要的东西，有些项目周期过长，可能自己写的代码过一段时间之后自己都不记得了，这个时候注释就发挥出它的作用了。

 注释很关键，但是我们又不能太依赖注释，**养成一个好的命名方式就是最好的注释**

 注释是不会被编译的

 ```go 
 /**
这
是一个
多行
的注释
*/
func main() {
	//这是一个单行注释
    fmt.Println("我要学习Go")
	fmt.Println("先从Hello, World开始")
}

 ```

 规范的命名方式，基本上是不需要注释的，注释可以写一些当时特殊的情况
 ```go
 func abc() string {
	//这是一个获取用户名称的方法
	return "张三"
}

func getUserName() string {

	return "张三"
}

 ```
 ## 标识符

 标识符用来命名变量、类型等程序实体，必须以字母或者下划线开头，不能是数字和关键字。

 ```go
 //这是正确的
var a string = ""
var a123 string =""
var _a string = ""
//这些是错误的
var 1a string = ""
var case string =""

 ```
 ## 函数
 `Go`里面的函数是由`func`声明
 ```
 func function_name( [parameter list] ) [return_types] {
   函数体
}
 ```
 基本上与`java`语言是类似的，由`名称`,`参数`,  `函数体`,`返回类型`组成，唯一不同的是`Go`可以返回多个多个值
 ```
 package main

import "fmt"

func swap(x, y string) (string, string) {
   return y, x
}

func main() {
   a, b := swap("Go", "Java")
   fmt.Println(a, b)
}
 ``` 

> 执行结果为 Go,Java
## 条件语句
### 语法

 ```
 if 布尔表达式 {
   /* 在布尔表达式为 true 时执行 */
}
 ```
 ### 实例

 ```go
 package main

import "fmt"

func main() {
  if 1 < 20 {
     
       fmt.Printf("1 小于 20\n" )
   }
}
 ```
 > `Go`的条件语句可以不加小括号的