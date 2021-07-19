# TCP, UDP

## TCP(Transmission Control Protocol)

##### 인터넷상에서 데이터를 메세지의 형태로 보내기 위해 IP와 함께 사용하는 프로토콜

##### 신뢰성이 요구되는 애플리케이션에서는 TCP를 사용

#### 특징



### UDP(User Datagram Protocol)

##### 데이터를 데이터그램 단위로 처리하는 프로토콜

##### 간단한 데이터를 빠른 속도로 전송하고자 하는 애플리케이션에서는 UDP를 사용



|                             TCP                              |                             UDP                              |
| :----------------------------------------------------------: | :----------------------------------------------------------: |
|    Connection-oriented protocol<br/> 연결지향형 프로토콜     |     Connection-less protocol<br/> 비 연결지향형 프로토콜     |
|   Connection by byte stream<br/> 바이트 스트림을 통한 연결   | Connection by message stream<br/> 메세지 스트림을 통한 연결  |
|      Congestion / Flow control<br/> 혼잡제어 / 흐름제어      | No Congestion / Flow control<br/> 혼잡제어 / 흐름제어 지원 X |
|    Ordered / Lower speed<br/> 순서 보장 / 상대적으로 느림    | Not ordered / Higer speed<br/> 순서 보장 X / 상대적으로 빠름 |
| Reliable data transmission<br/> 신뢰성 있는 데이터 전송 - 안정적 |     Unreliable data transmission<br/> 데이터 전송 보장 X     |
|         TCP packet : Segment<br/> 세그먼트 TCP 패킷          |        UDP packet : Datagram<br/> 데이터그램 UDP 패킷        |
|               HTTP, Email, File transfer 사용                |       DNS, Broadcasting (도메인, 실시간 스트리밍) 사용       |

