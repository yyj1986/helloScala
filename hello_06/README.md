包机制之二
=========
为了与java更好的对接，scala 的包对应目录结构

把Utils.scala移到 com/mine/hello 子目录下

Utils.scala 增加
package com.mine.hello

scalac com/mine/hello/Utils.scala

HelloWorld.scala 增加
import com.mine.hello._

scalac -cp . HelloWorld.scala
scala -cp . Hello
Hello sum: 5

java -cp .:/usr/local/scala-2.12.11/lib/scala-compiler.jar:/usr/local/scala-2.12.11/lib/scala-library.jar Hello
Hello sum: 5