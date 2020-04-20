参考资料

https://guides.gradle.org/building-scala-libraries/

程序目录结构要遵从src/main/scala....

gradle init --type scala-library

build.gradle 文件

plugins {
    // Apply the scala plugin to add support for Scala
    id 'scala'

    // Apply the java-library plugin for API and implementation separation.
    id 'java-library'
}

repositories {
    // Use jcenter for resolving dependencies.
    // You can declare any Maven/Ivy/file repository here.
    jcenter()
}

dependencies {
    // Use Scala 2.13 in our library project
    implementation 'org.scala-lang:scala-library:2.13.1'

    // Use Scalatest for testing our library
    testImplementation 'junit:junit:4.12'
    testImplementation 'org.scalatest:scalatest_2.13:3.1.0'
    testImplementation 'org.scalatestplus:junit-4-12_2.13:3.1.0.0'

    // Need scala-xml at test runtime
    testRuntimeOnly 'org.scala-lang.modules:scala-xml_2.13:1.2.0'
}

gradle build

scala -cp build/libs/hello_09.jar hello_09.Hello