# Iperf

网络性能测试工具[iperf](https://iperf.fr/)

## TCP
测量网络带宽
报告MSS/MTU值的大小和观测值
支持TCP窗口值通过套接字缓冲
当P线程或Win32线程可用时，支持多线程。客户端与服务端支持同时多重连接

* 在服务端运行iperf，输入命令iperf –s –p 12345 –i 1 –M 以在本机端口12345上启用iperf;
* 在客户端运行iperf，输入命令iperf –c server-ip –p server-port –i 1 –t 10 –w 20K，其中参数说明如下：
```
-c：客户端模式，后接服务器ip
-p：后接服务端监听的端口
-i：设置带宽报告的时间间隔，单位为秒
-t：设置测试的时长，单位为秒
-w：设置tcp窗口大小，一般可以不用设置，默认即可
```

## UDP

客户端可以创建指定带宽的UDP流
测量丢包
测量延迟
支持多播
当P线程可用时，支持多线程。客户端与服务端支持同时多重连接（不支持Windows）


* 在服务端运行iperf，输入命令iperf –s -u –p 12345 –i 1 以在本机端口12345上启用iperf，并运行于udp模式
* 在客户端运行iperf，输入命令iperf -c server-ip -p server-port -i 1 -t 10 -b，其中参数说明如下：
```
-c：客户端模式，后接服务器ip
-p：后接服务端监听的端口
-i：设置带宽报告的时间间隔，单位为秒
-t：设置测试的时长，单位为秒
-b：设置udp的发送带宽，单位bit/s
```


Iperf还有一个图形界面程序叫做Jperf，使用JPerf程序能简化了复杂命令行参数的构造，而且 它还保存测试结果,同时实时图形化显示结果。当然，JPerf可以测试TCP和UDP带宽质量。JPerf可以测量最大TCP带宽，具有多种参数和UDP 特性。JPerf可以报告带宽，延迟抖动和数据包丢失。为了测试的准确性，尽量使用linux环境测试。