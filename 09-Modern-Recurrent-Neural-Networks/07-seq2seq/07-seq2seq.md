## 序列到序列学习

![](07-seq2seq.assets/image-20221109113025123.png)



![](07-seq2seq.assets/image-20221109113045394.png)



## seq2seq

![](07-seq2seq.assets/image-20221109113127064.png)



双向 LSTM 可以作为 `Encoder` 来使用

可以使用 RNN 作为 `Decoder` 来使用

![image-20221109212638294](07-seq2seq.assets/image-20221109212638294.png)



## 一些细节

`Encoder` 没有输出，而 `Decoder` 把 `Encoder` 中的状态直接作为了 `Decoder` 的输入

![](07-seq2seq.assets/image-20221109214349121.png)


## 输入

![](07-seq2seq.assets/image-20221109214713912.png)



## 衡量生成序列的好坏

![](07-seq2seq.assets/image-20221109214841674.png)



## 总结

![](07-seq2seq.assets/image-20221109215307722.png)





