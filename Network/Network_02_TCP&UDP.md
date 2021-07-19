# TCP, UDP

## TCP(Transmission Control Protocol)

##### 인터넷상에서 데이터를 메세지의 형태로 보내기 위해 IP와 함께 사용하는 프로토콜

##### 장치들 사이에 논리적인 접속을 성립(establish)하기 위하여 연결을 설정하여 **신뢰성을 보장하는 연결형 서비스** 

##### TCP는 네트워크에 연결된 컴퓨터에서 실행되는 프로그램 간에 일련의 옥텟(데이터, 메세지, 세그먼트)을 안정적, 순차적, 에러없이 교환할 수 있게 함

##### 그렇기 때문에 신뢰성이 요구되는 애플리케이션에서는 TCP를 사용

### 특징

#### 연결형 서비스

- 3-way handshaking 과정을 통해 연결 설정
- 4-way handshaking 과정을 통해 연결 해제

#### 흐름제어 (Flow Control)

데이터 처리 속도를 조정하여 수신자의 버퍼 오버플로우 방지

- 송신하는 곳에서 감당이 안되게 많은 데이터를 빠르게 보내 수신하는 곳에서 문제가 일어나는 것을 막음
- 수신자가 윈도우크기(Window Size) 값을 통해 수신량을 정할 수 있음

#### 혼잡제어 (Congestion Control)

네트워크 내의 패킷 수가 넘치게 증가하지 않도록 방지

- 정보의 소통량이 과다하면 패킷을 조금만 전송하여 혼잡 붕괴 현상이 일어나는 것을 방지

#### 신뢰성이 높은 전송(Reliable Transmission)

- ##### Dupack-based retransmission

  ​	정상적인 상황에서는 ACK 값이 연속적으로 전송되어야 함

  ​	그러나 ACK값이 중복으로 올 경우 패킷 이상을 감지하고 재전송을 요청함

- ##### Timeout-based retransmission

  ​	일정시간동안 ACK 값이 수신을 못할 경우 재전송을 요청함

#### 전이중, 점대점 방식

- ##### 전이중 (Full - Duplex)

  ​	전송이 양방향으로 동시에 일어날 수 있음

- ##### 점대점 (Point to Point)

  ​	각 연결이 정확이 2개의 종단점을 가지고 있음

   	=> 멀티캐스팅(1:N)이나 브로드캐스팅(1:N)을 지원하지 않음

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

