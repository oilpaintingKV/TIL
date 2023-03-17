## 가상 선택자 [:(가상 클래스), ::(가상 요소)]

### 가상 요소 (Pseudo Elements)
`::before` , `::after` , `::first-letter` , `::first-line` , `::selection`
- 가상으로 요소(엘리먼트)를 생성해주는 기능
- 생성된 요소(엘리먼트)에게 내용(content) 와 css 속성을 부여할 수 있다.

### 가상 클래스 (Pseudo Classes)
`:active` , `:checked` , `:disabled` , `:focus` , `:hover`, `:link`, `:first-child`, `:nth-child(n)` 등
- 가상으로 class를 생성해주는 기능
- 별도의 class 지정 없이 해당 요소에게 css 속성을 부여할 수 있다.

### 가상 요소 IE
- CSS3에서만 더블콜론(::)을 사용할 수 있음.
- 하지만 CSS3를 지원 하지 않는 IE8의 경우는 싱글콜론만 지원함.
- IE8 까지 맞춰주어야 할 경우 싱글콜론(:)만 사용할 것
