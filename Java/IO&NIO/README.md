# IO vs NIO

IO(Input/Output) 과 NIO(New Input/Output) 은 Data를 입출력하는 것은 동일하지만, 방식에서는 차이가 많이 납니다.



### 입출력 방식

`IO`는 `Stream`을 기반으로 하며, `InputStream`과 `OutputStream`으로 구분이 되어있기 때문에 Data를 read하기 위해서는 `FileInputStream`을 생성해 주어야 하며,  Data를 Write하기 위해서는 `FileOutputStream`을 생성해 주어야 합니다. 

`NIO`는 `Channel`을 기반으로 하며, `Stream`은 `Input, Output Stream`이 구별되어 있지만, NIO는 `FileChannel` 하나만으로 Data를 read,write할 수  있다.



### 버퍼 방식

`IO`에서는 출력 `Stream`이 1바이트를 write를 쓰면 `InputStream` 이 1Byte를 읽는다. `IO`는 `Non-Buffer` 방식이기 때문에 느리므로 `BufferedInputStream, BufferedOutputStream`을 연결해서 쓰기도 합니다. 

`NIO`는 기본적으로 `Buffer`를 사용합니다. `Channel`은 `Buffer`를 이용해서 `Data Input, Output` 을 합니다.



### 블로킹 방식

`IO`는 `blocking` 상태입니다. `InputStream`의 `read() Method`가 호출되면 Data 입력전까지  `Thread`는 대기 상태(blocking)가 되며, `OutputStream`의 `write() Method`가 호출되면 Data가 출력되기 전까지 `Thread`는 대기 상태가 됩니다. `NIO`는 `Input, Output` 상태에서 `Thread`가 `blocking` 되지 않기 때문에 `Interrupt`를 씀으로서 빠져나올 수 있다는 것입니다.

