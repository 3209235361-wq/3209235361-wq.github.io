# 源码解读笔记

嵌入式源码阅读与工程实践笔记。每篇都从实际构建、实际运行过的工程里读代码，结论尽量落到具体的函数和调用链上，不照抄手册。

在线阅读：<https://3209235361-wq.github.io/>

## 文章

| 文章 | 讲什么 | 环境 |
| --- | --- | --- |
| [RT-Thread 启动流程：从 Reset_Handler 到 main](rtthread_startup_line/startup_line_new.md) | 汇编阶段搬 `.data`/清 `.bss`、`SystemInit` 到底做了什么、`entry → rtthread_startup`、调度器启动后谁先跑 | STM32F103C8T6 + RT-Thread 4.0.3 + RT-Thread Studio 2.3.1 (GCC) |
| [内核对象分布：RT-Thread 怎么用一个数组管住所有内核对象](rtthread_kernel_obj_distribution/kernel_obj.md) | 对象容器数组、`rt_object` 内嵌链表、两种 type 枚举的区别、`rt_container_of` 怎么反推宿主结构 | RT-Thread 4.0.3 |

## 写作方式

- **只写读过的代码**：文中代码取自实际工程，标出所在文件与函数
- **拆成 Step**：一篇长文按「Step 1 / Step 2 / Step 3」推进，每步一个可以独立理解的小结论
- **留验证口子**：每篇结尾给出自己动手验证的方法（打断点、查符号表、改配置看现象）
- **写记错的点**：把常见误解单独列出来，而不是只讲正确流程

## 仓库结构

```
.
├── index.md                              站点首页（文章入口）
├── rtthread_startup_line/                启动流程一文 + 配图
└── rtthread_kernel_obj_distribution/     内核对象分布一文 + 配图
```

## 许可

[MIT](LICENSE)
