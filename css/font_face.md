## 웹 폰트 사용하기
### 웹 폰트란?
- 방문자의 로컬 컴퓨터에 폰트 설치 여부와 상관 없이 온라인의 특정 서버에 위치한 폰트 파일을 다운로드하여 화면에 표시해주는 웹 전용 폰트.
- 말 그대로 웹 폰트를 사용하면 어떤 사용자든 내가 적용시킨 폰트를 보여줄 수 있음.

### 웹 폰트 확장자
- EOT: IE8 이하에서 사용.
- TTF: 구형 안드로이드 버전(4.4)에서 필요.
- WOFF: 대부분의 모던 브라우저에서 지원.
- WOFF2: WOFF 2.0 원래 WOFF 확장자보다 압축률이 30% 정도 더 좋음.

### 웹 폰트 사용법
```css
@font-face {
  font-family:'coolfont';
	src: local('coolfont'),  
    url(../font/coolfont-B.eot#iefix) format("embedded-opentype"),
    url("../font/coolfont-B.woff2") format('woff2'),
    url("../font/coolfont-B.woff") format('woff'),
		url("../font/coolfont-B.otf") format('opentype'),
		url("../font/coolfont-B.ttf") format('truetype');
  font-weight:500;
  font-style:normal; 
}
@font-face {
  font-family:'coolfont';
	src: local('coolfont'),
    url(../font/coolfont-B.eot#iefix) format("embedded-opentype"),
    url("../font/coolfont-B.woff2") format('woff2'),
    url("../font/coolfont-B.woff") format('woff'),
		url("../font/coolfont-B.otf") format('opentype'),
		url("../font/coolfont-B.ttf") format('truetype');
  font-weight:500;
  font-style:normal; 
}
```
- `font-family`: 폰트명
- `src`: 폰트 url
- `font-weight`: 폰트 굵기
- `font-style`: 폰트 스타일

### 웹 폰트 최적화
#### 1. `src` 폰트 확장자 순서
- `src` 로 폰트를 불러올 때, 가장 최신의 폰트 확장자를 먼저 선언해주어야 한다.
- 최신 -> 오래된
- 그러나 주의할 점은 IE 를 지원하기 위해 .eot 확장자를 쓸 경우엔 가장 앞에 작성해주어야 한다.

#### 2. local 설정
- `src` 최상단에 `local('해당폰트')`를 지정해주면 사용자 로컬에 폰트가 있을 시, 불필요하게 웹 폰트를 다운받지 않게 할 수 있다.

#### 3. `font-weight` 만 다를 경우엔 `font-family` 동일하게 지정
- 동일한 폰트이지만, 굵기만 다를 경우엔 상위 예시처럼 `font-family` 는 동일하게 하되, `font-weight`만 달리 지정해주면 된다.
