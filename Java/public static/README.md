# public static void main : reason

`Java Main`은 프로그램에서 가장 먼저  실행되는 시작점입니다. 

그러한 시작점인 `Main` 부분이 왜 `public static void Main` 인가? 입니다. 

`public` - 접근 제어자 ( 모든 클래스에 접근이 가능한 접근 제어자 )

`static` - 정적 

`void` - return 값 미존재

이러한 형식인 이유는 , `Main`이 Java에서의 프로그램의 시작과 끝이기 때문에, 

프로그램이 시작되기 전, 메모리에 올려져 있어야 `Main`이 사용가능하기 떄문입니다. 

이 점 때문에 `static` 입니다.

또한  `public`이 아닌 `default`, `protected`, `private`이라면, 

다른 클래스에서 이 `Main`을 사용할 수 없고 

접근할 수 없기 때문에, `Main`은 모두 접근할 수 있게 해야 되기 때문에 `public` 입니다.

`void`인 이유는 `Main`이 끝이 난다면, 프로그램은 끝이 난다는 이야기입니다. 즉 `return` 값이 있어도,

아무 의미가 없기 때문에, `void`를 사용하는 것입니다.



즉,  모든 클래스들이 접근 가능하여야 하고, 시작되기 전 메모리에 올려져 있어야 하며, 끝이 나면 `return`값에는 의미가 없기 때문에 `Java`의 `Main`은 `public static void main` 입니다.