### SPA

: Single Page Application
한 개의 웹 페이지 안에서 사용자와 상호작용하며 **필요한 부분만 동적으로 업데이트**하는 웹 어플리케이션입니다.

- 처음에만 전체 페이지를 로드하고 이후부터는 필요한 데이터만 교환하여 페이지의 **일부분만 업데이트**하여 사용자와의 **상호작용**을 자연스럽게 만들어 주어 네이티브앱과 유사한 사용감을 제공합니다.
- React, Vue.js, Angular등으로 **컴포넌트 기반 개발**을 가능하게 하여 **코드 재 사용성과 유지 보수성**을 향상시킵니다.

<br/>

### 장점

1. 사용자 경험 향상 : SPA는 페이지 간 전환시 화면 깜빡임없이 부드럽게 전환되므로 **사용자 경험**을 향상시키고 더 나은 인터랙션과 **빠른 응답 속도**를 제공할 수 있습니다.
2. 성능개선 : 초기에 필요한 리소스(HTML, CSS, JavaScript 등)를 한 번에 로드하고 이후에는 **필요한 데이터만 비동기적으로 로드**하기 때문에 네트워크 대역폭을 절약하고 서버 부하를 줄일 수 있습니다.
3. 개발 및 유지보수 용이성 : SPA는 **클라이언트 측에서 데이터와 UI를 관리**하기 때문에 서버와의 상호작용을 최소화하고 코드 베이스를 단순화할 수 있습니다.
   <br/>

### 단점

1. 초기 로딩 시간
   : 모든 리소스(HTML, CSS, JavaScript 등)을 처음에 다운로드해야 하므로 **초기 로딩시간**이 길어질 수도 있습니다.
2. SEO(Search Engine Optimization/검색 엔진 최적화)에 취약
   대부분의 웹 크롤러가 JavaScript 실행 후 생성된 DOM 요소를 인식하지 못하기 때문입니다.(= JS는 실행하지 않고 HTML만 분석할 수 있기 때문에 동적으로 생성된 콘텐츠를 색인화하지 못할 수 있어 SEO에 영향을 줄 수 있음 / 로드 되기 전 빈 상태의 코드를 크롤링해 인덱싱이 제대로 이루어 지지 않음 )=> 최근엔 Google등 주요 검색 엔진들이 Js 렌더링에 대응하는 중
   <br/>

---

### MPA

: Multi Page Application
전통적인 웹 애플리케이션 구조로 사용자가 링크를 클릭하거나 데이터를 제출할 때마다 새로운 페이지 요청이 서버로 전송되고 서버는 **새로운 HTML페이지를 생성**하여 응답합니다. 초기구동속도는 빠르지만 사용자 경험에 매번 **불필요한 로딩 시간**을 초래하고 서버에 부담이 갑니다.