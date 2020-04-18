脚本执行
=======

scala HelloWorld.sc

Hello sum: 5

交互环境
=======

$ scala
Welcome to Scala 2.12.11 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0_241).
Type in expressions for evaluation. Or try :help.

scala> object HelloWorld {
     | def sum(a: Int, b: Int): Int = {
     | 
Display all 411 possibilities? (y or n)
     | a + b
     | }
     | }
defined object HelloWorld

scala> val x HelloWorld.sum(2,3)
<console>:1: error: illegal start of simple pattern
       val x HelloWorld.sum(2,3)
                       ^

scala> val x = HelloWorld.sum(2,3)
x: Int = 5

scala> println(s"Hello sum: ${x}")
Hello sum: 5


scala> 

