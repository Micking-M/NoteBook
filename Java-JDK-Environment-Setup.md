---
title: Java JDK 环境搭建
date: 2020-12-17 13:30:53
categories:
- [Java]
tags:
- Java
- JDK
- 环境搭建
cover: https://img-blog.csdnimg.cn/20210313223823976.jpg
---

# 【Java JDK 环境搭建】

> 原创内容，转载请注明出处！

# 一、为什么 Java JDK 要配置环境变量

**配置环境变量，可以使 `jdk 工具` 全局生效！**

当我们没有配置 jdk 的环境变量时，在 jdk/bin 目录外是运行不了 `javac.exe` (java 编译器) 和 `java.exe` (java 解释器) 的。

当然我们也可以去 jdk/bin 目录下运行 java 程序，但问题是在 bin 目录下通过启动 javac.exe 把一个 `.java` 文件编译成 `.class` 文件后，这个 `.class` 文件就直接生成在 jdk/bin 目录里了，这样的文件组织方式显然是不好的。

所以我们需要把 jdk 配置到 path 里面，这样在任何目录下（全局）都能运行 javac.exe 和 java.exe 来编译解释 java 程序了，同时也就防止了 jdk/bin 目录里存在许多的 .java 文件和 .class 文件。

# 二、环境变量全局识别的原理

当在命令行中执行的程序不存在时，Windows 系统会在本地已有的一个名为 `path` 的环境变量中查找路径列表中是否存在目标程序。

# 三、环境变量配置步骤

## 3.1 情况1

对于单纯的 Java SE 开发来说：

- 找到 jdk 安装目录，复制 `\jdk\bin` 路径
- 控制面板 ——> 系统 ——> 高级系统设置 ——> 高级 ——> 环境变量 ——>系统变量
- 找到 `path` 变量 点击编辑
- 添加 `\jdk\bin` 路径
- 逐个确定退出

## 3.2 情况2

对于 Java SE & Java EE 开发来说：

- 找到 jdk 安装目录，复制 `\jdk\bin` 路径

- 控制面板 ——> 系统 ——> 高级系统设置 ——> 高级 ——> 环境变量 ——>系统变量
- 点击 新建变量
- 变量名：`JAVA_HOME`
- 变量值：`\jdk` 路径
- 点击确定
- 找到 `path` 变量 点击编辑
- 添加 `%JAVA_HOME%\bin`
- 逐个确定退出

# 四、配置测试

- 打开 命令行
- 输入 `javac`
- 输入 `java`
- 输入 `java -version`

若以上命令成功识别，则配置成功。

# 五、解释

1. **为啥要配置 JAVA_HOME，一定要用 JAVA_HOME 命名吗？**

电脑如果装了多个版本的 jdk，我们只需要在 `JAVA_HOME` 中把需要的 jdk 目录添加进去，而不用在 path 里面加 bin 目录的路径，这样可以防止多个版本调用时的版本不确定性。

同时有些 Java 开发工具，如（Eclipse、IDEA、Tomcat）都会去扫描 JAVA_HOME 变量，看看电脑装了几个版本的 jdk，确定使用哪一个。

若不用 JAVA_HOME 这个名字当参数名，那么当这些软件需要检索 JAVA_HOME 时，就需要先去手动修改相应的配置文件，才能使用这些软件，并且即便修改后也有发生故障的可能性，何必呢？

2. **为什么没有配置 CLASSPATH 变量？**

jdk1.5 之后就不用再配置 `CLASSPATH` 了。当然某时为了保证向下兼容，也可以配置上为好。