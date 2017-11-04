
# **NETWORK REVIEW** 

`Router` - 메시지를 전달받아서 목적지를 향해서 Data를 전달해 주는 역할

`NetWork Edge` - application ( WEB Broswer ), host

`NetWork Core` - Router들이 연결해서 목적지 연결 

`Link` - ( Network Edge - NetWork Core) 등을 서로 연결하는 것



### Network Edge 

`Client` - Network Edge 에 존재하는 컴퓨터 ( 자기가 원할 때 Server 에서 정보를 가져오는 요소 )

`Server` - 항시 24시간 켜져 있어 Client의 연결을 기다리는 것 ex) Web Server



##### 통신 서비스

Connetion - oriented Service 

`TCP service`   : Connection-oriented Service를 제공해주는 서비스

- Reliable : Server에게 Data를 보내면 Message가 그대로 감
- In-order-byte stream : 보낸 순서대로 Data가 감
- flow control : Receiver가 받아들일 수 있는 정보의 속도로 전달
- congestion Control : Receiver, Sender 사이의 NetWork 환경에 맞춰서 전달

TCP : Transmission Control Protocol 

##### Connectionless Service

`UDP service` : Connectionless Service를 제공해주는 서비스

* connectionless, unreliable data transfer, no flow control , no congestion control : 아무것도 제공해 주지 않는다.



`TCP / UDP` 는 TCP는 컴퓨터 리소싱이 많이 들고, UDP는 안전성이나 데이터 유실성이 있다.



##### Protocol 이란? 

둘 사이에 이야기하는 암묵적인 방식 ( Internet에서 중요한 메시지를 주고 받기 전에 준비하는 것 )

TCP <-> TCP / UDP <-> UDP



### NetWork Core

Network 중심에는 Router가 Data를 목적지까지 전달해준다. ( Router들끼리 얽히고 있음 )

Router는 Data를 어떻게 출발점에서 목적지까지 전달하는가? packet-switching ( Internet에서 사용 ), circult - switching



Circult- Switching