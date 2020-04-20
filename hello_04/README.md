参考资料:
http://www.scalatest.org/quick_start

scalac Utils.scala
scalac -cp .:/usr/local/scala-2.12.11/lib/scalatest_2.12-3.1.1.jar:/usr/local/scala-2.12.11/lib/scalactic_2.12-3.1.1.jar TestUtils.scala
warning: there were two deprecation warnings (since 3.1.0); re-run with -deprecation for details
one warning found

scala -cp .:/usr/local/scala-2.12.11/lib/scalatest_2.12-3.1.1.jar:/usr/local/scala-2.12.11/lib/scalactic_2.12-3.1.1.jar org.scalatest.run TestUtils
Run starting. Expected test count is: 1
TestUtils:
- should 两数之和
Run completed in 89 milliseconds.
Total number of tests run: 1
Suites: completed 1, aborted 0
Tests: succeeded 1, failed 0, canceled 0, ignored 0, pending 0
All tests passed.

scalac -cp . HelloWorld.scala
scala -cp . Hello
java -cp .:/usr/local/scala-2.12.11/lib/scala-compiler.jar:/usr/local/scala-2.12.11/lib/scala-library.jar Hello