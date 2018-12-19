# 最大打开文件数要求

推荐的打开文件描述符的最大数量是10000，或者更大。可以通过在每台主机上执行以下shell命令来查看当前打开文件描述符的最大值：

`ulimit -Sn`

`ulimit -Hn`

`如果输出的结果小于10000，运行以下命令给其设置一个合适的默认值：`

`ulimit -n 10000`

## More Information

[ulimit详解](https://www.jianshu.com/p/b4aadb88b19a)

