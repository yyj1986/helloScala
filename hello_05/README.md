包机制之一
=========
scala 的包，可以不对应目录结构  (这一点比java方便)

Utils.scala 增加
package com.mine.hello

scalac Utils.scala

HelloWorld.scala 增加
import com.mine.hello._

scalac -cp . HelloWorld.scala
scala -cp . Hello

java -cp .:/usr/local/scala-2.12.11/lib/scala-compiler.jar:/usr/local/scala-2.12.11/lib/scala-library.jar Hello