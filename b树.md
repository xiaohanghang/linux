# B树

> 我们前面讨论的数据结构，处理数据都是在内存中，因此考虑的都是内存中的运算时间复杂度，如若我们要操作的数据非常大，内存已经无法处理了，在这种情况下，对数据的处理需要不断从硬盘等存储设备中调入或者调出内存页面，为了降低对外存设备的访问次数，我们需要新的数据结构来处理这样的问题。
>
> 试想一下，为了要在一个拥有几十万个文件的磁盘中查找一个文本文件，你设计的算法需要读取磁盘 上万次还是读取几十次，这是有本质的问题，为了降低对外存设备的访问次数，我们就需要新的数据结构来处理这样的问题。

在一个典型的B树应用中，要处理的硬盘数据量很大，因此无法一次性全部装入内存中，因此我们会对B树进行调整，使得B树的阶数于硬盘存储的页面大小相匹配，比如说一颗树的阶数为1001（即1个节点包含1000个关键字），高度为2 ，它可以存储超过10亿个关键字，我们只要让根节点持久化的保留在内存中，那么在这颗树上，

