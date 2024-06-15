---

title: 'C++20 Moudle 模块'
pubDate: 'Jun 15 2024'
heroImage: '/blog-placeholder-2.jpg'
description: 'C++20 Moudle 模块在OI中的应用'

---

 

## 作用

当你需要调用某个头文件成百上千次，那么，gcc会把这个头文件编译成百上千遍，这无疑是无意义的

模块就是用来解决这个问题，提高效率的

## 用法

```cpp
export module 名称;
// code
```

```cpp
import 名称
```

## C++23

C++23,有一个新的语法，如下：

```cpp
import std;
```

它可以一键导入所有模块

## In OI

~~其实模块在OI中用处不大，但是~~对压行爱好者来说，这是非常好的功能（可以压成一行啦!）

以及`cpp.sh`、`LLVM`、`MSVC`不支持万能头，就可以使用它

当您尝试写一个[大模拟](https://www.luogu.com.cn/problem/P2482)的话，这或许比较有用吧

注：主流编译器尚未支持
