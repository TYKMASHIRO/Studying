[← BACK TO BLOG](https://openwebgal.com/zh-cn/blog/)

# RFC3：WebGAL 流程图技术解决方案（草案）

Mahiru

2024-1-20

\#RFC

第一次提交版本，2024年1月20日。

## 总体方案

WebGAL 在游戏运行的过程中记录流程图解锁情况。用户必须首先在WebGAL编辑器中使用流程图编辑器编辑流程图。

## 章节注册

使用流程图编辑器，将流程图的节点和流程图中要继续的位置对应起来。比如类似于

```json
{
    "节点1":{
        "sceneName":"xxx.txt"
    }
}
```

这里的意思是，用户点击了这个节点后，游戏回到 `xxx.txt` 继续。

**舞台状态和 backlog 被重置到流程图解锁时的状态**。

## 渲染算法

是一个图（图是一种数据结构）的遍历，从根开始，使用 BFS ，**每一层**被渲染为视图中的**一行**，并使用箭头连接父章节和子章节。

点击节点**就是读档**，读的是这个结点解锁时的状态。

## 如何存储

在每个 scene 开始的时候，假如我们发现该 scene 被注册到了图，那么就记录这个 scene 进入时的初始状态（舞台状态、Backlog什么的），解锁对应的结点。

“记录”这个过程，就是存一个状态快照，这个状态快照我们宣称其是章节，跳转到某个章节就是读取这个快照。

由于图中的每一个结点就是一个状态快照，所以为了防止存读档效率下降，将单个存档作为单个 key 存储已经势在必行。并且，章节的状态快照不记录 Backlog，所以跳转章节后清空 Backlog。

## 注册个人线

允许注册多个流程图。流程图的属性里面可以设置个人线的相关配置。