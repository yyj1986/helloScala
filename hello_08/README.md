自执行jar包
==========

scalac -d ./classes src/com/mine/hello/Utils.scala
scalac -d ./classes -cp ./classes src/HelloWorld.scala

manifest.txt
============
Main-Class: Hello
Class-Path: scala-library.jar scala-compiler.jar

通过MANIFEST.MF中的Class-Path 来指定运行时需要用到的其他jar，其他jar可以是当前路径，也可以是
当前路径下的子目录。但不能包含在当前jar里面。Class-Path的冒号后面必须要空一个空格，否则会出错
文件的最后一行必须是一个回车换行符，否则也会出错

cp /usr/local/scala-2.12.11/lib/scala-compiler.jar libs/
cp /usr/local/scala-2.12.11/lib/scala-library.jar libs/
jar cvf libs/hello.jar -C classes Hello.class -C classes 'Hello$.class'
---打包成lib/hello.jar

jar cmvf manifest.txt libs/hello.jar -C classes .
已添加清单
正在添加: Hello.class(输入 = 619) (输出 = 509)(压缩了 17%)
正在添加: com/(输入 = 0) (输出 = 0)(存储了 0%)
正在添加: com/mine/(输入 = 0) (输出 = 0)(存储了 0%)
正在添加: com/mine/hello/(输入 = 0) (输出 = 0)(存储了 0%)
正在添加: com/mine/hello/Utils.class(输入 = 592) (输出 = 469)(压缩了 20%)
正在添加: com/mine/hello/Utils$.class(输入 = 550) (输出 = 374)(压缩了 32%)
正在添加: Hello$.class(输入 = 999) (输出 = 599)(压缩了 40%)


java -jar libs/hello.jar
--执行jar包
Hello sum: 5

后续
====

参考 kotlin include-runtime
可以把 kotlin 相应的 class 文件放入 jar 包中
这样可以省略 Class-Path处理，从而把scala-compiler, scala-library的class放入 jar 包中
