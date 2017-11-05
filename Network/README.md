
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

Router는 Data를 어떻게 출발점에서 목적지까지 전달하는가?

`packet-switching` ( Internet에서 사용 ), `circult - switching`

##### Circult- Switching

출발지에서 목적지로 가는 길을 미리 정해놓고 특정 사용자만을 사용하기 위해 하는 것 ( ex) 예전 유선전화망 ) 

##### packet- Switching

User가 보내는 Message를 Packet 단위로 forwarding 해주는 것 

##### packet-Switching vs Circult-Switching

같은 link가 있을때, Internet을 사용하는 것이 사용자는 간헐적이기 때문에, 분산되어 사용할 수 있는 `packet - Switching` 이 적합합니다.  

##### Router에서 생기는 Delay ( Delay in Packet switched networks )

만약에 운이 나쁘게도, 여러명이 동시 접속할 경우, `packet-switching`은 router가 내보내주는 속도보다 많은 사용자가 있다면, router에서 packet을 검사하는 것을 `processing delay`라고 합니다. 또한 정보가  유실될수 있기 때문에 임시 `buffer(Queue)`가 router에 존재하여 임시 저장을 해주고 Queue에 있는 대기자는 순서가 올때까지 계속 기다립니다. 이를 `queueing delay` 라고 합니다. 첫번째 비트가 나가는 순간부터, 마지막 비트가 나오는 순간까지는 `Transmission delay` 시간이라고 합니다. 또한 마지막 비트가 나온 순간부터, 그 다음 router까지 걸리는 시간을 `Propagation delay` 라고 합니다.

* `processing delay` 는 router의 성능을 높이면 개선한다.
* `Transmission delay`는 케이블 갯수(회선)를 늘리면 개선된다.
* `Queueing delay`는 사람들의 인터넷 습관이 다르기 때문에 조절할 수가 없다.

Queue보다 넘치는 경우 버려야하기 때문에 사람이 많을 경우 Packet - loss (유실)이 발생한다.

Packet -  loss 시에는 처음부터 재전송을 해줍니다.

TCP에서 재전송을 해주며 가는 길은 dump - core를 통해 전달합니다.