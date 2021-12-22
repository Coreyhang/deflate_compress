# Deflate Compress

### [Huffman编码](https://zh.wikipedia.org/wiki/%E9%9C%8D%E5%A4%AB%E6%9B%BC%E7%BC%96%E7%A0%81)

#### Huffman最大编码长度

* 定理1: 在哈夫曼树的构造过程中,高层节点的概率不高于低层节点的概率
* 定理2: 哈夫曼树根节点的概率为`1`
* 定理3: 若某个节点概率为`p`,长度为`L`,那么这个节点的概率满足

<img src="https://latex.codecogs.com/png.image?\dpi{110}&space;\bg_white&space;L\leq&space;\log_2\cfrac{1}{p}&space;&plus;&space;1" title="\bg_white L\leq \log_2\cfrac{1}{p} + 1" />

因此，对于32KB大小的数据块，采用8bits字符长度，最大huffman编码长度为`16`。

参考链接：
1. [哈夫曼编码最大编码长度](https://blog.csdn.net/Mrfive555/article/details/86770192)
2. [信息熵最大值的证明](http://www.math345.com/blog/article/17)

#### Huffman编码后最大总长度

编码后，Huffman平均编码长度的上界为：

<img src="https://latex.codecogs.com/png.image?\dpi{110}&space;\bg_white&space;mean(L)\leq&space;\log_2{256}&space;&plus;&space;1=9\text{bits}" title="\bg_white mean(L)\leq \log_2{256} + 1=9\text{bits}" />

因此经过huffman编码之后，数据量可能会超过编码前的数据量。
