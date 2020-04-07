# IO

* 初级学习目标：结合场景正确IO相关API

* 应用场景：

  1. 网络IO：网络数据的操作
  2. 文件IO：本地文件的操作

  * 都是阻塞式的IO

### 流

1. 数据的流向(一个设备流向另一个设备)

2. 设备从输出输入来分，不同视角表现为不同输出设备或输入设备(一般我们所说输出输入是在Java程序的角度来说)

   1. 硬盘-> <- 系统内存 -> <- JVM内存 (-><- 特定条件相互转换)

3. 流的操作只能执行一次

4. Java中IO流的分类：

   1. 字节丶字符流：
      1. 字节：InputStream，OutputStream
      2. 字符：Writer，Reader
   2. 输出输入：
      1. 输出：Output，Reader
      2. 输入：Input，Writer
   3. 文件：带File的IO类，作为文件操作的IO流
   4. 二进制数组：ByteArray
   5. Java对象：Object
   6. 特殊：
      * PrintWriter:表示打印输出到某个设备
      * Scanner:表示接收某个设备的输入(接收控制台输入时，从System.in键盘作为输入设备来的)
      * StringWriter:
      * StringReader:

5. Java中的IO流，是可以包裹其他IO流的。

6. 字节转换为字符流，需要使用字节字符转换流；转换流可以设置编码：java文件的编码格式，文件编码格式

   1. InputStreamReader：输入的字节字符转换流
   2. OutputStreamWriter：输出的字节字符转换流

7. 缓冲流：

   * 使用缓冲流输出时要用flush刷新缓冲区，否则不会真实输出数据到目的设备

   1. BufferedWriter：字符缓冲输出
   2. BufferedReader：字符缓冲输入

8. 序列化与反序列化：

   1. 序列化：把对象转换为字节序列的过程称为对象的序列化
   2. 反序列化：把字节序列恢复为对象的过程称为对象的反序列化

   * 应用场景：
     * 把内存中的对象状态保存到一个文件中或者数据库中的时候
     * 用套接字在网络上传送对象时
