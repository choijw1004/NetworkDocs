# Computer Network Basic

## Closer Look at Network Structure
- **Network Edge**:  
  어플리케이션, 호스트
- **Network Core**:  
  라우터, 네트워크의 네트워크
- **Access Network / Physical Media**:  
  Communication Link

## Network Edge
- **End System (Hosts)**  
  - 애플리케이션  
  - Client/Server Model  
  - Peer-to-Peer Model

## 데이터 통신 서비스
### Connection-Oriented Service
1. **TCP (Transmission Control Protocol)**
   - **Reliable**: 신뢰성을 보장하며 메시지 유실을 방지한다.
   - **In-Order Byte Stream**: 전송된 바이트의 순서를 보장한다.
   - **Flow Control**: 수신 측의 처리 속도에 맞춰 송신 속도를 조절한다.
   - **Congestion Control**: 네트워크 혼잡을 감지하고 제어한다.
   - **비용**: UDP에 비해 상대적으로 많은 자원(비용)을 소모한다.

2. **UDP (User Datagram Protocol)**
   - **No Connection Control**: 연결 설정 없이 데이터를 전송한다.
   - **Unreliable**: 신뢰성을 보장하지 않는다.
   - **No Flow Control**: 송신 측에서 속도 조절이 없다.
   - **No Congestion Control**: 혼잡 제어 기능이 없다.
   - **속도**: TCP보다 전송 속도가 상대적으로 빠르다.

## Protocol
- **정의**: 메시지를 전송하기 위한 규약  
- **중요성**: Sender와 Receiver가 동일한 프로토콜을 사용해야 정상적인 통신이 가능하다.

## Network Core
- **위치**: 주로 라우터가 존재함

### Switching Techniques
- **Circuit Switching**
  - 출발지에서 목적지까지 경로를 미리 지정하고, 중간에 사용자가 개입하는 방식.
- **Packet Switching**
  - 사용자가 보내는 패킷을 라우터가 포워딩하는 방식.

### Packet Switching vs. Circuit Switching
- 예를 들어, 1Mbps 대역폭 링크에서:
  - **Circuit Switching**: 한 사용자가 100kb/s를 사용하면 최대 10명 이용 가능.
  - **Packet Switching**: 통계적 특성을 이용해 약 35명 정도 이용 가능.

## 딜레이가 생기는 이유
패킷 전송 시 발생하는 딜레이는 여러 단계로 나뉩니다.

1. **패킷 검사 및 목적지 결정 Delay**
   - **원인**: 라우터가 패킷을 검사하고 목적지를 결정하는 과정.
   - **개선 방법**: 라우터 성능 개선.

2. **Queueing Delay**
   - **원인**: 라우터 앞단의 버퍼에서 속도와 대역폭 제어를 위해 발생.
   - **개선 방법**: 현실적으로 개선이 어려워 대부분의 딜레이가 이 단계에서 발생.

3. **Transmission Delay**
   - **원인**: 패킷의 비트들이 링크를 통해 전송되는 데 걸리는 시간.
   - **계산**: (패킷 크기) / (링크 대역폭)
   - **개선 방법**: 링크 대역폭 성능 개선.

4. **Propagation Delay**
   - **원인**: 패킷이 링크를 따라 전파되어 목적지에 도달하는 데 걸리는 시간.
   - **계산**: (링크 길이) / (빛의 속도)

## 패킷 유실 (Packet Loss)
- **발생 조건**:  
  큐(queue)의 크기가 한계(queueing size)보다 작을 때 패킷 유실 발생.
- **처리 방법**:  
  TCP는 패킷 유실 시 재전송을 수행한다. (Sender가 재전송하며, Sender와 Receiver를 제외한 라우터들은 "Dummy Core"로 정의됨)
