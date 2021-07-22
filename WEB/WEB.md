# WEB

🌕 웹 (Web) : 월드 와이드 웹의 약자

➡️ 사전적 의미 : 거미줄 🌐 '세상 크기만한 거미줄'

⇒ 인터넷에 연결된 사용자들이 서로의 정보를 공유할 수 있는 공간

(어떠한 종류의 컴퓨터를 사용하여도 한 가지 종류의 표준 사용자 환경으로 조작 가능)

⏬

웹이 구동되는 주요 요소 - Web Browser (클라이언트) : 우리가 사용하는 웹페이지 → 사용자

```
                               - Web Server (서버) : 웹페이지 요청에 응답 → 제공자
```

![Untitled.png (1440×411)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/537b0df0-fad1-4d25-8a91-ddfc78a74212/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210722%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210722T143242Z&X-Amz-Expires=86400&X-Amz-Signature=8b81a795ad1c06f6f8cf259e65caf1eec711a1dc3b9a950c2528d9faa09c70c3&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

클라이언트 : 서버가 어떤 식으로 요청을 처리하는지 알고 싶지도 않고, 알기도 어렵다!

⇒ 추상화된 인터페이스 ([API](https://www.notion.so/API-5d277561a99c4421bc3120bfb4add15e) : Application Programming Interface)를 바탕으로 원격 서버에 요청 (RPC : Remote Procedure Call)하고 응답에 대해 적절한 형태로 화면에 표시

"오는 말이 고우면 가는 말이 곱다. " (컴퓨터 버전 🖥️)

- 클라이언트 : 웹에 들어갔을 때 보는 페이지, 'view page'  〰️ '프론트엔드'
- 서버 : 웹에 대한 요청을 받아들이는 곳. 요청에 대한 로직 & 데이터베이스 연동 〰️ '백엔드'

![Untitled.png (1440×688)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/1e0c97d8-4d4e-4576-acc9-d5934e645304/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210722%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210722T143251Z&X-Amz-Expires=86400&X-Amz-Signature=6026c0a9cf27d7ae8249f9ddc83d6a7d1e7c05351686bd05e1452a27502ff682&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

1. 웹 브라우저 : 도메인 입력 (사용자 : URL 입력)
2. 웹 브라우저 → 운영체제 → 하드웨어를 거쳐 서버에 전달
3. 서버 : 요청받아 하드웨어 → 운영체제 → 웹 서버에 도달
4. 도메인에 대한 index.html 파일을 찾아 다시 클라이언트에 전달

- DNS 서버 : 도메인에 대한 입력값을 IP(이는 웹 서버를 찾아주는 위치)로 되돌려줌

💬 현재의 웹 : 클라이언트와 서버가 존재
 클라이언트의 요청 → 어딘가에 있는 서버 내 존재하는 파일을 불러와 브라우저에 띄우게 되는 것

------

🌕 URI ❓ URL ❓

### URI (Uniform Resource Identifier) → 유일❗

: 인터넷의 자원을 나타내는 고유 식별자 ( 인터넷에 있는 자료의 id)

⇒ 특정 문법 존재   ex)    http://0JUUU.tistory.com

```
                                     프로토콜       도메인 이름
```

: URI의 타입으로 URL, URN, URC 등이 존재

![Untitled.png (1440×731)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/25950644-1ade-4183-8142-8e2357eafa7e/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210722%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210722T143304Z&X-Amz-Expires=86400&X-Amz-Signature=15a2101756c834c2f2ce9bf044f786b71661b69ada2327c3adde2a2f1cb2348c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

### URL (Uniform Resource Locator) : 위치지정자 → 프로토콜 포함 ⭕

: 해당 자원의 위치, Path를 의미. 일반적으로 사이트 도메인을 자주 의미

/ 네트워크 상에 자원이 어디에 위치하는지를 알려주는 규칙

→ 주소에 접속하기 위해서는 url에 맞는 프로토콜을 알아야 하고, 동일한 프로토콜로 접속 필수❗

### URN (Uniform Resource Name) : 자원식별자 → 프로토콜 포함 ❌

: 해당 자원의 이름을 의미, 독립적인 자원 지시자.

⏬ URL과의 차이 : URN - 리소스 식별만 가능 / 리소스를 얻을 수 있는 위치 포함❌

```
                                                    → 리소스 위치 관련 없이 고유하게 식별하려는 목적
```

- 리소스 식별자 → URI = URL + URN + α
- 이름으로 식별 → URN
- 위치로 식별 → URI

EX ) 두 사람 존재 → 구분하고 싶어요❗

1. 이름 붙이기 → URN ( 홍길동 / 김길동)

2. 그 리소스를 얻을 수 있는 주소 (위치) 표현 → URL

   ```
                                                          (서울시 강남구 역삼동 111-1 / 서울시 강남구 역삼동 123-2)
   ```

⇒ 이러한 방법으로 리소스를 명확히 식별할 수 있으면 (구분 ⭕) URI

URN과 URL 모두 URI이다❗

➕ URL의 한계

URL : 주소 → 즉, 특정 시점에 어떤 것이 위치한 곳을 알려줌

🔻

http://0JUUU.tistory.com/19 ⇒   http://0JUUU.cs.tistory.com/19

⏩ 바뀌면 페이지 접근 불가 : 리소스가 옮겨지면 더 이상 해당 URL 사용 불가❗

![Untitled.png (1593×666)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/227828ea-6d25-48af-8163-5955531a5021/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210722%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210722T143317Z&X-Amz-Expires=86400&X-Amz-Signature=b0bd99be051353a33833200c75757ac1d2cb5d2a7d7c837b84e931eb4417582f&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)

url 문법에 어긋나면 브라우저 기본 검색엔진에서 검색

> https://sowells.tistory.com/193   (혼란 부분)