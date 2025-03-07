# Application Layer

- **매핑 원리**:  
  IP 주소와 포트를 통해 하나의 포트에 하나의 프로세스를 매핑한다.  
  클라이언트가 IP 주소와 포트 번호를 입력하면, DNS를 통해 해당 사이트에 접속할 수 있다.

## 왜 공통된 포트를 사용할까? (예: 80, 8080)
- **이유**:  
  DNS는 IP 주소만 변환해주므로, 클라이언트는 공통된 포트를 통해 서버에 접속하게 된다.

## Transport Layer에서의 지원
- **데이터 무결성**:  
  Transport Layer는 데이터가 변조 없이 정확하게 전달되도록 지원한다.

## HTTP (Hyper Text Transfer Protocol)
- **구조**:  
  - Request  
  - Response
- **특징**:  
  - Transport Layer의 TCP를 사용하여 신뢰성 있는 데이터 전송을 지원한다.
  - **Stateless**: 각 요청은 독립적으로 처리되며, 서버는 이전의 요청 상태를 저장하지 않는다.

### HTTP Connections
1. **Non-Persistent**:  
   - 매 요청마다 새로운 연결을 설정한다.
2. **Persistent (Default)**:  
   - 연결을 맺은 후, 여러 요청/응답에 재사용한다.

## Socket Programming

### Socket의 종류
- **TCP Socket**
- **UDP Socket**

### Socket Functions
- **서버 측**:  
  1. `socket()`  
  2. `bind()`  
  3. `listen()`  
  4. `accept()`
- **클라이언트 측**:  
  1. `socket()`  
  2. `connect()`  
  3. `read()`, `write()`
