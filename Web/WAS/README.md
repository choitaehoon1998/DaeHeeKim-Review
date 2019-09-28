
# **Web Application Server(WAS)**

`Web Application Server` 는 인터넷 상에서 `HTTP`를 통해 사용자 컴퓨터나 장치에 Application을 수행해 주는 `소프트웨어 엔진`이다. WAS는 이러한 기능이 있습니다.

- 프로그램 실행 환경과 데이터베이스 접속 기능을 제공한다.

- 여러 개의 트랜잭션을 관리한다.

- 업무를 처리하는 비즈니스 로직을 수행한다.

대표적인 예시로는 `Zeus`, `Weblogic`, `Jboss` 등이 있지만. 저는 `Apache Tomcat`을 주로 쓰기 때문에
`Apache Tomcat`을 설명할 것입니다.



#### 용어 설명


`HTTP (HyperText Transfer Protocol)` : WWW 상에서 정보를 주고받을 수 있는 프로토콜 ( 통신 규약 )

`World Wide Web ( WWW, W3, Web )` - 인터넷에 연결된 컴퓨터들을 통해 사람들이 정보를 공유할 수 있는 공간

`Internet` - TCP/IP 라는 통신 프로토콜을 이용해 정보를 주고받는 컴퓨터 네트워크

`TCP/IP` - 인터넷에서 컴퓨터들이 정보를 주고받는데 쓰이는 통신규약 ( 프로토콜 )



#### WAS와 Web Server의 차이 

`Web Server`는 웹 브라우저(`Web Client`)에게 Contents를 제공하는 서버이고, 정적인 HTML이나 jpg,gif 등의 image를 http 프로토콜을 통해 웹 브라우저에게 제공합니다.   `WAS`는 Application을 동작할 수 있도록 지원하며, 현재는 `Serlvet, JSP, asp, php`등의 프로그램에도 이용되고 있습니다.



### Apache Tomcat 이란 

`Apache`란, `apache`라는 오픈소스 소프트웨어 재단에서 만든 `HTTP WEB SERVER`입니다. `HTTP Web Server`란 웹 브라우저와 같은 `Web Client`(ex. chrome) 로부터 HTTP 요청을 받아들이고, `HTML, Image, CSS , JS`를 포함한 `HTML` 문서를 `Client`로 반환시키는 서버 입니다.

`Tomcat`이란, `WAS(Web Application Server)`이며 (Web Server + Web Container)의 결합이며 다양한 기능을 컨테이너에 구현하여 동적으로 Data를 처리할 수 있는 Server이며, Client의 요청이 있을시 프로그램을 통해 결과를 다시 Client에 전달해 주는 역할을 합니다. 또한 `Web Server`와 연동하여 실행할 수 있는 `Java` 환경을 제공하여 `JSP`와 `Serlvet`이 실행될 수 있도록 하고 있습니다.

`Serlvet` : `Java`를 사용하여 웹페이지를 동적으로 생성하는 `Server` 프로그램

### HTTP와 HTTPS 의 차이 

`HTTPS(Hypertext Transfer Protocol over Secure Socket Layer)`는 HTTP의 보안이 강화된 버전으로서 S는 secure Socket의 약어 즉, 안전한 통신망을 의미한다고 보시면 됩니다. 암호화를 하는 방법은 간단합니다. **공개키** 방식을 사용해서 암호화를 진행합니다



### Cookie 와 Session

`Cookie`란 Server에서 Client측에 상태정보를 저장하고 추출해 주는 것으로서 Client의 요청마다 Browser로부터 Server에게 전송되는 패킷의 일종입니다.  ( Key와 value가 들어있는 작은 Data 파일입니다. )

`Session`이란 Client와 Server간의 NetWork 연결이 유지되어 있는 상태를 말하며, 사용자가 Broswer를 켜서 Server 접속 후, 연결을 종료한 시점까지를 말합니다. 그 때 Client가 Web Server에 Request를 보내면 Server가 ID를 부여하는데 이를 `Session`이라고 합니다. 

둘의 가장 큰 차이점은 저장 위치가 `Cookie`는 Client, `Session`은 Server에 저장이 된다는 점이 차이점이 있습니다. 또한 `Session`이 보완이 더 잘 된다는 장점이 있지만 Server의 자원을 사용하기 때문에 그때그때 용도에 따라 잘 사용 해야합니다. 



### Cache

프로그램이 수행될 때 나타나는 지역성을 이용하여 메모리나 디스크에서 사용되었던 내용을 특별히 빠르게 접근할 수 있는 곳에 보관하고 관리함으로서 이를 관리함으로서 보다 빠르게 참조하도록 하는 것이다.