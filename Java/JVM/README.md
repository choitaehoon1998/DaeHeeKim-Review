# JVM

`JVM ( Java Virtual Machine)` 이란 `Java Byte Code`를 실행할 수 있습니다. 

( 즉, Java를 실행하기 위한 가상 머신입니다. ) - 구현 방식은 인터프리터나 JIT 컴파일 방식으로 다른 컴퓨터 위에서 ByteCode를 실행할 수 있게 해줍니다.

`Java ByteCode` : JVM 이 실행하는 명령어의 형태입니다. ( java code -> decomplie -> Byte Code )

`interpreter` : 프로그래밍의 언어의 소스코드를 바로 실행하는 컴퓨터 프로그램 또는 환경 

 원시코드 -> 기계어 (x)  / Compiler가 이렇습니다. )

`JIT 컴파일(just-in-time compilation)` ,`동적 번역(dynamic translation)` : JVM에서 프로그램을 실제 실행하는 시점에 기계어로 번역하는 컴파일 기법 ( 실행 시점시 기계어 코드를 실행하고, 여러번 반복된 것은 다시 생성하지 않음 (캐싱 방법 사용) )

이론적으로 표준 Java API 까지 동이란 동작을 하도록 한 상태에서 작동되는 Java Programm은 CPU나 OS와는 

무관하게, 항상 성능을 보장한다고 합니다. ( 실제로는 당연히 변수가 많겠죠? )

* JVM Architecture 

## ![JvmSpec7](C:\Users\anyoz\OneDrive\Project\StiKuan-Review\Java\JVM\JvmSpec7.png)

## JVM의 특징

* Stack 기반의 가상 머신

* 포인터를 지원하지만 , C와 같이 주소값을 임의로 조작한 포인터 연산 불가능 ( unsafe 라고 뜹니다. )

* GC(Garbage Collector) 사용

* 모든 basic type의 정의를 명확히 함

  ​

## JVM의 사양

`Java ClassLoader` : JVM을 동적으로 Load하는 Java RunTime Error의 일부입니다. 또한 Java .class File을 RunTime시 동적으로 Load 합니다.

`Java ByteCode` : JVM이 실행하는 명령어의 형태입니다. ( JVM -> decomplier )

`Java Virtual Machine Language` : JVM 위에서 실행될 수 있도록 ByteCode 생성하거나, JVM 위에서 실행되는 Interprint를 지원하는 언어를 말합니다.