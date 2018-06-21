# GarBage Collector

`garbage collection`(가비지 컬렉션)은 메모리 관리를 위한 방법 중의 하나로, 프로그램이 동적으로 할당했던 메모리 영역 중에서 필요없게 된 영역을 해제하는 기능입니다. ( new 연산자를 이용한 객체 등 ..)



## Java Garbage Collector 

`Java GC`는 객체가 garbage인지 판단하기 위해 reachability 개념을 사용하여 객체의 유효한 참조가 있다면 'reachable' 로 없으면 'unreachable' 로 구별하고, unreachable 객체를 Garbage로 간주하여 GC가 실행되게 됩니다. 한 객체가 다른 객체를 참조하며, 다른 객체는 또다른 객체를 참조할 경우에는 유효한 최초의 참조가 무엇인기 파악해야 되는데, 이를 객체 참조의 root set이라고 합니다.

힙에 있는 객체들에 대한 참조는 다음 4가지 종류 중 하나입니다,

- 힙 내의 다른 객체에 의한 참조
- Java 스택, 즉 Java 메서드 실행 시에 사용하는 지역 변수와 파라미터들에 의한 참조
- 네이티브 스택, 즉 JNI(Java Native Interface)에 의해 생성된 객체에 대한 참조
- 메서드 영역의 정적 변수에 의한 참조

이들 중 힙 내의 다른 객체에 의한 참조를 제외한 나머지 3개가 root set으로, reachability를 판가름하는 기준이 된다. 즉 root set으로부터 시작한 객체들은 reachable이며, root set과 무관한 객체들이 unreachable 객체로 GC의 대상이 되게 됩니다.
