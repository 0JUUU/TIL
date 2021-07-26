# WebRTC 🎥

**Web Real-Time Communication**

![Untitled.png (729×462)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/34e7d881-3ab8-44eb-9503-8b7a69dee515/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142004Z&X-Amz-Expires=86400&X-Amz-Signature=aa9c37a34989b798e43695aec79f6bac967346738cc174619079d7944a5f81a0&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

웹 브라우저 간 플러그인의 도움 없이 서로 통신할 수 있도록 설계된 **JavaScript API**

➡ 음성 통화, 영상 통화, P2P 파일 공유 등으로 활용 가능

### 통신 원리

![Untitled.png (1280×593)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/794e6dc9-5a73-4194-ad95-a56ce53ce552/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142013Z&X-Amz-Expires=86400&X-Amz-Signature=be1ab5ee3d88c385bef7fed66528d73e27a7a1115454c4c154ac383f05a61633&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

P2P 통신 ➡ 동등 계층간 통신방식으로 클라이언트, 서버의 개념 없이 동등한 노드들로 구성

⇒ 데이터 주고받는 형식

**어떻게 가능할까❓**

**실시간 웹 데이터 교환 가능한 이유** ➡ 시그널링이라고 일컫어지는 NAT 우회 과정을 거치기 때문

![Untitled.png (700×436)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1c1e51e5-a9c9-44f2-9c24-654fe1a7106b/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142022Z&X-Amz-Expires=86400&X-Amz-Signature=f6c2d0efb00d5fa91c511dd6b05fa28a2ab27d9e3c2f4b34c93875b853ba8a98&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

크게 3가지 클래스에 의해 실시간 데이터 교환 ⭕

- MediaStream - 카메라와 마이크 등의 데이터 스트림 접근
- RTCPeerConnection - 암호화 및 대역폭 관리 및 오디오, 비디오의 연결
- RTCDataChannel - 일반적인 데이터의 P2P 통신

⇒ 데이터 교환 &  RTCPeerConnection들이 적절하게 데이터 교환할 수 있게 처리해주는 과정 : **시그널링(Signaling)**

주요 구성 요소 : 여러 자바스크립트 API 포함

- getUserMedia : 오디오, 비디오 미디어를 가져온다. (MEDIA 기기에 접근)

- RTCPeerConnection : 피어 간 오디오, 비디오 통신 활성화 / 신호 처리, 코덱 관리, P2P 통신, 보안, 대역폭 관리 수행 ⇒ 두 Peer간 안정적이고 효율적인 통신 설정 & 관리

- RTCDataChannel : 피어 간 양방향 임의 데이터 통신 허용 / 웹소켓과 동일한 API 사용

  (text, file, data 등 전송 가능)

  → 매우 낮은 레이턴시를 보임

➕ 통계 함수 포함

- getStats : 웹 애플리케이션에 WebRTC 세션에 관한 통계 집합의 검색 허용

WebRTC : 서버와 같은 중간자를 거치지 ❌ ➡ 브라우저 간을 P2P로 연결하는 기술

(e.g. 화상 통화, 실시간 스트리밍, 파일 공유, 스크린 공유, ...)

➡ 중개 서버 ❌ ⇒ 빠른 속도 보장

& HTTPS 강제 ⇒ 중간자 공격에 대한 보안 보장

& 실시간 상호작용 가능 ⇒ 더욱 개인화, 참여 유도적인 웹 애플리케이션 제작 가능

## WebRTC 장점과 단점

### 장점

1. Latency가 짧다.

인스타라이브, 유튜브라이브, 트위치 : RTMP 사용 → 실시간 스트리밍

- WebRTC : RTMP보다 낮은 Latency & 지연시간 거의 없는 REAL-TIME과 비슷한 방송 가능

  ⚡ RTMP (Real Time Messaging Protocol) : 어도비 시스템즈의 독점 컴퓨터 통신 규약

![Untitled.png (512×288)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5ab9aa24-1277-4c40-96e5-25b06f28d177/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142032Z&X-Amz-Expires=86400&X-Amz-Signature=1ae3fee5b701c2662175be2fbce42e0e0d3194fdd09dbceae3f6ffe1b488228c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

물론 WebRTC보다 Latency가 짧은 기술 존재 ⇒ 구글에서 미는 애 : WebRTC

1. 별 다른 소프트웨어 없이 실시간 커뮤니티 가능
   - 웹/앱 방송 ⇒ 별도의 플러그인이나 미디어 송출 관련 소프트웨어 따로 설치할 필요 ❌
2. 개발하는 데 있어 진입장벽 낮다.
3. 무료

### 단점

1. 크로스 브라우징 문제

   1. 다양한 플랫폼과 브라우저에서 접속하는 사용자들에게 동일한 사용자 경험 제공

   ⏩ 브라우저 호환성

   ### 브라우저 호환성

   ![https://wormwlrm.github.io/img/posts/2021-01-24/3.png](https://wormwlrm.github.io/img/posts/2021-01-24/3.png)

   WebRTC : 구글이 주도한 오픈소스 프로젝트 ⇒ 크롬에 호환성 ⏫ / 파이어폭스, 오페라 GOOD

   / BUT, 사파리 → WebKit 기반 브라우저라 WebRTC 지원하나, 호환성 ⏬ 지원해주는 설정 ⏬

2. STUN/TURN 서버 필요

### P2P 절차

: WebRTC → P2P 방식 커뮤니케이션

1. 각 브라우저가 P2P 커뮤니케이션에 동의
2. 서로의 주소 공유
3. 보안 사항 및 방화벽 우회
4. 멀티미디어 데이터 실시간 교환

⇒ 2, 3 : 일반적인 웹 개발의 접근 방법으로 해결 불가 ❌ (브라우저 : 웹 서버 ❌ ⇒ 외부에서 접근할 수 있는 주소 ❌)

⏩ WebRTC : P2P 기반이지만 통신 설정 초기 단계에서는 중재자의 역할 필수❗

### 방화벽과 NAT 트래버셜

🖥️ 일반적인 컴퓨터 : 공인 IP 할당 ❌ (cuz, 방화벽 (Firewall), 여러 대의 컴퓨터가 하나의 공인 IP를 공유하는 NAT, 유휴 상태의 IP를 일시적으로 임대받는 DHCP 때문)

⇒ 단순히 공인 IP만 안다고 해서, 특정한 사용자 가리킬 수 ❌

➡ 공인 IP & 해당 네트워크에 연결된 사설 IP 주소까지 알아야 특정 사용자 지정 가능⭕

- 라우터 : NAT 역할 (외부에서 접근하는 공인 IP & 포트 번호 확인 ⇒ 현재 네트워크 내 사설 IP 매핑)

➡ 브라우저 통신 : 각자 현재 연결된 라우터와 공인 IP 주소와 포트 알아내야 함

⚠️ 몇몇 라우터 : 특정 주소 OR 포트와의 연결 차단하는 방화벽 설정

⇒ 라우터 통과해서 연결할 방법을 찾는 과정 : NAT 트래버셜 (NAT traversal)

### STUN, TURN

![Untitled.png (825×379)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/5cd70561-e5ab-4cff-a472-9bc82f98bf1e/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142045Z&X-Amz-Expires=86400&X-Amz-Signature=6768ed06fd6480db54cbd1883151a26edb04bb745bb7023415301ce1d6a64ec8&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

: NAT 트래버셜 작업 ⇒ STUN (Session Traversal Utilities for NAT) 서버에 의해 이루어짐

✔ STUN 방식 : 단말이 자신의 공인 IP 주소와 포트를 확인하는 과정에 대한 프로토콜

⇒ 유일하게 자기 자신을 식별할 수 있는 정보 반환

(WebRTC 연결 시작 전, STUN 서버를 향해 요청

⇒ STUN 서버 : NAT 뒤에 있는 피어(Peer)들이 서로 연결할 수 있도록 공인 IP와 포트 찾아줌)

⚠️ STUN 서버를 이용해도 항상 자신의 정보를 알아낼 수 있는 것 ❌

(다른 방화벽 정책 / 이전 연결 내역이 있는 네트워크만 허용 : Symmetirc NAT)

➡ STUN 서버를 통해 자기 자신의 주소를 찾아내지 못했을 경우, **TURN(Traversal Using Relay NAT)** 서버 대안으로 이용

📢 <b>TURN 방식</b>

네트워크 미디어를 중개하는 서버 이용하는 것

⇒ 중간 서버 한 번 거침 : P2P 통신 ❌ ➡ 구조상 **지연**이 필연적으로 발생

But, 보안 정책 엄격한 개인 NAT 내부에 위치한 브라우저와 P2P 통신을 할 수 있는 **유일한** 방법

❗ TURN 방식 : 최후의 수단

### 시그널링

![Untitled.png (834×520)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/afa5b80e-c27f-4c58-a440-67c3a2e355df/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142055Z&X-Amz-Expires=86400&X-Amz-Signature=26ce568fc03a44cfd952a4dcce8705d21a94967e8c25de73ce9b3c074ef76dd8&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

RTCPeerConnection 통신에 사용할 프로토콜, 채널, 미디어 코덱 및 형식, 데이터 전송 방법, 라우팅 정보, NAT 통과 방법을 포함한 통신 규격을 교환하기 위해 두 장치의 제어 정보를 교환하는 과정

P2P 통신이 일어나기 전(데이터 전송 전) ⇒ 세션 제어 메시지, 네트워크 구성, 미디어 기능 등의 정보 교환 시 사용

- 세션 제어 메시지 : 통신 초기화 OR 닫고 오류 보고
- 네트워크 구성 : 외부 세계 컴퓨터의 IP 주소와 포트 파악
- 미디어 기능 : 브라우저와 통신하려는 브라우저에서 처리할 수 있는 코덱과 해상도 파악

⚠️ **Signaling** (WebRTC 자체에서 지원하는 기능 ❌ ⇒ WebRTC 연결 전 미리 준비해야 하는 과정 & 정해진 규약 ❌  (알 수 없는 두 장치가 언제 어떤 방식으로 연결될 수 있는지의 모든 경우를 예측하는 것은 불가능하기 때문❗ ))

⇒ 개발자 : 자신에게 맞는 최적의 방법 선택

1. 두 개의 장치 연결할 수 있는 시그널링 서버 직접 구축

   - 웹 소켓 (Web Socket) 이나 서버 전송 이벤트 (Server-sent Event) 방법 적용 가능

   ⇒ 시그널링 정보 조회 가능한 API 생성 후, 브라우저 단에서 주기적으로 XHR 요청하는 폴링 기법 사용 가능

   REF)

   [muaz-khan/WebRTC-Experiment](https://github.com/muaz-khan/WebRTC-Experiment/blob/master/Signaling.md)

2. 시그널링 서버를 제공해주는 외부 솔루션 적용 가능

   - 아마존 Kinesis Video Stream
   - 구글 AppRTC : Google App Engine 으로 구현된 시그널링 서버 확인 가능

💬😁 ㅋㅋㅋㅋㅋㅋㅋㅋ TCP VS UDP

![Untitled.png (693×397)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1fabba1b-c34d-4eae-a3c7-54ce22a4ba19/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210726%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210726T142105Z&X-Amz-Expires=86400&X-Amz-Signature=14bd769d69316f7dd02c54cc61486547376fb227c4f8c8beab531056e97f377e&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

➕ 단점 정리

1. 브라우저 호환성
2. 시그널링 서버에 대한 명시적 표준 ❌
3. WebRTC : 실시간성 매우 중요 ➡ UDP 위에서 동작 ⇒ 데이터 빠르게 전송 가능 / But, 데이터 손실 발생 가능 ( 중요 파일 전송 시 매우 큰 문제)