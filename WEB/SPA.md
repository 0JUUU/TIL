# SPA



**S**ingle **P**age **A**pplication

: 단일 페이지 애플리케이션 - 한 개(Single)의 Page로 구성된 Application❗

➡ 웹 애플리케이션에 필요한 모~든 정적 리소스(HTML, CSS, JS) 를 최초❗ 한 번에 다운로드

➡ if 새로운 페이지 요청 → 페이지 갱신에 **필요한 데이터만** 전달 받아서 페이지 갱신🔁

(초기 요청 : 서버에서 첫 페이지 처리 / 이 후 라우팅 : 클라이언트에서 처리)

e.g. Angular, React, Vue, ...

![Untitled.png (1080×583)](https://s3.us-west-2.amazonaws.com/secure.notion-static.com/89c0f1d3-d394-481e-9a5f-34316781a40b/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Credential=AKIAT73L2G45O3KS52Y5%2F20210725%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20210725T143537Z&X-Amz-Expires=86400&X-Amz-Signature=4d862f5765654f316ac82cd2d19e2a5f5ab4875fd32bc224bcc9311d9f62617a&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22)



👍 **SPA 장점**

1. 자연스러운 사용자 경험(UX)
   1. 전체 페이지 : 업데이트할 필요 ❌ → 빠름 & 깜빡거림 ❌
2. 필요한 리소스만 부분적으로 로딩(성능)
   1. SPA의 Application : 서버에게 정적 리소스 한 번만 요청 & 받은 데이터 전부 저장
3. 서버의 템플릿 연산을 클라이언트로 분산
4. 컴포넌트별 개발 용이
5. 모바일 앱 개발을 염두에 둔다면 동일한 API를 사용하도록 설계 가능

👎 **SPA 단점**

1. JavaScript 파일 번들링 ➡ 한 번에 받음 ⇒ 초기 구동 속도가 느림 (Webpack 의 code splitting으로 해결 가능)
2. 검색엔진최적화(SEO)가 어려움 ⇒ SSR로 해결 가능
3. 보안 이슈 ⇒ 프론트엔드에 비즈니스 로직 최소화

### 구현 조건

1. 자바스크립트에서 브라우저로 페이지 전환 요청을 보낼 수 있다. 단, 브라우저는 서버로 요청을 보내지 않아야 한다.
2. 브라우저의 뒤로 가기와 같은 사용자의 페이지 전환 요청을 자바스크립트에서 처리할 수 있다. 단, 브라우저는 서버로 보내지 않아야 한다.

⏩ 이러한 조건 만족하는 브라우저 API : pushState, replaceState 함수, popState 이벤트

Q. localStorage sessionStorage 모두 cookie인가요 (그냥 내 궁금증....)

https://velog.io/@ejchaid/localstorage-sessionstorage-cookie의-차이점

## MPA

페이지 **전환할 때마다** 렌더링 결과를 서버에서 받음 ⇒ 화면 깜빡 ⚡

🙋‍♀️ SPA VS MPA