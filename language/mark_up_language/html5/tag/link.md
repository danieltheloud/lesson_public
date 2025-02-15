# link

- 현재 문서와 외부 리소스 간의 관계를 지정한다.
- 이 요소는 `CSS`를 연결하는 데에 가장 일반적으로 사용되며, 사이트 아이콘을 설정하는 데에도 사용된다.

## 속성

- `as`: `<link>` 요소에 `rel="preload"` 또는 `rel="modulepreload"` 속성을 지정했을 때만 사용한다.
  - 유효 값
    - `audio`: `<audio>` 요소
    - `document`: `<iframe>` 과 `<frame>` 요소
    - `embed`: `<embed>` 요소
    - `fetch`: fetch, XHR
    - `font`: CSS @font-face
    - `image`: srcset 또는 imageset 속성을 가지고 있는 `<img>` 와 `<picture>` 요소, SVG `<image>` 요소, CSS `*-image` 규칙
    - `object`: `<object>` 요소
    - `script`: `<script>` 요소, Worker `importScripts`
    - `style`: `<link rel=stylesheet>` 요소, CSS `@import`
    - `track`: `<track>` 요소
    - `video`: `<video>` 요소
    - `worker`: Worker, SharedWorker

- `crossorigin`: 리소스를 가져올 때 `CORS`를 사용해야 하는지 나타내는 열거형 속성이다.
  - `CORS` 활성화 이미지는 `<canvas>` 요소를 "오염"(taint)시키지 않고 재사용할 수 있다.
  - `crossorigin` 속성이 존재하지 않으면 리소스를 `CORS` 요청 없이 가져오므로, 리소스의 오염 없이는 사용이 불가능하다.
  - 유효하지 않은 값은 `anonymous`를 지정한 것으로 간주합니다.
  - 유효한 값
    - `anonymous`: 교차 출처 요청(`cross-origin request`; Origin HTTP 헤더를 가진 요청)을 수행하지만, 인증 정보(쿠키, X.509 인증서, HTTP Basic 인증)를 전송하지 않는다.
    - `use-credentials`: 교차 출처 요청(`cross-origin request`; Origin HTTP 헤더를 가진 요청)을 수행하면서 인증 정보(쿠키, X.509 인증서, HTTP Basic 인증)를 한 가지 이상을 발송한다.
    > 서버에서 (`Access-Control-Allow-Origin` HTTP 헤더를 설정하지 않음으로 인해서) 출처 사이트에 인증 정보를 전달하지 않으면, 리소스가 오염되어 사용처가 제한된다.
- `href`: 연결할 리소스의 `URL`이다.
  > 절대 `URL`과 상대 `URL` 모두 가능하다.
- `hreflang`: 연결할 리소스가 사용하는 언어이며, 오직 제안하는 용도로만 사용된다.
  > 가능한 값은 `RFC 5646`(`BCP 47`)에 따르며, `href` 속성이 존재할 때만 사용한다.
- `imagesizes`: `rel="preload"`와 `as="image"` 속성에 대해서만, `srcset` 속성과 유사한 문법과 의미를 가진다.
  - 이는 `srcset` 및 `sizes` 속성에 해당하는 값을 가진 `img` 요소가 사용하는 적절한 자원을 `preload`하는 것을 나타낸다.
- `integrity`: 무결성을 확인하기 위한 인라인 메타데이터를 포함하며, 이는 브라우저로 하여금 가져오도록 지시하려는 리소스(파일)를 `Base64`로 인코딩한 암호학적 해시이다.
  > `stylesheet`, `preload`, `modulepreload`와 같은 속성과 함께 사용된다.
- `media`: 연결된 리소스를 적용할 미디어를 명시한다.
  - 값으로는 반드시 미디어 유형이나 미디어 쿼리를 사용해야 한다.
  - `media` 특성은 사용자 에이전트가 현재 장치에 맞춰 최적의 스타일시트를 선택하도록 할 수 있으므로 주로 외부 스타일시트를 연결할 때 유용하다.
- `referrerpolicy`
- `rel`
- `title`
- `type`

<!-- TODO -->
