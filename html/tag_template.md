### `<template>` 태그란?

- 실제로 스크립트를 이용해 어딘가 붙여넣기 전까지는 사용자에게 보이지 않는 HTML 조각.
- `<template>` 요소 내의 콘텐츠는 페이지가 로드될 때 즉시 렌더링되지 않고, 나중에 자바스크립트를 사용하여 해당 콘텐츠를 복제한 후 보이도록 렌더링함.

### 어떻게 활용?

- 자바스크립트를 이용하여 유동적으로 HTML 요소들을 만들어 내야 할 때.

origin

```jsx
btn.addEventListener('click', function () {
  var template = '<div class="row"><h2 class="content">template tag here</h2></div>';
  el.appendChild(template);
})
```

- 이렇게 직접 자바스크립트에 태그를 작성해주었다면,

template

```html
<template id="exam-template">
  <div class="row">
    <h2 class="content">template tag here</h2>
  </div>
</template>
```

```jsx
btn.addEventListener('click', function () {
  var template = document.getElementById('exam-template').html;
  el.appendChild(template);
})
```

- 다음과 같이 스크립트로 복사하여 불러내듯 사용할 수 있다.

### 장점

- 이렇게 해당 HTML 내부에 필요한 요소들을 작성해두고, 나중에 스크립트로 복사하여 언제든, 몇번이든 나타낼 수 있다는 것이 장점.
- 스크립트가 작용되기 전까진 해당 HTML 문서 내부에 없는 것으로 여겨짐.

### 지원 범위
- IE, Opera mini 대응 불가
- 이외엔 전부 지원
