源码与编译后字节码分离
===================
在当前目录下，新建文件夹classes
scalac -d ./classes src/com/mine/hello/Utils.scala
scalac -d ./classes -cp ./classes src/HelloWorld.scala

scala -cp ./classes Hello

java -cp .:/usr/local/scala-2.12.11/lib/scala-compiler.jar:/usr/local/scala-2.12.11/lib/scala-library.jar:./classes Hello


打包
===

jar cvf libs/utils.jar -C classes com/mine/hello/Utils.class -C classes 'com/mine/hello/Utils$.class'
---打包成lib/utils.jar

scalac -d ./classes -cp libs/utils.jar src/HelloWorld.scala
---编译

jar cvf libs/hello.jar -C classes Hello.class -C classes 'Hello$.class'
---打包成lib/hello.jar

scala -cp libs/utils.jar:libs/hello.jar Hello
---通过jar包运行

java -cp .:/usr/local/scala-2.12.11/lib/scala-compiler.jar:/usr/local/scala-2.12.11/lib/scala-library.jar:./libs/utils.jar:./libs/hello.jar Hello

文件名包含特殊字符
===============
参考资料：https://linux.cn/article-5777-1.html