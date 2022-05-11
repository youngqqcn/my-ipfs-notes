# my-ipfs-notes
学习ipfs笔记


IPFS官方文档：https://docs.ipfs.io/



## IPFS是什么？

> 原文：http://docs.ipfs.io.ipns.localhost:8080/concepts/what-is-ipfs

IPFS链接示例：

```
https://ipfs.io/ipfs/QmXoypizjW3WknFiJnKLwHCnL72vedxjQkDDP1mXWo6uco/wiki/Aardvark.html
```

其中`ipfs.io`是Gateway。`QmXoypizjW3WknFiJnKLwHCnL72vedxjQkDDP1mXWo6uco`是文件内容的hash值，用于定位文件。

ipfs通过内容进行寻址


问题：我把文件通过IPFS分享，是否可以永不丢失？
答：不是的。IPFS依赖“参与”模式，也就是说，你把文件通过IPFS进行分享，如果别人拷贝了这份文件，那么这分文件就有2份，其他人要获取这个文件，可以有2个选择，但是前提是，拥有这两份文件的电脑必须在线。如果你分享的文件，没有其他人拷贝，那么一旦你的电脑关机或者文件丢失，别人就不能获取到这份文件。



## IPFS是如何工作的？

> 原文：http://docs.ipfs.io.ipns.localhost:8080/concepts/how-ipfs-works/



视频：https://www.youtube.com/watch?v=Z5zNPwMDYGg

CID拆分：

http://cid.ipfs.io.ipns.localhost:8080/


http://cid.ipfs.io.ipns.localhost:8080/#QmXoypizjW3WknFiJnKLwHCnL72vedxjQkDDP1mXWo6uco



DAG：

https://dag.ipfs.io/

balanced：平衡模式
trickle



### 内容寻址



### DAGs（有向无环图）

http://explore.ipld.io.ipns.localhost:8080/#/explore/QmSnuWmxptJZdLJpKRarxBMS2Ju2oANVrgbr2xWbie9b2D



### DHTs(分布式哈希表)

libp2p

https://github.com/ipfs/specs/blob/master/BITSWAP.md


总结：
分割：IPFS对文件进行分割成小块，每个小块都有对应的CID
DAG：每个小块的CID构成Merkle DAG
libp2p：通过libp2p建立连接，只建立一个连接，多路复用，下载文件块
